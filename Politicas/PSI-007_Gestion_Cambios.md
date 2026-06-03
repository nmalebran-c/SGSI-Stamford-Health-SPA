# POLÍTICA DE GESTIÓN DE CAMBIOS
## Stamford Health and Solution SpA

---

**Código:** PSI-007  
**Versión:** 1.0  
**Fecha de aprobación:** 2 de junio de 2026  
**Aprobado por:** Comité de Seguridad de la Información  
**Propietario:** CTO  
**Clasificación:** CONFIDENCIAL - USO INTERNO  
**Controles ISO 27002:2022:** 8.9 (Gestión de Configuración), 8.32 (Gestión de Cambios)

---

## 1. PROPÓSITO

Establecer los criterios para gestionar los cambios en la infraestructura tecnológica, sistemas de información y aplicaciones de Stamford Health and Solution SpA, minimizando el riesgo de interrupciones operacionales, brechas de seguridad y pérdida de datos derivados de cambios no controlados.

---

## 2. ALCANCE

Esta política aplica a todo cambio que afecte:
- Servidores físicos y virtuales (SRV-001 a SRV-005)
- Infraestructura AWS (EC2, RDS, S3, IAM, VPC)
- Aplicaciones críticas (TechHealth Platform, HCE, Portal Médico)
- Configuraciones de red, firewall y VPN
- Active Directory y servicios de autenticación
- Código fuente desplegado en producción
- Bases de datos de producción

---

## 3. CLASIFICACIÓN DE CAMBIOS

### 3.1. Cambio Estándar (Tipo 1)
- Cambios de bajo riesgo, repetitivos, con procedimiento documentado y probado
- **Ejemplos:** Actualización de antivirus, renovación de certificados, parches de seguridad rutinarios
- **Aprobación:** Administrador de Sistemas
- **Plazo:** Ejecutable en cualquier momento dentro de ventana de cambios

### 3.2. Cambio Normal (Tipo 2)
- Cambios de riesgo medio o alto que requieren planificación y aprobación formal
- **Ejemplos:** Actualización de versión de aplicación, cambio de configuración de firewall, migración de base de datos
- **Aprobación:** CAB (Change Advisory Board)
- **Plazo:** Mínimo 5 días hábiles de anticipación para revisión

### 3.3. Cambio de Emergencia (Tipo 3)
- Cambios urgentes para remediar un incidente activo o vulnerabilidad crítica explotada
- **Ejemplos:** Parche de emergencia por vulnerabilidad 0-day, bloqueo de IP ante ataque activo
- **Aprobación:** CISO + CTO (verbal, documentación posterior en 24 horas)
- **Plazo:** Inmediato; revisión post-implementación obligatoria

---

## 4. CHANGE ADVISORY BOARD (CAB)

El CAB es el órgano responsable de revisar y aprobar los cambios Tipo 2.

**Composición:**
| Rol | Participación |
|-----|--------------|
| CTO | Presidente del CAB |
| CISO | Evaluación de impacto en seguridad |
| Administrador de Sistemas | Factibilidad técnica |
| DBA | Cambios que afecten bases de datos |
| Propietario del Activo afectado | Impacto en el negocio |

**Frecuencia de reunión:** Semanal (martes 10:00). Sesiones extraordinarias para cambios urgentes.

---

## 5. PROCESO DE GESTIÓN DE CAMBIOS

### 5.1. Solicitud
1. El solicitante documenta el cambio con: descripción, justificación, sistemas afectados, riesgos identificados y plan de rollback
2. Clasifica el cambio (Tipo 1, 2 o 3)
3. Envía solicitud al CAB con mínimo 5 días hábiles de anticipación (Tipo 2)

### 5.2. Evaluación de Impacto en Seguridad
El CISO evalúa obligatoriamente el impacto de seguridad de todo cambio Tipo 2 y 3:
- ¿Introduce nuevas superficies de ataque?
- ¿Modifica controles de acceso existentes?
- ¿Afecta la confidencialidad o integridad de datos de pacientes?
- ¿Requiere apertura de puertos o reglas de firewall?

### 5.3. Aprobación
- **Tipo 1:** Administrador de Sistemas registra y ejecuta
- **Tipo 2:** CAB aprueba o rechaza con acta de reunión
- **Tipo 3:** CISO + CTO aprueban verbalmente; documentación en ≤ 24 horas

### 5.4. Implementación
- Todo cambio Tipo 2 se implementa en la **ventana de cambios autorizada**
- Ventana estándar: **sábado 22:00 – domingo 06:00**
- Ventana extendida (por excepción): previa notificación a usuarios afectados con 48 horas
- El responsable técnico debe estar disponible durante toda la ventana
- Se ejecuta el plan de pruebas post-implementación antes de considerar el cambio exitoso

### 5.5. Plan de Rollback
Todo cambio Tipo 2 debe incluir un plan de rollback documentado que especifique:
- Criterios para activar el rollback (qué falla lo dispara)
- Pasos técnicos para revertir el cambio
- Tiempo estimado de rollback
- Responsable de ejecutarlo

### 5.6. Cierre
1. El responsable confirma el éxito o reporta el rollback
2. Se registra el resultado en el registro de cambios
3. Para cambios de emergencia: revisión post-implementación en reunión del CAB siguiente

---

## 6. VENTANAS DE CAMBIO

| Tipo de Sistema | Ventana Estándar | Ventana de Emergencia |
|----------------|-----------------|----------------------|
| Sistemas Nivel 3 (HCE, AWS producción) | Sábado 22:00 – Domingo 06:00 | Cualquier momento con aprobación CISO+CTO |
| Sistemas Nivel 2 (TechHealth, M365) | Sábado 22:00 – Domingo 06:00 | Cualquier momento con aprobación CAB |
| Sistemas Nivel 1 (correo, herramientas) | Lunes a viernes 19:00–22:00 | Horario laboral con aprobación Administrador |

---

## 7. GESTIÓN DE CONFIGURACIÓN (CMDB)

- Stamford Health mantendrá una Base de Datos de Gestión de Configuración (CMDB) con el estado actualizado de todos los activos de Nivel 2 y 3
- La CMDB se actualiza obligatoriamente después de cada cambio aprobado
- El CTO es responsable de la integridad de la CMDB
- Auditoría de la CMDB: semestral

---

## 8. AMBIENTES DE DESPLIEGUE

Todo cambio en código o configuración de sistemas Nivel 2 y 3 debe seguir el flujo:

```
Desarrollo → QA/Testing → Pre-producción → Producción
```

- **PROHIBIDO** desplegar directamente a producción sin pasar por QA
- Los ambientes de desarrollo y QA no deben contener datos reales de pacientes
- El paso a producción requiere aprobación del propietario del activo

---

## 9. RESPONSABILIDADES

| Rol | Responsabilidad |
|-----|----------------|
| **CTO** | Presidir el CAB, aprobar la estrategia de gestión de cambios |
| **CISO** | Evaluar impacto en seguridad, aprobar cambios de emergencia |
| **Administradores de Sistemas** | Documentar y ejecutar cambios, actualizar CMDB |
| **DBA** | Gestionar cambios en bases de datos de producción |
| **Coordinador de Seguridad** | Auditar el proceso de cambios trimestralmente |

---

## 10. MÉTRICAS

| Indicador | Meta |
|-----------|------|
| Cambios con rollback ejecutado / total cambios | < 5% |
| Cambios Tipo 2 sin aprobación CAB | 0 |
| Tiempo promedio de aprobación CAB | ≤ 5 días hábiles |
| Incidentes causados por cambios no controlados | 0 |

---

## 11. SANCIONES

- Desplegar un cambio en producción sin aprobación: **Amonestación escrita + revisión disciplinaria**
- Reincidencia: **Revocación de acceso a producción**

---

## 12. REFERENCIAS NORMATIVAS

- ISO/IEC 27002:2022 — Control 8.9, 8.32
- ITIL v4 — Change Enablement Practice

---

## 13. REVISIÓN

Anual o tras cualquier incidente causado por un cambio no controlado.

**Próxima revisión:** Junio 2027

---

**Aprobado por:**

**Firma:** ___________________________  
**Nombre:** Rodrigo Vásquez Herrera  
**Cargo:** CISO  
**Fecha:** 2 de junio de 2026

---

**FIN DEL DOCUMENTO**
