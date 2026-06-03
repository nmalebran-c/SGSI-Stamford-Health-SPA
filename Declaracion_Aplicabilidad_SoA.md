# DECLARACIÓN DE APLICABILIDAD (SoA)
## Statement of Applicability — Stamford Health and Solution SpA

---

**Código:** SOA-001  
**Versión:** 1.0  
**Fecha de aprobación:** 18 de noviembre de 2026  
**Aprobado por:** CISO — Rodrigo Vásquez Herrera  
**Clasificación:** CONFIDENCIAL - USO INTERNO  
**Referencia:** ISO/IEC 27001:2022 — Cláusula 6.1.3 d) | Anexo A (ISO/IEC 27002:2022)

---

## 1. PROPÓSITO

La Declaración de Aplicabilidad (SoA) es el documento central del SGSI exigido por la cláusula 6.1.3 d) de ISO/IEC 27001:2022. Documenta, para cada uno de los **93 controles del Anexo A** (ISO/IEC 27002:2022), si el control **aplica o no** a Stamford Health and Solution SpA, la **justificación** de su inclusión o exclusión, su **estado de implementación** y el **documento del SGSI** que lo soporta.

---

## 2. RESUMEN

| Estado | Cantidad | % |
|--------|---------|---|
| ✅ Implementado | 85 | 91.4% |
| ⚠️ Parcial / En mejora continua | 7 | 7.5% |
| ⛔ No aplica (excluido) | 1 | 1.1% |
| **Total controles Anexo A** | **93** | **100%** |

**Controles aplicables:** 92 / 93 | **Implementados sobre aplicables:** 85 / 92 (92.4%)

**Justificación de exclusión:**
- **8.30 Desarrollo contratado externamente:** No aplica. El desarrollo de la plataforma TechHealth es **100% interno** (equipo de desarrollo propio bajo el CTO). No se contrata desarrollo de software a terceros.

---

## 3. LEYENDA

| Símbolo | Estado de implementación |
|---------|--------------------------|
| ✅ | Implementado y verificado |
| ⚠️ | Parcial — incluido en el plan de mejora continua 2027 |
| ⛔ | No aplica — excluido con justificación |

---

## 4. A.5 — CONTROLES ORGANIZACIONALES (37 controles)

| Control | Nombre | Aplica | Estado | Documento / Justificación |
|---------|--------|--------|--------|---------------------------|
| 5.1 | Políticas de seguridad de la información | Sí | ✅ | PSI-001 |
| 5.2 | Roles y responsabilidades de seguridad | Sí | ✅ | ORG-001 |
| 5.3 | Segregación de funciones | Sí | ✅ | PSI-002 §3.3; ORG-001 (RACI) |
| 5.4 | Responsabilidades de la dirección | Sí | ✅ | PSI-001; AUD-004 |
| 5.5 | Contacto con autoridades | Sí | ✅ | PROC-005 §11.2 |
| 5.6 | Contacto con grupos de interés especial | Sí | ⚠️ | En curso: adhesión a comunidades de ciberseguridad en salud (2027) |
| 5.7 | Inteligencia de amenazas | Sí | ⚠️ | Suscripción a feeds de threat intelligence planificada Q1 2027 |
| 5.8 | Seguridad de la información en gestión de proyectos | Sí | ✅ | PSI-007; PSI-001 |
| 5.9 | Inventario de información y activos asociados | Sí | ✅ | Inventario_Activos (DIAG-001) |
| 5.10 | Uso aceptable de la información y activos | Sí | ✅ | PSI-003 |
| 5.11 | Devolución de activos | Sí | ✅ | PSI-002 §4.3; FORM-003 |
| 5.12 | Clasificación de la información | Sí | ✅ | PSI-001; PSI-002 §3.6 |
| 5.13 | Etiquetado de la información | Sí | ✅ | PSI-001 (clasificación CONFIDENCIAL/RESTRINGIDO/INTERNO) |
| 5.14 | Transferencia de información | Sí | ✅ | PSI-003; PSI-008 (cifrado en tránsito) |
| 5.15 | Control de accesos | Sí | ✅ | PSI-002 |
| 5.16 | Gestión de identidades | Sí | ✅ | PSI-002 §4; PROC-003 |
| 5.17 | Información de autenticación | Sí | ✅ | PSI-002 §5 |
| 5.18 | Derechos de acceso | Sí | ✅ | PSI-002 §3, §9; FORM-002 |
| 5.19 | Seguridad en relaciones con proveedores | Sí | ✅ | PSI-009 |
| 5.20 | Seguridad en contratos con proveedores | Sí | ✅ | PSI-009 §5 |
| 5.21 | Gestión de seguridad en la cadena de suministro TIC | Sí | ✅ | PSI-009 §8 |
| 5.22 | Monitoreo y revisión de servicios de proveedores | Sí | ✅ | PSI-009 §7 |
| 5.23 | Seguridad para uso de servicios en la nube | Sí | ✅ | PSI-009 §8; PSI-008 §6.3 (AWS) |
| 5.24 | Planificación y preparación de gestión de incidentes | Sí | ✅ | PSI-004; PROC-005 |
| 5.25 | Evaluación y decisión sobre eventos de seguridad | Sí | ✅ | PROC-005 §6 |
| 5.26 | Respuesta a incidentes de seguridad | Sí | ✅ | PROC-005 §7-10 |
| 5.27 | Aprendizaje de los incidentes | Sí | ✅ | PROC-005 §12; FORM-007 §11 |
| 5.28 | Recolección de evidencia | Sí | ✅ | PROC-005 §8.1; FORM-007 §9 |
| 5.29 | Seguridad durante interrupciones | Sí | ✅ | PSI-005 (DRP) |
| 5.30 | Preparación TIC para continuidad del negocio | Sí | ✅ | PSI-005 (RTO/RPO, sitio DR) |
| 5.31 | Requisitos legales, regulatorios y contractuales | Sí | ✅ | PSI-001; PSI-002 §17 (Ley 19.628, 20.584) |
| 5.32 | Derechos de propiedad intelectual | Sí | ✅ | PSI-003; PSI-001 |
| 5.33 | Protección de registros | Sí | ✅ | PSI-005 §retención; PSI-002 §10.2 (logs 7 años) |
| 5.34 | Privacidad y protección de PII | Sí | ✅ | PSI-002 §17.1 (Ley 19.628) |
| 5.35 | Revisión independiente de la seguridad | Sí | ✅ | AUD-001/002 (auditoría interna independiente) |
| 5.36 | Cumplimiento de políticas y normas | Sí | ✅ | PSI-001 §sanciones; AUD-002 |
| 5.37 | Procedimientos operativos documentados | Sí | ✅ | PROC-003, PROC-004, PROC-005 |

---

## 5. A.6 — CONTROLES DE PERSONAS (8 controles)

| Control | Nombre | Aplica | Estado | Documento / Justificación |
|---------|--------|--------|--------|---------------------------|
| 6.1 | Investigación de antecedentes (screening) | Sí | ✅ | ORG-001; procedimiento RRHH de verificación previa a contratación |
| 6.2 | Términos y condiciones de empleo | Sí | ✅ | Contratos con cláusulas de seguridad; PSI-003 |
| 6.3 | Concientización, educación y capacitación | Sí | ✅ | IMPL-003; IMPL-004 (100% capacitados) |
| 6.4 | Proceso disciplinario | Sí | ✅ | PSI-002 §14; PSI-003 (sanciones) |
| 6.5 | Responsabilidades tras el cese del empleo | Sí | ✅ | PSI-002 §4.3; FORM-003 §4 |
| 6.6 | Acuerdos de confidencialidad (NDA) | Sí | ✅ | PSI-009 §5.3; FORM-003 §4 |
| 6.7 | Trabajo remoto | Sí | ✅ | PSI-003; PSI-002 §8.2 (VPN + MFA) |
| 6.8 | Reporte de eventos de seguridad | Sí | ✅ | PROC-005 §6; FORM-007 |

---

## 6. A.7 — CONTROLES FÍSICOS (14 controles)

| Control | Nombre | Aplica | Estado | Documento / Justificación |
|---------|--------|--------|--------|---------------------------|
| 7.1 | Perímetros de seguridad física | Sí | ✅ | PSI-002 §7.1 (Data Center) |
| 7.2 | Entrada física | Sí | ✅ | PSI-002 §7.1; biometría implementada Q2 2026 |
| 7.3 | Seguridad de oficinas, salas e instalaciones | Sí | ✅ | PSI-002 §7.2 |
| 7.4 | Monitoreo de seguridad física | Sí | ⚠️ | CCTV operativo; ampliación de cobertura planificada 2027 |
| 7.5 | Protección contra amenazas físicas y ambientales | Sí | ✅ | FAC-003/004/005 (UPS, HVAC, contra incendios) |
| 7.6 | Trabajo en áreas seguras | Sí | ✅ | PSI-002 §7.1 (acceso al Data Center con escolta) |
| 7.7 | Escritorio limpio y pantalla limpia | Sí | ✅ | PSI-002 §7.2 |
| 7.8 | Ubicación y protección de equipos | Sí | ✅ | PSI-002 §7; CMDB |
| 7.9 | Seguridad de activos fuera de las instalaciones | Sí | ✅ | PSI-003 (trabajo remoto); BitLocker en notebooks |
| 7.10 | Soportes de almacenamiento | Sí | ✅ | PSI-006 (dispositivos extraíbles) |
| 7.11 | Servicios de soporte (utilities) | Sí | ✅ | FAC-003 (UPS); FAC-004 (climatización) |
| 7.12 | Seguridad del cableado | Sí | ✅ | PSI-002 §7.1 (Data Center) |
| 7.13 | Mantenimiento de equipos | Sí | ✅ | PSI-007; proveedores con escolta (PSI-009) |
| 7.14 | Eliminación o reutilización segura de equipos | Sí | ✅ | PSI-006 §7 (destrucción certificada) |

---

## 7. A.8 — CONTROLES TECNOLÓGICOS (34 controles)

| Control | Nombre | Aplica | Estado | Documento / Justificación |
|---------|--------|--------|--------|---------------------------|
| 8.1 | Dispositivos de usuario final | Sí | ✅ | PSI-003 §4; BitLocker 100% |
| 8.2 | Derechos de acceso privilegiado | Sí | ✅ | PSI-002 §6 (bóveda, doble cuenta, PAM) |
| 8.3 | Restricción de acceso a la información | Sí | ✅ | PSI-002 §3 (need-to-know, mínimo privilegio) |
| 8.4 | Acceso al código fuente | Sí | ✅ | PSI-002; PSI-007 §8 (control de repositorios) |
| 8.5 | Autenticación segura | Sí | ✅ | PSI-002 §5.3 (MFA 100% sistemas Nivel 3) |
| 8.6 | Gestión de capacidad | Sí | ⚠️ | Monitoreo de capacidad básico; métricas formales en 2027 |
| 8.7 | Protección contra malware | Sí | ✅ | EDR desplegado Q2 2026 (100% de sistemas) |
| 8.8 | Gestión de vulnerabilidades técnicas | Sí | ✅ | PROC-004 (escaneo semanal, pentest anual) |
| 8.9 | Gestión de configuración | Sí | ✅ | PSI-007; CMDB |
| 8.10 | Eliminación de información | Sí | ✅ | PSI-006 §7; PSI-005 (retención y borrado) |
| 8.11 | Enmascaramiento de datos | Sí | ⚠️ | Enmascaramiento en ambientes no productivos planificado 2027 |
| 8.12 | Prevención de fuga de datos (DLP) | Sí | ✅ | DLP (Microsoft Purview) implementado Q3 2026 |
| 8.13 | Respaldo de información | Sí | ✅ | PSI-005 (estrategia 3-2-1, pruebas verificadas) |
| 8.14 | Redundancia de instalaciones de procesamiento | Sí | ✅ | PSI-005 (sitio DR en AWS); simulacro DR Q3 2026 |
| 8.15 | Registro de eventos (logging) | Sí | ✅ | PSI-002 §10.2 (logs centralizados, cifrados) |
| 8.16 | Actividades de monitoreo | Sí | ✅ | PSI-002 §10.1; SIEM con escalamiento 24/7 (NC-M-01 cerrada) |
| 8.17 | Sincronización de relojes | Sí | ⚠️ | NTP configurado; verificación formal de sincronización en 2027 |
| 8.18 | Uso de programas utilitarios privilegiados | Sí | ✅ | PSI-002 §6; PAM con grabación de sesiones |
| 8.19 | Instalación de software en sistemas operativos | Sí | ✅ | PSI-003; PSI-007 (control de cambios) |
| 8.20 | Seguridad de redes | Sí | ✅ | PSI-002 §8.1 (firewall, default deny) |
| 8.21 | Seguridad de servicios de red | Sí | ✅ | PSI-002 §8 (VPN, TLS) |
| 8.22 | Segregación de redes | Sí | ✅ | PSI-002 §8.1 (7 VLANs) |
| 8.23 | Filtrado web | Sí | ✅ | PSI-003 §6.2 (bloqueo de categorías) |
| 8.24 | Uso de criptografía | Sí | ✅ | PSI-008 |
| 8.25 | Ciclo de vida de desarrollo seguro | Sí | ✅ | PSI-007 §8; SAST/DAST en pipeline |
| 8.26 | Requisitos de seguridad de aplicaciones | Sí | ✅ | PSI-007; security gate en CI/CD |
| 8.27 | Arquitectura y principios de ingeniería segura | Sí | ✅ | PSI-007 §8; PSI-008 |
| 8.28 | Codificación segura | Sí | ✅ | SAST (SonarQube); estándares de código seguro |
| 8.29 | Pruebas de seguridad en desarrollo y aceptación | Sí | ✅ | PROC-004 (DAST); flujo Dev→QA→Prod |
| 8.30 | Desarrollo contratado externamente | **No** | ⛔ | **Excluido:** TechHealth se desarrolla 100% in-house; no hay desarrollo contratado a terceros |
| 8.31 | Separación de ambientes de desarrollo, prueba y producción | Sí | ✅ | PSI-007 §8 (Dev→QA→Pre-prod→Prod) |
| 8.32 | Gestión de cambios | Sí | ✅ | PSI-007 (CAB, ventanas de cambio) |
| 8.33 | Información de prueba | Sí | ⚠️ | Datos de prueba sintéticos; procedimiento formal de anonimización en 2027 |
| 8.34 | Protección de sistemas durante auditorías | Sí | ✅ | AUD-001 §9 (acceso de auditores de solo lectura, supervisado) |

---

## 8. CONTROLES EN MEJORA CONTINUA (Plan 2027)

Los 7 controles marcados como ⚠️ Parcial forman parte del plan de mejora continua aprobado en la Revisión por la Dirección (AUD-004, decisión N°3):

| Control | Acción planificada | Plazo |
|---------|--------------------|-------|
| 5.6 | Adhesión a comunidades de ciberseguridad en salud | Q1 2027 |
| 5.7 | Suscripción a feeds de inteligencia de amenazas | Q1 2027 |
| 7.4 | Ampliación de cobertura CCTV | Q2 2027 |
| 8.6 | Métricas formales de gestión de capacidad | Q1 2027 |
| 8.11 | Enmascaramiento de datos en ambientes no productivos | Q2 2027 |
| 8.17 | Verificación formal de sincronización de relojes | Q1 2027 |
| 8.33 | Procedimiento de anonimización de datos de prueba | Q2 2027 |

---

## 9. APROBACIÓN

Esta Declaración de Aplicabilidad fue elaborada como acción correctiva a la NC-m-01 de la auditoría interna (AUD-002) y aprobada formalmente para sustentar la auditoría externa de certificación ISO/IEC 27001:2022.

**Elaborado por:** Coordinador de Seguridad  
**Aprobado por:** Rodrigo Vásquez Herrera — CISO  
**Firma:** ___________________________  
**Fecha:** 18 de noviembre de 2026

---

## 10. CONTROL DE CAMBIOS

| Versión | Fecha | Descripción |
|---------|-------|-------------|
| 1.0 | 18/11/2026 | Versión inicial — 93 controles del Anexo A evaluados |

---

**FIN DEL DOCUMENTO**
