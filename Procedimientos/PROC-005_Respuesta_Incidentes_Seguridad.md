# PROCEDIMIENTO DE RESPUESTA A INCIDENTES DE SEGURIDAD
## Stamford Health and Solution SpA

---

**Código:** PROC-005  
**Versión:** 1.0  
**Fecha de aprobación:** 2 de junio de 2026  
**Aprobado por:** Comité de Seguridad de la Información  
**Propietario:** CISO  
**Clasificación:** CONFIDENCIAL - USO INTERNO  
**Política asociada:** PSI-004 — Política de Gestión de Incidentes  
**Referenciado por:** PSI-002 §10.3, PSI-002 §11

---

## CONTROL DE CAMBIOS

| Versión | Fecha | Descripción |
|---------|-------|-------------|
| 1.0 | 02/06/2026 | Versión inicial |

---

## 1. PROPÓSITO

Definir los pasos operacionales detallados que el equipo de seguridad debe seguir para detectar, contener, erradicar y recuperarse de incidentes de seguridad de la información, en cumplimiento de la PSI-004 y de las obligaciones regulatorias establecidas en la Ley 19.628 y la Ley 20.584.

---

## 2. ALCANCE

Este procedimiento aplica a todos los incidentes de seguridad que afecten o puedan afectar los sistemas de información, datos clínicos, datos personales o infraestructura de Stamford Health and Solution SpA, independientemente de su origen (interno, externo, accidental o deliberado).

---

## 3. REFERENCIAS

| Documento | Código |
|-----------|--------|
| Política de Gestión de Incidentes | PSI-004 |
| Política de Control de Accesos | PSI-002 |
| Política de Backup y Recuperación | PSI-005 |
| Formulario de Registro de Incidente | FORM-007 *(a crear)* |

---

## 4. ROLES Y RESPONSABILIDADES

| Rol | Responsabilidad en este procedimiento |
|-----|--------------------------------------|
| **Coordinador de Seguridad** | Receptor primario de reportes; activa el CSIRT; coordina la respuesta técnica |
| **CISO** | Autoridad máxima del incidente; aprueba comunicaciones externas; evalúa notificaciones regulatorias |
| **Equipo de Seguridad Técnica** | Análisis forense, contención técnica, erradicación |
| **Administradores de Sistemas** | Aislamiento de sistemas, restauración desde backup |
| **DBA** | Evaluación de integridad de bases de datos |
| **Asesor Legal** | Incidentes con implicaciones legales o regulatorias |
| **CEO** | Vocero ante medios y comunicaciones externas de alto nivel |

---

## 5. CLASIFICACIÓN DE INCIDENTES

*(Según PSI-004 — resumida aquí para referencia operacional)*

| Nivel | Denominación | Ejemplos | Tiempo de respuesta |
|-------|-------------|---------|---------------------|
| **1** | Bajo | Phishing bloqueado, malware contenido automáticamente | 24–48 horas |
| **2** | Medio | Intento de acceso fallido repetido, malware con limpieza manual | 4–8 horas |
| **3** | Alto | Acceso no autorizado exitoso, pérdida limitada de datos sensibles | 2–4 horas |
| **4** | Crítico | Ransomware activo, brecha de datos de pacientes, sistema HCE comprometido | Inmediato |

---

## 6. FASE 1 — DETECCIÓN Y REPORTE

### 6.1. Canales de reporte

| Canal | Uso |
|-------|-----|
| Correo: `seguridad@stamfordhealth.cl` | Reporte en horario laboral |
| Extensión interna 911 | Reporte urgente en horario laboral |
| Celular de guardia TI (publicado en intranet) | Reporte fuera de horario laboral |
| Sistema de monitoreo automático (SIEM) | Alertas automáticas 24/7 |

### 6.2. Información mínima requerida al reportar

1. Nombre del reportante y área
2. Fecha y hora de detección
3. Descripción del comportamiento inusual observado
4. Sistemas o equipos involucrados
5. Acciones ya tomadas (si alguna)

### 6.3. Validación inicial (responsable: Coordinador de Seguridad)

| Paso | Acción | Tiempo máximo |
|------|--------|---------------|
| 1 | Recibir y acusar recibo del reporte | 15 minutos |
| 2 | Validar si es un incidente real o falso positivo | 30 minutos |
| 3 | Clasificar el incidente (Niveles 1–4) | 30 minutos |
| 4 | Si Nivel 3 o 4: Notificar al CISO inmediatamente | Inmediato |
| 5 | Si Nivel 3 o 4: Activar el CSIRT | Inmediato |
| 6 | Abrir ticket de incidente con ID único | 30 minutos |

---

## 7. FASE 2 — CONTENCIÓN

### 7.1. Contención inmediata (0–30 minutos desde clasificación)

**Para incidentes que involucren acceso no autorizado a sistemas:**
1. Invalidar todas las sesiones activas de las cuentas comprometidas
2. Deshabilitar temporalmente las cuentas afectadas
3. Revocar tokens MFA registrados en las cuentas comprometidas
4. Revocar API keys o secretos potencialmente expuestos (ver sección 6.3 de PSI-002)

**Para incidentes que involucren malware o ransomware:**
1. Aislar el equipo de la red (desconectar cable o desactivar WiFi)
2. No apagar el equipo (preservar evidencia en memoria RAM)
3. Bloquear la dirección IP de origen en el firewall perimetral
4. Notificar a los usuarios del área afectada para que dejen de usar los sistemas impactados

**Para incidentes que involucren exfiltración de datos:**
1. Bloquear el destino de la exfiltración (IP, dominio, cuenta cloud) en el firewall
2. Revocar accesos del usuario involucrado (si es amenaza interna)
3. Preservar los logs de red y sistema sin modificación

### 7.2. Contención de mediano plazo (30 min – 4 horas)

1. Aplicar parches de emergencia si la vulnerabilidad es conocida
2. Implementar reglas temporales de firewall para reducir la superficie de ataque
3. Activar monitoreo intensivo en los sistemas adyacentes al incidente
4. Si corresponde: activar el sitio de recuperación ante desastres (DR en AWS) según PSI-005

---

## 8. FASE 3 — ANÁLISIS FORENSE

### 8.1. Preservación de evidencia

**Antes de cualquier acción de limpieza, preservar:**
- Imagen forense del disco del equipo comprometido (si aplica)
- Volcado de memoria RAM (si el equipo no fue apagado)
- Logs de sistema, aplicación y seguridad del período afectado
- Logs de firewall, VPN y Active Directory
- Capturas de tráfico de red (pcap) si el sistema de monitoreo lo permite

**Cadena de custodia:** Todo material de evidencia debe ser documentado con fecha, hora, responsable y método de recolección.

### 8.2. Análisis

| Pregunta a responder | Método |
|---------------------|--------|
| ¿Cuál fue el vector de entrada? | Revisión de logs de autenticación, correo, navegación |
| ¿Qué sistemas fueron afectados? | Correlación de logs en SIEM |
| ¿Qué datos fueron accedidos o exfiltrados? | Logs de acceso a base de datos y archivos |
| ¿Cuánto tiempo estuvo activo el atacante? | Línea de tiempo de eventos (timeline) |
| ¿Hay indicadores de compromiso adicionales (IoC)? | Análisis de malware, revisión de otros sistemas |

---

## 9. FASE 4 — ERRADICACIÓN

1. Eliminar el malware o artefacto malicioso identificado con herramientas EDR
2. Cerrar la vulnerabilidad explotada (parche, cambio de configuración, corrección de código)
3. Eliminar cuentas o backdoors creados por el atacante
4. Restaurar las configuraciones de seguridad a estado conocido como bueno
5. Cambiar todas las contraseñas de cuentas que pudieron haber sido expuestas
6. Regenerar todos los secretos y API keys potencialmente comprometidos y registrarlos en la bóveda

---

## 10. FASE 5 — RECUPERACIÓN

1. Restaurar los sistemas afectados desde el último backup íntegro verificado (según PSI-005)
2. Validar la integridad de los datos restaurados antes de volver a producción
3. Implementar monitoreo intensivo durante los primeros **7 días** post-recuperación
4. Retornar a operación normal gradualmente, validando funcionalidad por sistema
5. Confirmar con los propietarios de activos que los sistemas operan correctamente

---

## 11. COMUNICACIONES

### 11.1. Comunicación interna

| Destinatario | Cuándo | Responsable |
|-------------|--------|-------------|
| CISO | Inmediato (Nivel 3–4) | Coordinador de Seguridad |
| CEO | < 1 hora (Nivel 4) | CISO |
| Comité de Seguridad | < 24 horas (Nivel 3–4) | CISO |
| Usuarios afectados | Según necesidad operacional | Coordinador de Seguridad |
| Jefes de área afectada | < 2 horas (Nivel 3–4) | CISO |

### 11.2. Comunicación externa y obligaciones regulatorias

| Situación | Acción | Plazo | Responsable |
|-----------|--------|-------|-------------|
| Brecha de datos personales (Ley 19.628) | Evaluar notificación a la autoridad competente | ≤ 72 horas desde detección | CISO + Asesor Legal |
| Brecha de datos clínicos de pacientes (Ley 20.584) | Notificar a pacientes afectados | Según instrucción de autoridad | CISO + Asesor Legal |
| Incidente con impacto en terceros (proveedores, clientes) | Notificar al proveedor / cliente | ≤ 24 horas | CISO |
| Comunicación con medios | Solo por el CEO | Coordinado con CISO | CEO |

**Plantilla de notificación a pacientes** (ver PSI-004, sección de Comunicación).

---

## 12. FASE 6 — LECCIONES APRENDIDAS

**Reunión post-incidente:** A realizarse dentro de los **5 a 10 días hábiles** siguientes al cierre del incidente.

**Participantes:** CISO, Coordinador de Seguridad, Equipo de Seguridad Técnica, Propietarios de Activos afectados.

**Agenda mínima:**
1. Revisión de la línea de tiempo del incidente
2. Causa raíz identificada
3. Efectividad de la respuesta (¿se siguieron los tiempos definidos?)
4. Mejoras a implementar en controles, procedimientos o capacitación
5. Actualización del registro de lecciones aprendidas

**Entregable:** Informe post-incidente (ver sección 13) presentado al Comité de Seguridad en la siguiente reunión.

---

## 13. DOCUMENTACIÓN REQUERIDA

Todo incidente Nivel 2 o superior requiere los siguientes registros:

| Documento | Contenido mínimo | Plazo |
|-----------|-----------------|-------|
| Ticket de incidente (FORM-007) | ID, clasificación, descripción, línea de tiempo | Abrir al detectar |
| Log de acciones tomadas | Cada acción con fecha, hora y responsable | Durante la respuesta |
| Informe forense (si aplica) | Evidencia recolectada, cadena de custodia, análisis | ≤ 5 días post-cierre |
| Informe post-incidente | Causa raíz, impacto, lecciones aprendidas, mejoras | ≤ 10 días post-cierre |

**Retención:** 5 años (incidentes Nivel 1–2) / 7 años (incidentes Nivel 3–4 con datos clínicos).

---

## 14. INDICADORES DE DESEMPEÑO (KPIs)

| Indicador | Meta |
|-----------|------|
| Tiempo medio de detección (MTTD) | < 4 horas |
| Tiempo de contención inicial (Nivel 3–4) | < 30 minutos |
| Tiempo de notificación al CISO (Nivel 3–4) | < 15 minutos |
| Tiempo medio de recuperación (MTTR) | < 24 horas |
| Incidentes con informe post-incidente completado | 100% (Nivel 2+) |
| Simulacros realizados según plan | 4 por año (trimestral) |

---

## 15. REVISIÓN

Este procedimiento será revisado anualmente o después de cada incidente Nivel 3 o superior.

**Próxima revisión:** Junio 2027

---

**Aprobado por:**

**Firma:** ___________________________  
**Nombre:** Rodrigo Vásquez Herrera  
**Cargo:** Chief Information Security Officer (CISO)  
**Fecha:** 2 de junio de 2026

---

**FIN DEL DOCUMENTO**
