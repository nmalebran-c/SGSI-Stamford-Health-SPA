# Sistema de Gestión de Seguridad de la Información
## Stamford Health and Solution SpA

> Proyecto académico de diseño, implementación y auditoría de un SGSI conforme a **ISO/IEC 27001:2022** para una empresa ficticia del sector salud.

---

## Descripción

**Stamford Health and Solution SpA** es una empresa ficticia de telemedicina ubicada en La Serena, Chile. Opera la plataforma TechHealth con 15.000 pacientes activos, 250 profesionales médicos asociados e infraestructura en AWS. Este repositorio contiene el diseño completo de su Sistema de Gestión de Seguridad de la Información (SGSI), desarrollado como proyecto de la asignatura **Ciberseguridad Avanzada** de la Universidad de La Serena.

---

## Estructura del Repositorio

```
SGSI-Stamford-Health-SPA/
│
├── Semana1/                          # Fase 1 — Diagnóstico Inicial
│   ├── Informe_Diagnostico.md        # Informe completo de diagnóstico
│   ├── Inventario_Activos.md         # 487 activos clasificados
│   └── Matriz_Riesgos.md             # 20 riesgos evaluados, 8 prioritarios
│
├── Semana2/                          # Fase 2 — Diseño del SGSI
│   ├── Estructura_Organizativa_SGSI.md   # Comité, roles y RACI
│   └── Semana2_Resumen_Ejecutivo.md      # Resumen ejecutivo de la fase
│
├── Politicas/                        # Políticas de Seguridad
│   ├── Politica_Seguridad_Informacion_Principal.md  # PSI-001
│   ├── Politica_Control_Accesos.md                  # PSI-002 v1.1
│   ├── Politica_Uso_Aceptable.md                    # PSI-003
│   └── Politicas_Restantes_y_Mapeo.md               # PSI-004/005/006 + ISO map
│
├── Procedimientos/                   # Procedimientos Operacionales
│   ├── PROC-003_Gestion_Accesos.md              # Procedimiento de gestión de accesos
│   └── PROC-005_Respuesta_Incidentes_Seguridad.md   # Respuesta a incidentes
│
├── Formularios/                      # Formularios del SGSI
│   ├── FORM-001_Solicitud_Acceso.md
│   ├── FORM-002_Revision_Accesos.md
│   ├── FORM-003_Acta_Devolucion_Activos.md
│   ├── FORM-004_Excepcion_Politica.md
│   ├── FORM-005_Registro_Cuentas_Servicio.md
│   └── FORM-006_Acceso_Medico_Externo.md
│
├── INDICE_COMPLETO_PROYECTO.md       # Índice general con estado de avance
└── README.md
```

---

## Documentos Principales

### Fase 1 — Diagnóstico

| Documento | Descripción |
|-----------|-------------|
| [Informe de Diagnóstico](Semana1/Informe_Diagnostico.md) | Diagnóstico completo: empresa, activos, amenazas, vulnerabilidades y riesgos |
| [Inventario de Activos](Semana1/Inventario_Activos.md) | 487 activos catalogados en 8 categorías, 13 activos críticos identificados |
| [Matriz de Riesgos](Semana1/Matriz_Riesgos.md) | 20 riesgos evaluados con metodología probabilidad × impacto, 8 prioritarios |

### Fase 2 — Diseño del SGSI

| Documento | Descripción |
|-----------|-------------|
| [PSI-001 — Política Principal](Politicas/Politica_Seguridad_Informacion_Principal.md) | Marco estratégico rector del SGSI, 23 secciones |
| [PSI-002 — Control de Accesos](Politicas/Politica_Control_Accesos.md) | Política completa de gestión de identidades y accesos, v1.1 |
| [PSI-003 — Uso Aceptable](Politicas/Politica_Uso_Aceptable.md) | Uso aceptable de recursos tecnológicos corporativos |
| [PSI-004/005/006 + Mapeo ISO](Politicas/Politicas_Restantes_y_Mapeo.md) | Incidentes, Backup, Dispositivos Extraíbles y mapeo de 93 controles ISO |
| [Estructura Organizativa](Semana2/Estructura_Organizativa_SGSI.md) | Comité de Seguridad (9 miembros), 10 roles, matriz RACI |
| [PROC-003 — Gestión de Accesos](Procedimientos/PROC-003_Gestion_Accesos.md) | Procedimiento operacional de gestión del ciclo de vida de accesos |
| [PROC-005 — Respuesta a Incidentes](Procedimientos/PROC-005_Respuesta_Incidentes_Seguridad.md) | Procedimiento de 6 fases para respuesta a incidentes |

---

## Normativas Aplicadas

| Norma | Aplicación |
|-------|-----------|
| ISO/IEC 27001:2022 | Marco del SGSI — requisitos y estructura |
| ISO/IEC 27002:2022 | 93 controles de seguridad evaluados |
| ISO 27799:2016 | Controles específicos para el sector salud |
| NIST Cybersecurity Framework | Marco de referencia complementario |
| Ley 19.628 | Protección de datos personales (Chile) |
| Ley 20.584 | Derechos y deberes de los pacientes (Chile) |
| Ley 21.459 | Marco de ciberseguridad (Chile) |

---

## Estado del Proyecto

| Fase | Estado | Entregables |
|------|--------|-------------|
| Semana 1 — Diagnóstico | ✅ Completo | Inventario activos, Matriz riesgos, Informe diagnóstico |
| Semana 2 — Diseño SGSI | ✅ Completo | 9 políticas, 3 procedimientos, 7 formularios, estructura organizativa |
| Semana 3 — Implementación | ✅ Completo | Plan e implementación de 20 controles, plan y registro de capacitación |
| Semana 4 — Auditoría | ✅ Completo | Auditoría interna, acción correctiva, revisión por la dirección, certificación ISO 27001 |

**Proyecto completo** — ciclo PDCA cerrado con certificación ISO/IEC 27001:2022 (escenario simulado, diciembre 2026).

---

## Métricas del Proyecto

- **Políticas desarrolladas:** 6 (PSI-001 a PSI-006)
- **Procedimientos:** 2 (PROC-003, PROC-005)
- **Formularios:** 6 (FORM-001 a FORM-006)
- **Activos inventariados:** 487 (13 críticos)
- **Controles ISO 27002 evaluados:** 93
- **Controles implementados:** 18 (19%) — objetivo Q2 2026: 90%
- **Exposición al riesgo estimada:** $120M CLP/año → objetivo $48M CLP/año

---

## Contexto Académico

**Asignatura:** Ciberseguridad Avanzada  
**Institución:** Universidad de La Serena  
**Período:** Noviembre 2025 — 2026
