# PLAN DE AUDITORÍA INTERNA DEL SGSI
## Stamford Health and Solution SpA

---

**Código:** AUD-001  
**Versión:** 1.0  
**Fecha de aprobación:** 1 de octubre de 2026  
**Aprobado por:** Comité de Seguridad de la Información  
**Responsable:** Coordinador de Seguridad (Auditor Líder Interno)  
**Fase:** Semana 4 — Auditoría  
**Clasificación:** CONFIDENCIAL - USO INTERNO  
**Referencia normativa:** ISO/IEC 27001:2022 — Cláusula 9.2 (Auditoría Interna)

---

## 1. PROPÓSITO

Definir el alcance, criterios, metodología y cronograma de la auditoría interna del Sistema de Gestión de Seguridad de la Información (SGSI) de Stamford Health and Solution SpA, con el fin de verificar la conformidad del SGSI con los requisitos de la norma ISO/IEC 27001:2022 y con las políticas internas, antes de la auditoría externa de certificación.

---

## 2. OBJETIVOS DE LA AUDITORÍA

1. Verificar que el SGSI cumple los requisitos de ISO/IEC 27001:2022 (cláusulas 4 a 10)
2. Verificar la implementación efectiva de los controles del Anexo A / ISO 27002:2022
3. Comprobar que las políticas (PSI-001 a PSI-009) y procedimientos se aplican en la práctica
4. Identificar no conformidades y oportunidades de mejora antes de la certificación
5. Evaluar la eficacia de los controles implementados durante 2026

---

## 3. ALCANCE

### 3.1. Alcance organizacional
Toda la organización Stamford Health and Solution SpA, incluyendo:
- Áreas: Clínica, Administrativa, TI, Dirección
- Sedes: Oficinas corporativas y Data Center (La Serena)
- Infraestructura en la nube (AWS)

### 3.2. Alcance documental
- Cláusulas 4 a 10 de ISO/IEC 27001:2022
- 93 controles evaluados de ISO/IEC 27002:2022
- Políticas PSI-001 a PSI-009
- Procedimientos PROC-003, PROC-004, PROC-005
- Formularios FORM-001 a FORM-007
- Registros de implementación (IMPL-002) y capacitación (IMPL-004)

### 3.3. Exclusiones
- Sistemas fuera del alcance declarado del SGSI (uso personal no autorizado)

---

## 4. CRITERIOS DE AUDITORÍA

| Criterio | Fuente |
|----------|--------|
| Requisitos del SGSI | ISO/IEC 27001:2022 |
| Controles de seguridad | ISO/IEC 27002:2022, ISO 27799:2016 |
| Políticas internas | PSI-001 a PSI-009 |
| Requisitos legales | Ley 19.628, Ley 20.584, Ley 21.459 |

---

## 5. EQUIPO AUDITOR

| Rol | Responsable | Independencia |
|-----|------------|---------------|
| **Auditor Líder** | Coordinador de Seguridad | No audita áreas bajo su responsabilidad directa |
| **Auditor de apoyo** | Analista de Seguridad 1 | Audita procesos de TI distintos a los propios |
| **Observador** | Asesor externo (consultor pre-auditoría) | Independencia total |

> **Principio de independencia (ISO 27001 §9.2):** Ningún auditor audita su propio trabajo. La auditoría del área de seguridad la realiza el consultor externo.

---

## 6. METODOLOGÍA

La auditoría se realizará mediante:

| Técnica | Aplicación |
|---------|-----------|
| **Revisión documental** | Verificación de políticas, procedimientos, registros y evidencias |
| **Entrevistas** | A propietarios de activos, administradores, CISO, jefes de área |
| **Observación directa** | Inspección física del Data Center, controles de acceso |
| **Pruebas de cumplimiento** | Verificación técnica de controles (MFA, cifrado, logs, backups) |
| **Muestreo** | Revisión de muestra de FORM-001, FORM-002, logs de acceso, tickets de incidentes |

**Escala de hallazgos:**
- **No Conformidad Mayor (NC-M):** Ausencia o fallo total de un requisito que compromete el SGSI
- **No Conformidad Menor (NC-m):** Desviación puntual que no compromete el sistema global
- **Observación (OBS):** Oportunidad de mejora; no es incumplimiento
- **Conformidad (C):** Cumple el requisito

---

## 7. CRONOGRAMA

| Fecha | Actividad | Área / Cláusula | Auditor |
|-------|-----------|----------------|---------|
| 13/10/2026 | Reunión de apertura | Toda la organización | Auditor Líder |
| 13/10/2026 | Auditoría cláusulas 4-5 (Contexto y Liderazgo) | Dirección, CISO | Auditor Líder |
| 14/10/2026 | Auditoría cláusula 6 (Planificación) + gestión de riesgos | CISO, Comité | Auditor Líder |
| 14/10/2026 | Auditoría cláusula 7 (Soporte) + capacitación | RRHH, Coordinador | Auditor de apoyo |
| 15/10/2026 | Auditoría controles de acceso (PSI-002, PROC-003) | TI, Administradores | Auditor de apoyo |
| 15/10/2026 | Auditoría gestión de incidentes (PSI-004, PROC-005) | CSIRT | Auditor Líder |
| 16/10/2026 | Auditoría controles técnicos (cifrado, backup, vuln.) | TI, DBA | Auditor de apoyo |
| 16/10/2026 | Inspección física Data Center | Instalaciones | Auditor Líder + Observador |
| 17/10/2026 | Auditoría cláusulas 9-10 (Evaluación y Mejora) | CISO, Comité | Auditor Líder |
| 20/10/2026 | Consolidación de hallazgos | Equipo auditor | Todos |
| 22/10/2026 | Reunión de cierre y presentación de hallazgos | Comité de Seguridad | Auditor Líder |
| 30/10/2026 | Entrega del Informe de Auditoría Interna (AUD-002) | — | Auditor Líder |

---

## 8. ENTREGABLES

| Entregable | Código | Fecha |
|-----------|--------|-------|
| Informe de Auditoría Interna | AUD-002 | 30/10/2026 |
| Plan de Acción Correctiva | AUD-003 | 07/11/2026 |
| Insumo para Revisión por la Dirección | AUD-004 | 15/11/2026 |

---

## 9. CONFIDENCIALIDAD

Toda la información recolectada durante la auditoría es confidencial y se usa exclusivamente para los fines del SGSI. El equipo auditor firma acuerdo de confidencialidad.

---

**Aprobado por:**

**Firma:** ___________________________  
**Nombre:** Rodrigo Vásquez Herrera  
**Cargo:** CISO  
**Fecha:** 1 de octubre de 2026

---

**FIN DEL DOCUMENTO**
