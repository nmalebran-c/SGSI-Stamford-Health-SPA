# FORMULARIO DE REGISTRO DE INCIDENTE DE SEGURIDAD
## Stamford Health and Solution SpA

---

**Código:** FORM-007  
**Versión:** 1.0  
**Fecha de aprobación:** 2 de junio de 2026  
**Asociado a:** PSI-004, PROC-005 §13  
**Clasificación:** CONFIDENCIAL - USO INTERNO

---

## SECCIÓN 1 — IDENTIFICACIÓN DEL INCIDENTE

| Campo | Datos |
|-------|-------|
| **ID del incidente** | INC-[año]-[correlativo] |
| **Fecha y hora de detección** | |
| **Fecha y hora de apertura del ticket** | |
| **Detectado por** | ☐ Sistema automático (SIEM/EDR) ☐ Usuario ☐ Proveedor ☐ Monitoreo externo |
| **Reportante** | |
| **Canal de reporte** | ☐ Correo seguridad@stamfordhealth.cl ☐ Extensión 911 ☐ Celular guardia ☐ Otro: ______ |

---

## SECCIÓN 2 — CLASIFICACIÓN INICIAL

| Campo | Datos |
|-------|-------|
| **Nivel de incidente** | ☐ Nivel 1 — Bajo ☐ Nivel 2 — Medio ☐ Nivel 3 — Alto ☐ Nivel 4 — Crítico |
| **Tipo de incidente** | ☐ Malware/Ransomware ☐ Acceso no autorizado ☐ Phishing ☐ DDoS ☐ Fuga de datos ☐ Compromiso de credenciales ☐ Vulnerabilidad explotada ☐ Incidente físico ☐ Otro: ______ |
| **¿Involucra datos de pacientes (HCE)?** | ☐ Sí ☐ No ☐ Desconocido |
| **¿Involucra datos personales (Ley 19.628)?** | ☐ Sí ☐ No ☐ Desconocido |
| **¿CSIRT activado?** | ☐ Sí — Hora de activación: _______ ☐ No |

---

## SECCIÓN 3 — DESCRIPCIÓN DEL INCIDENTE

**Descripción de los hechos observados:**

_______________________________________________
_______________________________________________
_______________________________________________

**Sistemas y activos involucrados:**

| Activo / Sistema | ID | Impacto observado |
|-----------------|-----|------------------|
| | | |
| | | |
| | | |

**Indicadores de Compromiso (IoC) identificados:**

| Tipo | Valor | Fuente |
|------|-------|--------|
| ☐ IP ☐ Dominio ☐ Hash ☐ Cuenta ☐ Otro | | |
| ☐ IP ☐ Dominio ☐ Hash ☐ Cuenta ☐ Otro | | |
| ☐ IP ☐ Dominio ☐ Hash ☐ Cuenta ☐ Otro | | |

---

## SECCIÓN 4 — LÍNEA DE TIEMPO

| Fecha y Hora | Evento | Responsable |
|-------------|--------|-------------|
| | Detección del incidente | |
| | Validación (real vs. falso positivo) | |
| | Clasificación y apertura de ticket | |
| | Notificación al CISO (si Nivel 3–4) | |
| | Activación del CSIRT (si aplica) | |
| | Inicio de contención | |
| | Fin de contención | |
| | Inicio de erradicación | |
| | Fin de erradicación | |
| | Inicio de recuperación | |
| | Sistemas restaurados a operación normal | |
| | Cierre del incidente | |

---

## SECCIÓN 5 — ACCIONES DE CONTENCIÓN

| Acción tomada | Responsable | Fecha y Hora | Resultado |
|--------------|------------|-------------|-----------|
| | | | ☐ Efectiva ☐ Parcial ☐ Sin efecto |
| | | | ☐ Efectiva ☐ Parcial ☐ Sin efecto |
| | | | ☐ Efectiva ☐ Parcial ☐ Sin efecto |

---

## SECCIÓN 6 — ERRADICACIÓN Y RECUPERACIÓN

**Causa raíz identificada:**

_______________________________________________
_______________________________________________

**Acciones de erradicación:**

| Acción | Responsable | Fecha |
|--------|------------|-------|
| | | |
| | | |

**Restauración desde backup:**

| ☐ Sí — Backup utilizado: ________________ Fecha del backup: ________________ | ☐ No fue necesario |

---

## SECCIÓN 7 — IMPACTO

| Dimensión | Detalle |
|-----------|---------|
| **Sistemas afectados** | |
| **Duración de la interrupción** | |
| **Datos comprometidos** | ☐ Sí (especificar abajo) ☐ No ☐ Desconocido |
| **Tipo y volumen de datos comprometidos** | |
| **Número de pacientes afectados (si aplica)** | |
| **Impacto económico estimado** | |
| **Impacto reputacional** | ☐ Alto ☐ Medio ☐ Bajo ☐ Sin impacto |

---

## SECCIÓN 8 — COMUNICACIONES

| Comunicación | Destinatario | Fecha y Hora | Responsable |
|-------------|-------------|-------------|-------------|
| Notificación al CISO | | | |
| Notificación al CEO | | | |
| Notificación al Comité de Seguridad | | | |
| Notificación a autoridad regulatoria (Ley 19.628) | | | |
| Notificación a pacientes afectados (Ley 20.584) | | | |
| Notificación a proveedor involucrado | | | |

**¿Se requiere notificación regulatoria?** ☐ Sí ☐ No ☐ En evaluación  
**Evaluación realizada por:** ___________________________  
**Fecha de evaluación:** ___________________________

---

## SECCIÓN 9 — EVIDENCIA FORENSE

| Evidencia recolectada | Formato | Ubicación de almacenamiento | Responsable de custodia |
|----------------------|---------|----------------------------|------------------------|
| | | | |
| | | | |
| | | | |

**¿Se preservó la cadena de custodia?** ☐ Sí ☐ No (indicar razón): _______________

---

## SECCIÓN 10 — CIERRE DEL INCIDENTE

| Campo | Datos |
|-------|-------|
| **Fecha y hora de cierre** | |
| **Estado final** | ☐ Resuelto ☐ Mitigado (riesgo residual aceptado) ☐ Transferido a otro proceso |
| **¿Requiere seguimiento post-cierre?** | ☐ Sí — Fecha de revisión: _________ ☐ No |
| **Closed by** | |

---

## SECCIÓN 11 — LECCIONES APRENDIDAS

*(Completar en reunión post-incidente, ≤ 10 días hábiles desde el cierre)*

**Fecha de reunión post-incidente:** ___________________________

**¿Qué se hizo bien?**

_______________________________________________

**¿Qué se puede mejorar?**

_______________________________________________

**Mejoras a implementar:**

| Mejora | Responsable | Plazo | Estado |
|--------|------------|-------|--------|
| | | | ☐ Pendiente ☐ En progreso ☐ Completado |
| | | | ☐ Pendiente ☐ En progreso ☐ Completado |
| | | | ☐ Pendiente ☐ En progreso ☐ Completado |

---

## NOTAS DE ARCHIVO

- **Retención:** 5 años (Nivel 1–2) / 7 años (Nivel 3–4 con datos clínicos)
- Archivar en: `/SGSI/Incidentes/[año]/INC-[año]-[correlativo]/`
- El informe post-incidente completo se adjunta como documento separado

---

**FIN DEL FORMULARIO**
