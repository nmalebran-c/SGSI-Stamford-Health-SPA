# ÍNDICE COMPLETO DE ENTREGABLES — PROYECTO SGSI
## Stamford Health and Solution SpA

---

**Proyecto:** Diseño, Implementación y Auditoría de un SGSI  
**Asignatura:** Ciberseguridad Avanzada  
**Equipo:** Miguel Carvajal, Cristóbal Aguirre, Emilio Maturana, Josué Bustos, Nicolás Malebrán  
**Docente:** Cristian Cubillos  
**Institución:** Universidad de La Serena  
**Periodo:** Noviembre 2025 — 2026

---

## ESTADO DEL PROYECTO

| Fase | Estado | Entregables |
|------|--------|-------------|
| **Semana 1:** Diagnóstico | ✅ Completo | Informe diagnóstico, Inventario 487 activos, Matriz 20 riesgos |
| **Semana 2:** Diseño SGSI | ✅ Completo | 9 políticas, 3 procedimientos, 7 formularios, estructura organizativa, mapeo ISO |
| **Semana 3:** Implementación | ✅ Completo | Plan de implementación, registro de controles, plan y registro de capacitación |
| **Semana 4:** Auditoría | ✅ Completo | Plan y informe de auditoría interna, acción correctiva, revisión por la dirección, certificación |

---

## SEMANA 1 — DIAGNÓSTICO INICIAL

| Documento | Descripción |
|-----------|-------------|
| [Informe_Diagnostico.md](Semana1/Informe_Diagnostico.md) | Diagnóstico completo: empresa, metodología, estado de controles, exposición financiera ($120M CLP/año), 14 recomendaciones |
| [Inventario_Activos.md](Semana1/Inventario_Activos.md) | 487 activos en 8 categorías, 16 activos críticos, propietario por activo |
| [Matriz_Riesgos.md](Semana1/Matriz_Riesgos.md) | 19 amenazas, 23 vulnerabilidades, 20 riesgos evaluados (3 críticos, 8 importantes), plan de tratamiento |

---

## SEMANA 2 — DISEÑO DEL SGSI

### Estructura Organizativa

| Documento | Código | Descripción |
|-----------|--------|-------------|
| [Estructura_Organizativa_SGSI.md](Semana2/Estructura_Organizativa_SGSI.md) | ORG-001 | Comité de Seguridad (9 miembros), 10 roles detallados, matriz RACI, programa de capacitación |
| [Semana2_Resumen_Ejecutivo.md](Semana2/Semana2_Resumen_Ejecutivo.md) | — | Resumen ejecutivo de la fase: presupuesto $75M CLP, cronograma Q1–Q4 2026, checklist de cumplimiento |

### Políticas de Seguridad

| Documento | Código | Controles ISO 27002 |
|-----------|--------|---------------------|
| [Politica_Seguridad_Informacion_Principal.md](Politicas/Politica_Seguridad_Informacion_Principal.md) | PSI-001 | 5.1, 5.2 |
| [Politica_Control_Accesos.md](Politicas/Politica_Control_Accesos.md) | PSI-002 v1.1 | 5.15, 5.16, 5.17, 5.18, 8.2, 8.3, 8.5 |
| [Politica_Uso_Aceptable.md](Politicas/Politica_Uso_Aceptable.md) | PSI-003 | 5.10, 5.19, 5.20, 8.23 |
| [Politicas_Restantes_y_Mapeo.md](Politicas/Politicas_Restantes_y_Mapeo.md) | PSI-004/005/006 | 5.24–5.26, 5.29, 5.30, 8.9, 8.10, 8.13, 8.14 |
| [PSI-007_Gestion_Cambios.md](Politicas/PSI-007_Gestion_Cambios.md) | PSI-007 | 8.9, 8.32 |
| [PSI-008_Criptografia.md](Politicas/PSI-008_Criptografia.md) | PSI-008 | 8.24 |
| [PSI-009_Gestion_Proveedores.md](Politicas/PSI-009_Gestion_Proveedores.md) | PSI-009 | 5.19, 5.20, 5.21, 5.22 |

### Procedimientos Operacionales

| Documento | Código | Descripción |
|-----------|--------|-------------|
| [PROC-003_Gestion_Accesos.md](Procedimientos/PROC-003_Gestion_Accesos.md) | PROC-003 | Alta, modificación, baja y revisión trimestral de accesos |
| [PROC-004_Gestion_Vulnerabilidades.md](Procedimientos/PROC-004_Gestion_Vulnerabilidades.md) | PROC-004 | Escaneo, clasificación CVSS, remediación y seguimiento |
| [PROC-005_Respuesta_Incidentes_Seguridad.md](Procedimientos/PROC-005_Respuesta_Incidentes_Seguridad.md) | PROC-005 | Respuesta a incidentes en 6 fases, KPIs, obligaciones regulatorias |

### Formularios

| Documento | Código | Descripción |
|-----------|--------|-------------|
| [FORM-001_Solicitud_Acceso.md](Formularios/FORM-001_Solicitud_Acceso.md) | FORM-001 | Alta, modificación y acceso temporal |
| [FORM-002_Revision_Accesos.md](Formularios/FORM-002_Revision_Accesos.md) | FORM-002 | Revisión y certificación trimestral |
| [FORM-003_Acta_Devolucion_Activos.md](Formularios/FORM-003_Acta_Devolucion_Activos.md) | FORM-003 | Devolución de activos en baja de usuario |
| [FORM-004_Excepcion_Politica.md](Formularios/FORM-004_Excepcion_Politica.md) | FORM-004 | Solicitud de excepción a política con controles compensatorios |
| [FORM-005_Registro_Cuentas_Servicio.md](Formularios/FORM-005_Registro_Cuentas_Servicio.md) | FORM-005 | Ciclo de vida de cuentas de servicio (svc-*) |
| [FORM-006_Acceso_Medico_Externo.md](Formularios/FORM-006_Acceso_Medico_Externo.md) | FORM-006 | Alta de médicos externos con verificación Ley 20.584 |
| [FORM-007_Registro_Incidente.md](Formularios/FORM-007_Registro_Incidente.md) | FORM-007 | Registro de incidente de seguridad con línea de tiempo |

### Mapeo de Controles ISO 27002:2022

| Estado | Controles | Cantidad |
|--------|-----------|---------|
| ✅ Implementados | 5.1, 5.15, 5.16, 5.17, 5.18, 5.24, 5.25, 5.26, 5.29, 5.30, 6.3, 6.4, 8.1, 8.2, 8.3, 8.5, 8.9, 8.10, 8.13, 8.24 | 20 |
| ⚠️ Parciales | 5.7, 5.19, 5.20, 5.21, 5.22, 6.1, 6.2, 7.2, 7.4, 8.8, 8.14, 8.23 | 12 |
| ❌ Pendientes | 8.11 (enmascaramiento de datos) | 1 |
| **Total evaluados** | | **93** |

---

## MÉTRICAS DEL PROYECTO

| Elemento | Cantidad |
|----------|---------|
| Activos inventariados | 487 (16 críticos) |
| Amenazas identificadas | 19 |
| Vulnerabilidades identificadas | 23 |
| Riesgos evaluados | 20 (3 críticos) |
| Políticas desarrolladas | 9 (PSI-001 a PSI-009) |
| Procedimientos | 3 (PROC-003, PROC-004, PROC-005) |
| Formularios | 7 (FORM-001 a FORM-007) |
| Controles ISO 27002 implementados | 20 / 93 (21%) |
| Exposición financiera inicial | $120M CLP/año |
| Exposición proyectada con controles | $48M CLP/año (−60%) |
| Presupuesto de implementación 2026 | $75M CLP |

---

## NORMATIVAS APLICADAS

| Norma / Ley | Aplicación en el proyecto |
|-------------|--------------------------|
| ISO/IEC 27001:2022 | Marco del SGSI — estructura y requisitos |
| ISO/IEC 27002:2022 | 93 controles evaluados, 20 implementados |
| ISO 27799:2016 | Controles específicos para sector salud |
| NIST Cybersecurity Framework | Marco de referencia complementario |
| Ley 19.628 | Protección de datos personales — aplicada en PSI-002 §17, PSI-009 |
| Ley 20.584 | Derechos y deberes de los pacientes — logs 7 años, acceso HCE restringido |
| Ley 21.459 | Marco de ciberseguridad — CSIRT, reporte de incidentes |

---

## OBJETIVOS ESTRATÉGICOS 2025–2026

| Objetivo | Meta | Plazo |
|----------|------|-------|
| Certificación ISO 27001:2022 | Obtener | Diciembre 2026 |
| Reducción de exposición al riesgo | 60% ($120M → $48M CLP) | Diciembre 2026 |
| Incidentes con pérdida de datos | Cero | Permanente |
| Cumplimiento legal Ley 19.628 y 20.584 | 100% | Junio 2026 |
| Disponibilidad sistemas críticos | ≥ 99.5% | Permanente |
| Personal capacitado en seguridad | 100% | Diciembre 2026 |

---

## VERIFICACIÓN POR FASE

### Semana 1 — Diagnóstico
- [x] Empresa ficticia definida (Stamford Health and Solution SpA)
- [x] 487 activos catalogados en 8 categorías, 16 críticos
- [x] 19 amenazas y 23 vulnerabilidades identificadas
- [x] 20 riesgos evaluados con metodología Probabilidad × Impacto
- [x] Plan de tratamiento con estimación de costos
- [x] Exposición financiera cuantificada ($120M CLP/año)
- [x] Análisis de cumplimiento Ley 19.628, 20.584, 21.459

### Semana 2 — Diseño del SGSI
- [x] PSI-001: Política Principal de Seguridad de la Información
- [x] Estructura organizativa: Comité de Seguridad, 10 roles, matriz RACI
- [x] PSI-002: Control de Accesos v1.1 (completa, con KPIs y normativa)
- [x] PSI-003: Uso Aceptable de Recursos
- [x] PSI-004: Gestión de Incidentes
- [x] PSI-005: Backup y Recuperación
- [x] PSI-006: Dispositivos Extraíbles
- [x] PSI-007: Gestión de Cambios
- [x] PSI-008: Criptografía
- [x] PSI-009: Gestión de Proveedores y Terceros
- [x] PROC-003: Gestión de Accesos (operacional)
- [x] PROC-004: Gestión de Vulnerabilidades
- [x] PROC-005: Respuesta a Incidentes (6 fases)
- [x] FORM-001 a FORM-007: Formularios del ciclo de vida de accesos e incidentes
- [x] Mapeo ISO 27002:2022 (93 controles evaluados)
- [x] Plan de implementación Q1–Q4 2026

### Semana 3 — Implementación
- [x] Plan de implementación detallado con hitos (IMPL-001)
- [x] Registro de implementación de controles (IMPL-002)
- [x] Plan de capacitación formal (IMPL-003)
- [x] Registro de capacitaciones ejecutadas (IMPL-004)
- [x] Resumen ejecutivo de la fase (IMPL-000)

### Semana 4 — Auditoría
- [x] Plan de auditoría interna (AUD-001)
- [x] Informe de auditoría interna (AUD-002)
- [x] Plan de acción correctiva (AUD-003)
- [x] Acta de revisión por la dirección (AUD-004)
- [x] Resumen ejecutivo y cierre del proyecto (AUD-000)

---

## SEMANA 3 — IMPLEMENTACIÓN

| Documento | Código | Descripción |
|-----------|--------|-------------|
| [Plan_Implementacion_2026.md](Semana3/Plan_Implementacion_2026.md) | IMPL-001 | Cronograma Q1–Q4 con hitos, responsables y costos |
| [Registro_Implementacion_Controles.md](Semana3/Registro_Implementacion_Controles.md) | IMPL-002 | Evidencia de 20 controles ISO implementados y verificados |
| [Plan_Capacitacion.md](Semana3/Plan_Capacitacion.md) | IMPL-003 | 6 módulos por audiencia, calendario y métricas |
| [Registro_Capacitaciones.md](Semana3/Registro_Capacitaciones.md) | IMPL-004 | Registro de ejecución H1 2026, simulacro y campaña de phishing |
| [Semana3_Resumen_Ejecutivo.md](Semana3/Semana3_Resumen_Ejecutivo.md) | IMPL-000 | Cierre H1 2026: KPIs, riesgos mitigados, presupuesto |

---

## SEMANA 4 — AUDITORÍA

| Documento | Código | Descripción |
|-----------|--------|-------------|
| [AUD-001_Plan_Auditoria_Interna.md](Semana4/AUD-001_Plan_Auditoria_Interna.md) | AUD-001 | Alcance, criterios, metodología y cronograma (ISO 27001 §9.2) |
| [AUD-002_Informe_Auditoria_Interna.md](Semana4/AUD-002_Informe_Auditoria_Interna.md) | AUD-002 | Hallazgos: 1 NC Mayor, 4 NC Menores, 6 observaciones |
| [AUD-003_Plan_Accion_Correctiva.md](Semana4/AUD-003_Plan_Accion_Correctiva.md) | AUD-003 | Causa raíz y cierre de las 5 no conformidades (ISO 27001 §10.2) |
| [AUD-004_Revision_por_la_Direccion.md](Semana4/AUD-004_Revision_por_la_Direccion.md) | AUD-004 | Acta de revisión por la dirección (ISO 27001 §9.3) |
| [Semana4_Resumen_Ejecutivo.md](Semana4/Semana4_Resumen_Ejecutivo.md) | AUD-000 | Cierre del proyecto: certificación ISO 27001:2022 obtenida |

---

**Versión del índice:** 3.0  
**Última actualización:** Diciembre 2026 — Proyecto completo (4 fases)

---

**FIN DEL ÍNDICE**
