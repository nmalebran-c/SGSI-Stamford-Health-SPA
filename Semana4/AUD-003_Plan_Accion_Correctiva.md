# PLAN DE ACCIÓN CORRECTIVA
## Stamford Health and Solution SpA

---

**Código:** AUD-003  
**Versión:** 1.0  
**Fecha:** 7 de noviembre de 2026  
**Responsable:** CISO — Rodrigo Vásquez Herrera  
**Fase:** Semana 4 — Auditoría  
**Clasificación:** CONFIDENCIAL - USO INTERNO  
**Referencia:** ISO/IEC 27001:2022 — Cláusula 10.2 (No Conformidad y Acción Correctiva)  
**Origen:** Informe de Auditoría Interna AUD-002

---

## 1. PROPÓSITO

Definir las acciones correctivas para cerrar las no conformidades identificadas en la auditoría interna (AUD-002), incluyendo análisis de causa raíz, acciones, responsables, plazos y verificación de eficacia, conforme a la cláusula 10.2 de ISO/IEC 27001:2022.

---

## 2. METODOLOGÍA

Para cada no conformidad se aplica:
1. **Corrección inmediata** (acción para contener el efecto)
2. **Análisis de causa raíz** (técnica de los 5 porqués)
3. **Acción correctiva** (elimina la causa para evitar recurrencia)
4. **Verificación de eficacia** (confirma que la acción funcionó)

---

## 3. ACCIONES CORRECTIVAS

### 🔴 NC-M-01 — Monitoreo de alertas fuera de horario

| Campo | Detalle |
|-------|---------|
| **Corrección inmediata** | Revisión retroactiva de todas las alertas pendientes de fin de semana; ninguna correspondía a incidente real |
| **Causa raíz** | No existía cobertura de monitoreo 24/7 ni proceso de escalamiento automático fuera de horario laboral |
| **Acción correctiva** | (1) Configurar escalamiento automático del SIEM vía SMS/llamada al analista de guardia para alertas de severidad media y alta; (2) Establecer turno de guardia rotativo del equipo de seguridad; (3) Documentar procedimiento de revisión de alertas en fin de semana |
| **Responsable** | CISO + Equipo de Seguridad Técnica |
| **Plazo** | 25/11/2026 |
| **Verificación de eficacia** | Prueba de alerta simulada en fin de semana con medición de tiempo de respuesta (objetivo < 1 hora) |
| **Estado** | ✅ Cerrada — 24/11/2026; prueba exitosa con respuesta en 22 min |

### 🟡 NC-m-01 — Declaración de Aplicabilidad (SoA)

| Campo | Detalle |
|-------|---------|
| **Corrección inmediata** | Iniciar elaboración de SoA basada en el mapeo ISO existente |
| **Causa raíz** | El equipo documentó el mapeo de controles pero desconocía que la SoA es un documento formal independiente obligatorio |
| **Acción correctiva** | Elaborar la Declaración de Aplicabilidad formal (SoA) con los 93 controles del Anexo A, su estado (aplica/no aplica), justificación e implementación; aprobar y firmar por el CISO |
| **Responsable** | Coordinador de Seguridad |
| **Plazo** | 20/11/2026 |
| **Verificación de eficacia** | SoA revisada por consultor externo; confirmada como conforme a ISO 27001 §6.1.3 |
| **Estado** | ✅ Cerrada — 18/11/2026; SoA v1.0 aprobada |

### 🟡 NC-m-02 — Capacitación de médicos externos

| Campo | Detalle |
|-------|---------|
| **Corrección inmediata** | Suspender el acceso a HCE de los 52 médicos sin capacitación hasta que la completen |
| **Causa raíz** | No existía un control técnico que bloqueara el acceso a HCE sin haber completado el Módulo 6 |
| **Acción correctiva** | (1) Campaña de capacitación dirigida a los 52 médicos; (2) Implementar control técnico que vincule el acceso a HCE con la finalización del Módulo 6 en el LMS |
| **Responsable** | Coordinador de Seguridad + Jefe de Área Clínica |
| **Plazo** | 28/11/2026 |
| **Verificación de eficacia** | 100% de médicos con acceso a HCE tienen Módulo 6 completado; control técnico probado |
| **Estado** | ✅ Cerrada — 27/11/2026; 250/250 médicos capacitados |

### 🟡 NC-m-03 — Revisión por la Dirección

| Campo | Detalle |
|-------|---------|
| **Corrección inmediata** | Convocar formalmente la Revisión por la Dirección |
| **Causa raíz** | La primera revisión se programó para noviembre; el calendario anual no contemplaba una revisión más temprana |
| **Acción correctiva** | Ejecutar la Revisión por la Dirección (AUD-004) y establecer en el SGSI un calendario fijo de revisiones semestrales |
| **Responsable** | CISO + Comité de Seguridad |
| **Plazo** | 15/11/2026 |
| **Verificación de eficacia** | Acta de Revisión por la Dirección firmada (AUD-004) |
| **Estado** | ✅ Cerrada — 15/11/2026; acta AUD-004 emitida |

### 🟡 NC-m-04 — NDA de proveedores

| Campo | Detalle |
|-------|---------|
| **Corrección inmediata** | Solicitar firma de NDA a los 2 proveedores pendientes |
| **Causa raíz** | El registro de proveedores no tenía alertas de vencimiento de NDA |
| **Acción correctiva** | (1) Obtener NDA firmados de ambos proveedores; (2) Agregar alertas de vencimiento de NDA al Registro de Proveedores (PSI-009 §11) |
| **Responsable** | Coordinador de Seguridad + Asesor Legal |
| **Plazo** | 22/11/2026 |
| **Verificación de eficacia** | 8/8 proveedores Alto y Crítico con NDA vigente en expediente |
| **Estado** | ✅ Cerrada — 21/11/2026 |

---

## 4. SEGUIMIENTO DE OBSERVACIONES

Las observaciones (OBS-01 a OBS-06) no son obligatorias para la certificación pero se incorporan al plan de mejora continua 2027:

| ID | Acción planificada | Plazo | Responsable |
|----|--------------------|-------|-------------|
| OBS-01 | Completar CMDB a nivel de instancia | Q1 2027 | CTO |
| OBS-02 | Campañas de phishing trimestrales | Continuo 2027 | Coordinador de Seguridad |
| OBS-03 | Acumular evidencia de uso de PAM | Q4 2026 | Equipo de Seguridad |
| OBS-04 | Ampliar pruebas de restauración a sistemas Nivel 2 | Q1 2027 | Administrador de Sistemas |
| OBS-05 | Procedimiento formal de revisión de logs | Q1 2027 | Coordinador de Seguridad |
| OBS-06 | KPI de cumplimiento de SLA de parcheo | Q1 2027 | Equipo de Seguridad |

---

## 5. RESUMEN DE CIERRE

| No Conformidad | Tipo | Plazo | Estado |
|---------------|------|-------|--------|
| NC-M-01 — Monitoreo 24/7 | Mayor | 25/11/2026 | ✅ Cerrada |
| NC-m-01 — SoA | Menor | 20/11/2026 | ✅ Cerrada |
| NC-m-02 — Capacitación médicos | Menor | 28/11/2026 | ✅ Cerrada |
| NC-m-03 — Revisión Dirección | Menor | 15/11/2026 | ✅ Cerrada |
| NC-m-04 — NDA proveedores | Menor | 22/11/2026 | ✅ Cerrada |

**Estado global:** 5/5 no conformidades cerradas al 28/11/2026 ✅  
**El SGSI está listo para la auditoría externa de certificación.**

---

**Aprobado por:**

**Firma:** ___________________________  
**Nombre:** Rodrigo Vásquez Herrera  
**Cargo:** CISO  
**Fecha:** 7 de noviembre de 2026

---

**FIN DEL DOCUMENTO**
