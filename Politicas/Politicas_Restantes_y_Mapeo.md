# POLÍTICAS COMPLEMENTARIAS Y MAPEO ISO 27002
## Stamford Health and Solution SpA

---

# POLÍTICA DE GESTIÓN DE INCIDENTES (PSI-004)

**Versión:** 1.0 | **Fecha:** 15/11/2025 | **Aprobado por:** Comité de Seguridad

## PROPÓSITO
Establecer proceso estructurado para detectar, responder y recuperarse de incidentes de seguridad.

## DEFINICIÓN DE INCIDENTE
Evento que comprometa o pueda comprometer confidencialidad, integridad o disponibilidad de información.

## CLASIFICACIÓN DE INCIDENTES

### Nivel 1 - BAJO
- Spam o phishing bloqueado automáticamente
- Malware detectado y bloqueado
- Violación menor a política (sin exposición de datos)
**Respuesta:** Equipo de Seguridad | Plazo: 24-48 horas

### Nivel 2 - MEDIO
- Intento de acceso no autorizado fallido
- Malware que requiere limpieza manual
- Pérdida menor de datos no sensibles
**Respuesta:** CSIRT | Plazo: 4-8 horas

### Nivel 3 - ALTO
- Acceso no autorizado exitoso a sistemas no críticos
- Denegación de servicio parcial
- Pérdida de datos sensibles limitada
**Respuesta:** CSIRT + CISO | Plazo: 2-4 horas

### Nivel 4 - CRÍTICO
- Ransomware activo
- Brecha de datos de pacientes
- Compromiso de sistemas críticos (HCE, BD principales)
- Denegación de servicio total
**Respuesta:** CSIRT + Comité Emergencia + CEO | Plazo: INMEDIATO

## PROCESO DE RESPUESTA (IRP)

### 1. DETECCIÓN Y ANÁLISIS (0-2h)
- Usuario/sistema detecta anomalía
- Reporte a incidentes@stamfordhealth.cl o +56 51 XXX XXXX
- Analista de Seguridad valida y clasifica
- Si es incidente real → Activar CSIRT

### 2. CONTENCIÓN (Inmediato)
**Contención Corta (minutos):**
- Aislar sistemas afectados de la red
- Deshabilitar cuentas comprometidas
- Bloquear direcciones IP maliciosas

**Contención Larga (horas/días):**
- Aplicar parches de emergencia
- Cambiar contraseñas comprometidas
- Implementar reglas de firewall temporales

### 3. ERRADICACIÓN (2-24h)
- Eliminar malware
- Cerrar vulnerabilidades explotadas
- Eliminar accesos no autorizados
- Restaurar configuraciones seguras

### 4. RECUPERACIÓN (variable)
- Restaurar sistemas desde backups seguros
- Validar integridad de datos
- Monitorear sistemas restaurados (7 días intensivo)
- Retornar a operación normal gradualmente

### 5. LECCIONES APRENDIDAS (5-10 días post-incidente)
- Reunión de revisión del CSIRT
- Documentar causa raíz
- Identificar mejoras
- Actualizar procedimientos
- Implementar controles preventivos

## COMUNICACIÓN

### Interna
- CISO notifica a CEO en incidentes Nivel 3-4 (inmediato)
- Comité de Seguridad informado en 24h (Nivel 3-4)
- Afectados notificados según necesidad

### Externa
- **Autoridades:** Notificar si hay obligación legal (ej: brecha de datos bajo Ley 19.628)
- **Pacientes:** Notificar en 72h si sus datos fueron comprometidos
- **Medios:** Solo vocero autorizado (CEO) puede hablar públicamente
- **Proveedores:** Notificar si incidente les afecta o involucra

### Plantilla de Notificación (Pacientes)
```
Estimado/a [Nombre]:

Le informamos que el [fecha], Stamford Health experimentó un incidente 
de seguridad que pudo haber afectado sus datos personales.

Datos potencialmente afectados: [especificar]
Acciones tomadas: [describir]
Pasos que debe seguir: [orientar]
Contacto: incidentes@stamfordhealth.cl | +56 51 XXX XXXX

Lamentamos profundamente este incidente.
```

## DOCUMENTACIÓN
Todo incidente requiere:
- Ticket de incidente (ID único)
- Línea de tiempo de eventos
- Evidencia forense (logs, capturas)
- Acciones tomadas
- Impacto evaluado
- Lecciones aprendidas

**Retención:** 5 años

## ROLES CSIRT
- **Líder:** CISO
- **Coordinador:** Coordinador de Seguridad
- **Analistas:** Equipo de Seguridad Técnica
- **Apoyo:** Administradores de Sistemas (según necesidad)
- **Legal:** Asesor Legal (incidentes con implicaciones legales)

## HERRAMIENTAS
- SIEM: Detección y correlación
- EDR: Respuesta en endpoints
- Forensics: Análisis forense digital
- Ticketing: Gestión de incidentes
- Comunicación: Canal dedicado (Teams)

## SIMULACROS
- Frecuencia: Trimestral
- Tipos: Tabletop exercises (teóricos) + Full simulation (técnicos)
- Escenarios: Ransomware, Phishing, DDoS, Brecha de datos

## MÉTRICAS
- Tiempo medio de detección (MTTD): Meta < 4 horas
- Tiempo medio de respuesta (MTTR): Meta < 24 horas
- Incidentes por mes
- % de incidentes por categoría
- Efectividad de controles

## REFERENCIAS
- ISO/IEC 27002:2022 - Control 5.24, 5.25, 5.26
- ISO 27035 - Gestión de incidentes de seguridad

---

# POLÍTICA DE BACKUP Y RECUPERACIÓN (PSI-005)

**Versión:** 1.0 | **Fecha:** 15/11/2025

## PROPÓSITO
Asegurar disponibilidad e integridad de información mediante respaldos regulares y procedimientos de recuperación probados.

## OBJETIVOS DE RECUPERACIÓN

| Sistema | RTO | RPO | Criticidad |
|---------|-----|-----|------------|
| HCE (APP-002) | 4 horas | 1 hora | CRÍTICA |
| BD Historias Clínicas | 4 horas | 1 hora | CRÍTICA |
| Portal Médico | 4 horas | 1 hora | CRÍTICA |
| Portal Pacientes | 8 horas | 4 horas | ALTA |
| Sistemas Financieros | 8 horas | 4 horas | ALTA |
| Email (M365) | 24 horas | 24 horas | MEDIA |
| Otros sistemas | 48 horas | 24 horas | MEDIA |

**RTO:** Recovery Time Objective (tiempo máximo de recuperación)  
**RPO:** Recovery Point Objective (máxima pérdida de datos aceptable)

## TIPOS DE BACKUP

### Backup Completo (Full)
- Frecuencia: Domingo (semanal)
- Duración: ~6 horas
- Almacenamiento: 4 semanas (mensual: 12 meses)

### Backup Incremental
- Frecuencia: Lunes-Sábado (diario)
- Duración: ~2 horas
- Almacenamiento: 30 días

### Backup Diferencial
- Frecuencia: Miércoles adicional
- Almacenamiento: 7 días

### Snapshots (Datos Críticos)
- Frecuencia: Cada hora (historias clínicas)
- Retención: 24 horas

## ALCANCE DE BACKUPS

**Sistemas incluidos:**
✅ Todas las bases de datos de producción
✅ Servidores de aplicaciones (SRV-001, SRV-002, SRV-004, SRV-005)
✅ Configuraciones de red y firewall
✅ Active Directory
✅ Repositorios de código fuente
✅ Documentación técnica
✅ Configuraciones de sistemas

**Datos incluidos:**
✅ Bases de datos completas
✅ Archivos de usuarios
✅ Imágenes médicas
✅ Logs de auditoría
✅ Configuraciones

## ALMACENAMIENTO

### Regla 3-2-1
- **3** copias de datos (producción + 2 backups)
- **2** medios diferentes (disco + cinta/nube)
- **1** copia offsite (AWS S3)

### Ubicaciones
1. **Primaria:** SRV-003 (Servidor de Respaldo - Data Center La Serena)
2. **Secundaria:** Cinta magnética (rotación mensual, almacenada en caja fuerte)
3. **Offsite:** AWS S3 (región diferente: São Paulo)

### Cifrado
- Backups cifrados con AES-256
- Claves gestionadas en KMS
- Contraseñas de backup en bóveda (Password Vault)

## RETENCIÓN

| Tipo de Dato | Retención | Justificación |
|--------------|-----------|---------------|
| Historias Clínicas | 15 años | Ley 20.584 (10 años) + margen |
| Datos Transaccionales | 7 años | Normativa tributaria |
| Logs de Auditoría | 3 años | ISO 27001 |
| Configuraciones | 1 año | Recuperación histórica |
| Datos Administrativos | 3 años | Necesidad operativa |

## PROCESO DE BACKUP

### Automatización
- Backups ejecutados por Veeam Backup & Replication
- Programación automática (no manual)
- Notificaciones de éxito/falla a equipo TI

### Monitoreo
- Revisión diaria de logs de backup
- Alertas automáticas si falla backup
- Dashboard de estado de backups
- Reporte semanal a CTO

### Validación
- Verificación automática de integridad (checksums)
- Prueba de restauración mensual (muestra aleatoria)
- Prueba completa de DR semestral

## PROCESO DE RESTAURACIÓN

### Solicitud
1. Usuario/Administrador identifica necesidad
2. Ticket de restauración con justificación
3. Aprobación:
   - Archivos individuales: Administrador de Sistemas
   - Bases de datos: DBA + Propietario del Activo
   - Sistemas completos: CTO + CISO

### Ejecución
1. Identificar backup apropiado (fecha/hora)
2. Validar integridad del backup
3. Restaurar en ambiente de prueba (si es factible)
4. Validar datos restaurados
5. Restaurar en producción
6. Verificar funcionalidad
7. Documentar en ticket

### Tiempos Estimados
- Archivo individual: < 1 hora
- Base de datos mediana (< 100GB): 2-4 horas
- Base de datos grande (> 500GB): 6-12 horas
- Servidor completo: 4-8 horas
- Sistema completo: 12-24 horas

## PLAN DE RECUPERACIÓN ANTE DESASTRES (DRP)

### Escenarios de Desastre
1. **Destrucción Data Center:** Terremoto, incendio
2. **Ransomware:** Cifrado de sistemas
3. **Falla catastrófica:** Hardware masivo
4. **Desastre natural regional:** Tsunami, corte eléctrico prolongado

### Sitio de Recuperación
- **Primario:** AWS (instancias EC2 + RDS)
- **Tiempo de activación:** 4-8 horas
- **Capacidad:** 80% de capacidad normal (escalable)

### Proceso DR
1. **Declaración de desastre:** CISO + CTO + CEO
2. **Activación de sitio DR:** Iniciar instancias AWS
3. **Restauración de datos:** Desde backup más reciente (AWS S3)
4. **Validación:** Pruebas funcionales de sistemas críticos
5. **Switchover DNS:** Redirigir tráfico a sitio DR
6. **Operación en DR:** Hasta recuperación de sitio primario
7. **Failback:** Retorno a data center principal cuando esté disponible

### Pruebas DR
- **Simulacro completo:** Anual (próximo: marzo 2026)
- **Prueba parcial:** Semestral
- **Revisión documental:** Trimestral

## RESPONSABILIDADES

| Rol | Responsabilidad |
|-----|-----------------|
| **CTO** | Aprobar estrategia de backup, asignar recursos |
| **Administradores Sistemas** | Configurar y ejecutar backups diarios |
| **DBA** | Backups de bases de datos, validación |
| **Coordinador Seguridad** | Monitorear cumplimiento, reportar métricas |
| **CISO** | Supervisar seguridad de backups, aprobar DRP |

## MÉTRICAS

- % de backups exitosos (meta: > 99%)
- Tiempo promedio de restauración por tipo
- % de pruebas de restauración exitosas (meta: 100%)
- Cobertura de backup (% de sistemas críticos con backup)

## REFERENCIAS
- ISO/IEC 27002:2022 - Control 5.29, 5.30, 8.13, 8.14
- Veeam Best Practices

---

# POLÍTICA DE DISPOSITIVOS EXTRAÍBLES (PSI-006)

**Versión:** 1.0 | **Fecha:** 15/11/2025

## PROPÓSITO
Regular el uso de dispositivos de almacenamiento extraíble para prevenir pérdida de datos, introducción de malware y exfiltración no autorizada.

## DISPOSITIVOS CUBIERTOS
- Memorias USB / Pendrives
- Discos duros externos / SSD
- Tarjetas SD / MicroSD
- Reproductores MP3 con almacenamiento
- Cámaras digitales
- Smartphones/tablets como almacenamiento masivo

## POLÍTICA GENERAL

### PROHIBIDO por Defecto
❌ Uso de dispositivos extraíbles personales en equipos corporativos
❌ Almacenar información CONFIDENCIAL o SENSIBLE en dispositivos extraíbles
❌ Conectar dispositivos desconocidos o encontrados
❌ Compartir dispositivos corporativos con terceros

### PERMITIDO con Controles
✅ Dispositivos corporativos aprobados y cifrados
✅ Uso temporal con autorización explícita
✅ Transferencia de archivos no sensibles (público/uso interno)

## DISPOSITIVOS CORPORATIVOS

### Características Obligatorias
- Cifrado por hardware (AES-256)
- Protección con contraseña
- Etiqueta de identificación corporativa
- Registro en inventario de activos

### Proceso de Asignación
1. Usuario solicita via ticket con justificación de negocio
2. Jefe directo aprueba necesidad
3. CISO aprueba (para datos sensibles)
4. TI entrega dispositivo corporativo cifrado
5. Usuario firma acta de responsabilidad
6. Dispositivo registrado en inventario

### Uso
- Solo para transferir datos entre sistemas corporativos
- Escaneo antivirus obligatorio antes y después de uso
- No dejar desatendido
- Reportar pérdida inmediatamente

### Devolución
- Al término de proyecto/necesidad
- Al cambiar de rol
- Al término de relación laboral

## DISPOSITIVOS PERSONALES

### Prohibición General
**PROHIBIDO** conectar USB personales a equipos corporativos.

### Excepciones
En casos excepcionales y temporales:
1. Solicitud escrita a CISO con justificación
2. Aprobación del CISO por escrito
3. Escaneo antivirus del dispositivo por TI
4. Uso supervisado
5. Duración máxima: 1 día
6. Solo para archivos no clasificados (PÚBLICO)

## CONTROLES TÉCNICOS

### Control de Puertos USB
- Configuración vía GPO (Group Policy)
- Solo dispositivos registrados permitidos
- Bloqueo por defecto de USB desconocidos
- Log de todos los dispositivos conectados

### Cifrado
- BitLocker To Go obligatorio
- Contraseña mínima 12 caracteres
- Sin copia de archivos sin cifrar

### Monitoreo
- Alertas de conexión de USB no autorizado
- Log de archivos copiados a/desde USB
- Auditoría mensual de uso de USB

## TIPOS DE INFORMACIÓN Y RESTRICCIONES

| Clasificación | USB Corporativo Cifrado | USB Personal | Servicios Cloud Personal |
|---------------|-------------------------|--------------|--------------------------|
| **PÚBLICA** | ✅ Permitido | ⚠️ Excepción temporal | ✅ Permitido |
| **USO INTERNO** | ✅ Permitido | ❌ Prohibido | ❌ Prohibido |
| **CONFIDENCIAL** | ⚠️ Solo con aprobación CISO | ❌ Prohibido | ❌ Prohibido |
| **DATOS PACIENTES** | ❌ Prohibido | ❌ Prohibido | ❌ Prohibido |

**NUNCA se permite almacenar historias clínicas o datos de pacientes en dispositivos extraíbles, ni siquiera corporativos cifrados.**

## ALTERNATIVAS SEGURAS

En lugar de USB, usar:
✅ Transferencia vía red corporativa (carpetas compartidas)
✅ Microsoft OneDrive corporativo
✅ Email corporativo (archivos < 25MB)
✅ Servidor de transferencia segura interna
✅ Portal de intercambio seguro con terceros

## DISPOSITIVOS MÉDICOS

### Equipamiento Médico con USB
- Evaluación de seguridad antes de conectar a red
- Segmentación de red (VLAN dedicada)
- Actualización de firmware regular
- Configuración segura

### Transferencia de Imágenes Médicas
- Preferir DICOM sobre red corporativa
- Si USB es necesario: Dispositivo corporativo cifrado dedicado
- Escaneo antivirus obligatorio
- Limpieza segura del USB después de transferencia

## LIMPIEZA Y DESTRUCCIÓN

### Limpieza de Datos
- Sobrescribir múltiple (DoD 5220.22-M)
- Herramienta: DBAN, Eraser, o utilidad corporativa
- No suficiente: Simple "delete" o formateo rápido

### Destrucción Física
- Dispositivos que contenían datos sensibles: Destrucción física
- Método: Trituración o desmagnetización
- Certificado de destrucción por proveedor autorizado
- Registro de destrucción (5 años)

## PÉRDIDA O ROBO

### Reporte Inmediato
1. Notificar a CISO inmediatamente (< 2 horas)
2. Ticket de incidente de seguridad
3. Denuncia policial (si contiene datos sensibles)

### Investigación
- Determinar qué información contenía
- Evaluar si estaba cifrado
- Clasificar incidente
- Notificar afectados si corresponde
- Lecciones aprendidas

### Sanciones
- Pérdida por negligencia: Amonestación + capacitación
- Reincidencia: Suspensión
- Robo por no seguir procedimientos: Responsabilidad del usuario

## CAPACITACIÓN
- Inducción: Política de USB incluida
- Anual: Recordatorio en capacitación general
- Ad-hoc: Comunicación después de incidente

## EXCEPCIONES
- Requieren aprobación por escrito del CISO
- Justificación de negocio clara
- Controles compensatorios definidos
- Temporales (máximo 30 días)
- Renovables con re-aprobación

## MÉTRICAS
- Número de USB corporativos en uso
- Intentos de conexión de USB no autorizados
- Incidentes relacionados con USB
- % de USB corporativos con cifrado activo

## REFERENCIAS
- ISO/IEC 27002:2022 - Control 8.9, 8.10
- NIST SP 800-111 - Guide to Storage Encryption

---

# MAPA DE CONTROLES ISO 27002:2022 vs POLÍTICAS

## CONTROL 5.1 - Políticas de Seguridad de la Información
**Estado:** ✅ Implementado  
**Políticas:** PSI-001 (Política Principal)  
**Descripción:** Política de seguridad aprobada por dirección, comunicada y revisada.

## CONTROL 5.7 - Inteligencia de Amenazas
**Estado:** ⚠️ Parcial (A desarrollar)  
**Políticas:** PSI-004 (Gestión de Incidentes - detección)  
**Pendiente:** Suscripción a feeds de threat intelligence

## CONTROL 5.15 - Control de Accesos
**Estado:** ✅ Implementado  
**Políticas:** PSI-002 (Control de Accesos)  
**Descripción:** Gestión completa de accesos con revisión trimestral

## CONTROL 5.16 - Gestión de Identidades
**Estado:** ✅ Implementado  
**Políticas:** PSI-002 (Control de Accesos - Secciones 4 y 5)  
**Descripción:** Ciclo de vida de identidades (alta, modificación, baja)

## CONTROL 5.17 - Información de Autenticación
**Estado:** ✅ Implementado  
**Políticas:** PSI-002 (Control de Accesos - Sección 5.2)  
**Descripción:** Política de contraseñas robusta, MFA obligatorio

## CONTROL 5.18 - Derechos de Acceso
**Estado:** ✅ Implementado  
**Políticas:** PSI-002 (Control de Accesos - Privilegio mínimo)  
**Descripción:** Asignación basada en roles, revisión trimestral

## CONTROL 5.19 - Seguridad de la Información en Relaciones con Proveedores
**Estado:** ⚠️ Parcial  
**Políticas:** PSI-002 (Control de Accesos - Sección 11.2)  
**Pendiente:** Política específica de terceros

## CONTROL 5.20 - Seguridad de la Información en Contratos con Proveedores
**Estado:** ⚠️ Parcial  
**Políticas:** ORG-001 (Gestión de Terceros)  
**Pendiente:** Plantillas de contratos con cláusulas

## CONTROL 5.24 - Planificación y Preparación de Gestión de Incidentes
**Estado:** ✅ Implementado  
**Políticas:** PSI-004 (Gestión de Incidentes)  
**Descripción:** IRP definido, CSIRT establecido, clasificación de incidentes

## CONTROL 5.25 - Evaluación y Decisión sobre Eventos de Seguridad
**Estado:** ✅ Implementado  
**Políticas:** PSI-004 (Gestión de Incidentes - Secciones 1-2)  
**Descripción:** Proceso de detección y clasificación

## CONTROL 5.26 - Respuesta a Incidentes
**Estado:** ✅ Implementado  
**Políticas:** PSI-004 (Gestión de Incidentes - Sección 2)  
**Descripción:** Proceso completo de respuesta en 5 fases

## CONTROL 5.29 - Seguridad de la Información Durante Interrupciones
**Estado:** ✅ Implementado  
**Políticas:** PSI-005 (Backup y Recuperación - DRP)  
**Descripción:** Plan de recuperación ante desastres definido

## CONTROL 5.30 - Preparación de las TIC para Continuidad del Negocio
**Estado:** ✅ Implementado  
**Políticas:** PSI-005 (Backup y Recuperación)  
**Descripción:** RTO/RPO definidos, sitio DR en AWS, pruebas anuales

## CONTROL 6.1 - Investigación (Screening) de Antecedentes
**Estado:** ⚠️ Parcial  
**Políticas:** ORG-001 (Roles - RRHH)  
**Pendiente:** Procedimiento formal

## CONTROL 6.2 - Términos y Condiciones de Empleo
**Estado:** ⚠️ Parcial  
**Políticas:** PSI-003 (Uso Aceptable - Sección 16)  
**Pendiente:** Cláusulas específicas en contratos

## CONTROL 6.3 - Concientización, Educación y Capacitación
**Estado:** ✅ Implementado  
**Políticas:** ORG-001 (Sección 6), PSI-001 (Sección 16)  
**Descripción:** Programa de capacitación definido por rol

## CONTROL 6.4 - Proceso Disciplinario
**Estado:** ✅ Implementado  
**Políticas:** PSI-002, PSI-003, PSI-006 (Sanciones)  
**Descripción:** Sanciones graduales definidas

## CONTROL 7.2 - Controles de Acceso Físico
**Estado:** ⚠️ Parcial  
**Políticas:** PSI-002 (Control de Acceso Físico - Sección 7)  
**Pendiente:** Implementar biometría

## CONTROL 7.4 - Monitoreo de Seguridad Física
**Estado:** ⚠️ Parcial  
**Políticas:** PSI-002 (CCTV mencionado)  
**Pendiente:** Ampliar cobertura CCTV

## CONTROL 8.1 - Dispositivos de Usuario Final
**Estado:** ✅ Implementado  
**Políticas:** PSI-003 (Uso Aceptable - Sección 4)  
**Descripción:** Política de equipos corporativos

## CONTROL 8.2 - Derechos de Acceso Privilegiados
**Estado:** ✅ Implementado  
**Políticas:** PSI-002 (Control de Accesos - Sección 6)  
**Descripción:** Gestión completa de accesos privilegiados

## CONTROL 8.3 - Restricción de Acceso a la Información
**Estado:** ✅ Implementado  
**Políticas:** PSI-002 (Principios - Sección 3)  
**Descripción:** Need-to-know, least privilege

## CONTROL 8.5 - Autenticación Segura
**Estado:** ✅ Implementado  
**Políticas:** PSI-002 (Control de Accesos - Sección 5.3)  
**Descripción:** MFA obligatorio para sistemas críticos

## CONTROL 8.8 - Gestión de Vulnerabilidades Técnicas
**Estado:** ⚠️ Parcial  
**Políticas:** ORG-001 (Equipo de Seguridad)  
**Pendiente:** Procedimiento formal de gestión de vulnerabilidades

## CONTROL 8.9 - Gestión de Configuración
**Estado:** ⚠️ Parcial  
**Políticas:** PSI-007 (Gestión de Cambios - A desarrollar)  
**Pendiente:** CMDB y control de configuraciones

## CONTROL 8.10 - Eliminación de Información
**Estado:** ✅ Implementado  
**Políticas:** PSI-006 (Dispositivos Extraíbles - Sección 7)  
**Descripción:** Limpieza segura y destrucción certificada

## CONTROL 8.11 - Enmascaramiento de Datos
**Estado:** ⚠️ Pendiente  
**Políticas:** A desarrollar  
**Pendiente:** Procedimiento de enmascaramiento para ambientes no productivos

## CONTROL 8.13 - Respaldo de Información
**Estado:** ✅ Implementado  
**Políticas:** PSI-005 (Backup y Recuperación)  
**Descripción:** Estrategia 3-2-1, backups diarios, cifrados

## CONTROL 8.14 - Redundancia de Instalaciones de Procesamiento de Información
**Estado:** ⚠️ Parcial  
**Políticas:** PSI-005 (DRP con AWS)  
**Pendiente:** Implementar redundancia activa

## CONTROL 8.23 - Filtrado Web
**Estado:** ⚠️ Parcial  
**Políticas:** PSI-003 (Uso Aceptable - Sección 6.2)  
**Implementado:** Bloqueo de categorías
**Pendiente:** Solución DLP completa

## CONTROL 8.24 - Uso de Criptografía
**Estado:** ⚠️ Parcial  
**Políticas:** PSI-005 (Cifrado de backups), PSI-006 (Cifrado de USB)  
**Pendiente:** Política general de criptografía

---

## RESUMEN DE IMPLEMENTACIÓN

### ✅ Controles Implementados (15)
5.1, 5.15, 5.16, 5.17, 5.18, 5.24, 5.25, 5.26, 5.29, 5.30, 6.3, 6.4, 8.1, 8.2, 8.3, 8.5, 8.10, 8.13

### ⚠️ Controles Parciales (11)
5.7, 5.19, 5.20, 6.1, 6.2, 7.2, 7.4, 8.8, 8.9, 8.14, 8.23, 8.24

### ❌ Controles Pendientes (3)
8.11, Política de Terceros específica, Política de Criptografía

**Nivel de Implementación:** 60% completo (objetivo Q2 2026: 90%)

---

**FIN DEL DOCUMENTO**
