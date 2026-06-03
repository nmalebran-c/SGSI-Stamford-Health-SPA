# INFORME DE AUDITORÍA INTERNA DEL SGSI
## Stamford Health and Solution SpA

---

**Código:** AUD-002  
**Versión:** 1.0  
**Fecha de emisión:** 30 de octubre de 2026  
**Auditor Líder:** Coordinador de Seguridad  
**Período auditado:** Enero – Octubre 2026  
**Fase:** Semana 4 — Auditoría  
**Clasificación:** CONFIDENCIAL - USO INTERNO  
**Referencia:** ISO/IEC 27001:2022 — Cláusula 9.2

---

## 1. RESUMEN EJECUTIVO

Se realizó la auditoría interna del SGSI de Stamford Health and Solution SpA entre el 13 y el 22 de octubre de 2026, conforme al plan AUD-001. El SGSI presenta un **alto grado de madurez y conformidad** con ISO/IEC 27001:2022. Se identificaron hallazgos que deben cerrarse antes de la auditoría externa de certificación.

### Resultado global

| Tipo de hallazgo | Cantidad |
|------------------|---------|
| No Conformidades Mayores (NC-M) | **1** |
| No Conformidades Menores (NC-m) | **4** |
| Observaciones (OBS) | **6** |
| Conformidades destacadas | 8 |

**Conclusión:** El SGSI está **apto para avanzar a auditoría externa** una vez cerrada la NC Mayor y las NC Menores. Nivel de conformidad general estimado: **88%**.

---

## 2. RESULTADOS POR CLÁUSULA ISO 27001

### Cláusula 4 — Contexto de la Organización
**Resultado:** ✅ Conforme  
El alcance del SGSI está documentado en PSI-001. Las partes interesadas (pacientes, médicos, reguladores) están identificadas. Contexto interno y externo analizado.

### Cláusula 5 — Liderazgo
**Resultado:** ✅ Conforme  
La Dirección demuestra compromiso mediante la aprobación de PSI-001 y la asignación de presupuesto ($75M CLP). Roles y responsabilidades definidos en ORG-001. Política de seguridad comunicada.

### Cláusula 6 — Planificación
**Resultado:** ⚠️ NC Menor (NC-m-01)  
La evaluación de riesgos (Matriz de Riesgos) es robusta. Sin embargo, **no existe una Declaración de Aplicabilidad (SoA) formal y firmada** que documente la inclusión/exclusión de cada control del Anexo A con su justificación.

### Cláusula 7 — Soporte
**Resultado:** ⚠️ NC Menor (NC-m-02)  
La capacitación está bien gestionada (IMPL-004, 100% empleados). Sin embargo, **52 médicos externos (20.8%) no han completado el Módulo 6** obligatorio antes de tener acceso activo a HCE. Riesgo de cumplimiento con Ley 20.584.

### Cláusula 8 — Operación
**Resultado:** ✅ Conforme  
Los procesos operacionales (PROC-003, PROC-004, PROC-005) se ejecutan según lo documentado. Evidencia de gestión de cambios (CAB), gestión de vulnerabilidades y respuesta a incidentes verificada.

### Cláusula 9 — Evaluación del Desempeño
**Resultado:** ⚠️ NC Menor (NC-m-03)  
Los KPIs se miden y reportan correctamente. Sin embargo, **la primera Revisión por la Dirección formal aún no se había ejecutado** al momento de la auditoría (programada para 15/11/2026). Es requisito de la cláusula 9.3.

### Cláusula 10 — Mejora
**Resultado:** ✅ Conforme  
Existe evidencia de mejora continua: actualización de PSI-002 a v1.1, actualización de PROC-005 tras simulacro, lecciones aprendidas documentadas.

---

## 3. HALLAZGOS DETALLADOS

### 🔴 NC-M-01 — No Conformidad Mayor
**Control afectado:** ISO 27001 Cláusula 8.1 / Control 8.16 (Monitoreo)  
**Hallazgo:** El SIEM registra eventos de seguridad, pero **no existe evidencia de revisión documentada y sistemática de las alertas de seguridad fuera del horario laboral**. Durante el muestreo se encontraron 3 alertas de severidad media generadas en fin de semana sin registro de revisión hasta el lunes siguiente (retraso de hasta 60 horas).  
**Impacto:** Un incidente real fuera de horario podría no detectarse oportunamente, comprometiendo el MTTD declarado (< 4 horas).  
**Requisito incumplido:** PSI-002 §10.1 establece alertas en tiempo real; no se cumple el monitoreo continuo efectivo.

### 🟡 NC-m-01 — Declaración de Aplicabilidad (SoA)
**Hallazgo:** No existe SoA formal firmada. El mapeo ISO existe pero no constituye una SoA conforme a ISO 27001 §6.1.3 d).  
**Impacto:** Requisito obligatorio para la certificación.

### 🟡 NC-m-02 — Capacitación de médicos externos incompleta
**Hallazgo:** 52 de 250 médicos externos no completaron el Módulo 6 (Ley 20.584).  
**Impacto:** Riesgo de incumplimiento legal; acceso a HCE sin capacitación verificada.

### 🟡 NC-m-03 — Revisión por la Dirección pendiente
**Hallazgo:** No se había realizado la primera Revisión por la Dirección formal.  
**Impacto:** Requisito obligatorio ISO 27001 §9.3.

### 🟡 NC-m-04 — Acuerdos de confidencialidad de proveedores
**Hallazgo:** 2 de 8 proveedores clasificados como "Alto" no tienen NDA actualizado en el expediente, conforme exige PSI-009 §5.3.  
**Impacto:** Brecha contractual en gestión de terceros.

---

## 4. OBSERVACIONES (Oportunidades de Mejora)

| ID | Observación | Recomendación |
|----|-------------|---------------|
| OBS-01 | La CMDB cubre tipos de activos pero no todas las instancias individuales | Completar inventario a nivel de instancia para Q1 2027 |
| OBS-02 | Tasa de reporte de phishing (71.8%) bajo la meta (85%) | Reforzar capacitación y campañas más frecuentes |
| OBS-03 | El PAM se implementó en Q3 pero lleva poco tiempo en operación | Acumular más evidencia de uso antes de la externa |
| OBS-04 | Las pruebas de restauración cubren sistemas críticos pero no todos los Nivel 2 | Ampliar alcance de pruebas de restauración |
| OBS-05 | Los logs se retienen correctamente pero falta documentar el proceso de su revisión periódica | Crear procedimiento formal de revisión de logs |
| OBS-06 | No existe métrica formal de tiempo de aplicación de parches | Agregar KPI de cumplimiento de SLA de parcheo |

---

## 5. CONFORMIDADES DESTACADAS

1. ✅ **MFA al 100%** en los 6 sistemas críticos — control 8.5 ejemplar
2. ✅ **Gestión de incidentes madura** — MTTD 1.8h, MTTR 6.4h, muy por debajo de objetivos
3. ✅ **Cifrado integral** — BitLocker 100% endpoints, SSE-KMS en S3, TLS 1.3
4. ✅ **Bóveda de contraseñas** con cobertura total de cuentas privilegiadas
5. ✅ **Backups verificados** con pruebas de restauración reales y RTO/RPO cumplidos
6. ✅ **Segmentación de red** con 7 VLANs y default deny
7. ✅ **Capacitación de empleados** al 100% con evaluaciones
8. ✅ **Compromiso visible de la Dirección** con presupuesto y recursos asignados

---

## 6. CONCLUSIÓN Y RECOMENDACIÓN

El SGSI de Stamford Health and Solution SpA demuestra un nivel de madurez sólido y un compromiso organizacional genuino con la seguridad de la información. Las no conformidades identificadas son **cerrables en el corto plazo** y no representan fallas estructurales del sistema.

**Recomendación del Auditor Líder:**
> Proceder con el Plan de Acción Correctiva (AUD-003), cerrar la NC Mayor y las 4 NC Menores antes del **30 de noviembre de 2026**, y avanzar a la auditoría externa de certificación en diciembre de 2026.

---

**Auditor Líder:**

**Firma:** ___________________________  
**Nombre:** [Coordinador de Seguridad]  
**Fecha:** 30 de octubre de 2026

**Recibido por el CISO:**

**Firma:** ___________________________  
**Nombre:** Rodrigo Vásquez Herrera  
**Fecha:** 30 de octubre de 2026

---

**FIN DEL DOCUMENTO**
