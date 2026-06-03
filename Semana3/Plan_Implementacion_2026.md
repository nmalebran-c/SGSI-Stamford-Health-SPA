# PLAN DE IMPLEMENTACIÓN DEL SGSI 2026
## Stamford Health and Solution SpA

---

**Código:** IMPL-001  
**Versión:** 1.0  
**Fecha:** Diciembre 2025  
**Fase:** Semana 3 — Implementación  
**Clasificación:** CONFIDENCIAL - USO INTERNO

---

## 1. RESUMEN EJECUTIVO

Este plan define la hoja de ruta para implementar los controles del SGSI durante 2026, con el objetivo de reducir la exposición al riesgo de **$120M CLP/año a $48M CLP/año** y obtener la certificación **ISO/IEC 27001:2022** en diciembre de 2026.

| Indicador | Valor |
|-----------|-------|
| **Controles a implementar** | 73 (de 93 evaluados) |
| **Presupuesto total** | $75M CLP |
| **Período** | Enero — Diciembre 2026 |
| **Responsable general** | CISO — Rodrigo Vásquez Herrera |
| **Reducción de riesgo objetivo** | 60% |

---

## 2. CRONOGRAMA GENERAL

```
Q1 2026 (Ene–Mar): Controles críticos de acceso y autenticación
Q2 2026 (Abr–Jun): Controles técnicos y gestión de vulnerabilidades
Q3 2026 (Jul–Sep): Madurez operacional y preparación para auditoría
Q4 2026 (Oct–Dic): Auditoría interna + Auditoría externa ISO 27001
```

---

## 3. Q1 2026 — CONTROLES CRÍTICOS (Enero–Marzo 2026)

**Presupuesto Q1:** $27M CLP | **Objetivo:** Mitigar los 3 riesgos con score ≥ 15

### 3.1. Implementación de MFA

| Actividad | Responsable | Fecha Límite | Estado |
|-----------|------------|-------------|--------|
| Seleccionar solución MFA (Microsoft Authenticator + Azure AD) | CTO | 15/01/2026 | ✅ Completado |
| Configurar MFA en Microsoft 365 y Active Directory | Administrador de Sistemas | 31/01/2026 | ✅ Completado |
| Activar MFA en HCE (APP-002) | Administrador de Sistemas | 15/02/2026 | ✅ Completado |
| Activar MFA en Portal Médico (APP-004) | Administrador de Sistemas | 15/02/2026 | ✅ Completado |
| Activar MFA en VPN corporativa | Administrador de Red | 28/02/2026 | ✅ Completado |
| Activar MFA en AWS Console | Administrador de Sistemas | 28/02/2026 | ✅ Completado |
| Capacitar a usuarios en uso de MFA (100%) | Coordinador de Seguridad | 31/03/2026 | ✅ Completado |

**Costo estimado:** $3M CLP | **Riesgo mitigado:** RSG-003 (16 → 6)

### 3.2. Implementación de Bóveda de Contraseñas (Password Vault)

| Actividad | Responsable | Fecha Límite | Estado |
|-----------|------------|-------------|--------|
| Seleccionar solución (HashiCorp Vault + integración AWS KMS) | CISO + CTO | 15/01/2026 | ✅ Completado |
| Desplegar bóveda en servidor dedicado | Administrador de Sistemas | 31/01/2026 | ✅ Completado |
| Migrar credenciales privilegiadas (10 usuarios) | Administrador de Sistemas | 15/02/2026 | ✅ Completado |
| Migrar API keys y secretos de integración | Equipo de Seguridad Técnica | 28/02/2026 | ✅ Completado |
| Capacitar a usuarios privilegiados | Coordinador de Seguridad | 15/03/2026 | ✅ Completado |
| Verificar cobertura 100% de cuentas privilegiadas | CISO | 31/03/2026 | ✅ Completado |

**Costo estimado:** $2M CLP | **Riesgo mitigado:** RSG-015 (12 → 4)

### 3.3. Segmentación de Red (VLANs)

| Actividad | Responsable | Fecha Límite | Estado |
|-----------|------------|-------------|--------|
| Diseñar esquema de 7 VLANs (PSI-002 §8.1) | Administrador de Red + CTO | 15/01/2026 | ✅ Completado |
| Configurar VLANs en switches core | Administrador de Red | 07/02/2026 | ✅ Completado |
| Configurar reglas de firewall (default deny) | Administrador de Red | 14/02/2026 | ✅ Completado |
| Aislar dispositivos IoT médicos en VLAN 70 | Administrador de Red | 21/02/2026 | ✅ Completado |
| Pruebas de segmentación y verificación de reglas | Equipo de Seguridad Técnica | 28/02/2026 | ✅ Completado |
| Auditoría de reglas de firewall | Coordinador de Seguridad | 31/03/2026 | ✅ Completado |

**Costo estimado:** $1M CLP | **Riesgo mitigado:** RSG-008 (12 → 5)

### 3.4. Cifrado de Endpoints (BitLocker)

| Actividad | Responsable | Fecha Límite | Estado |
|-----------|------------|-------------|--------|
| Activar BitLocker vía GPO en 85 PCs de escritorio | Administrador de Sistemas | 31/01/2026 | ✅ Completado |
| Activar BitLocker en 30 notebooks corporativos | Administrador de Sistemas | 15/02/2026 | ✅ Completado |
| Configurar respaldo de claves de recuperación en AD | Administrador de Sistemas | 28/02/2026 | ✅ Completado |
| Verificar cobertura 100% de endpoints | Coordinador de Seguridad | 31/03/2026 | ✅ Completado |

**Costo estimado:** $0.5M CLP | **Riesgo mitigado:** RSG-010 (12 → 4)

### 3.5. Activación del CSIRT

| Actividad | Responsable | Fecha Límite | Estado |
|-----------|------------|-------------|--------|
| Formalizar equipo CSIRT (CISO + 3 técnicos) | CISO | 15/01/2026 | ✅ Completado |
| Publicar canal de reporte de incidentes (correo + ext. 911) | CISO | 15/01/2026 | ✅ Completado |
| Capacitar al equipo CSIRT en PROC-005 | Coordinador de Seguridad | 31/01/2026 | ✅ Completado |
| Primer simulacro de incidente (ransomware tabletop) | CISO | 28/02/2026 | ✅ Completado |
| Documentar lecciones aprendidas del simulacro | Coordinador de Seguridad | 07/03/2026 | ✅ Completado |

**Costo estimado:** $1M CLP | **Riesgo mitigado:** RSG-001 (15 → 8)

### 3.6. Prueba de Restauración de Backups

| Actividad | Responsable | Fecha Límite | Estado |
|-----------|------------|-------------|--------|
| Definir cronograma de pruebas mensuales | Administrador de Sistemas | 15/01/2026 | ✅ Completado |
| Primera prueba de restauración (BD HCE) | DBA | 31/01/2026 | ✅ Completado |
| Segunda prueba (servidor de aplicaciones) | Administrador de Sistemas | 28/02/2026 | ✅ Completado |
| Documentar resultados y tiempos de RTO/RPO reales | DBA | 15/03/2026 | ✅ Completado |

**Costo estimado:** $0.5M CLP

---

## 4. Q2 2026 — CONTROLES TÉCNICOS (Abril–Junio 2026)

**Presupuesto Q2:** $25M CLP | **Objetivo:** Implementar controles técnicos de detección y prevención

### 4.1. Implementación de EDR

| Actividad | Responsable | Fecha Límite | Estado |
|-----------|------------|-------------|--------|
| Evaluar y seleccionar solución EDR (CrowdStrike / SentinelOne) | CTO + CISO | 15/04/2026 | ✅ Completado |
| Desplegar agente EDR en servidores físicos | Equipo de Seguridad Técnica | 30/04/2026 | ✅ Completado |
| Desplegar EDR en endpoints corporativos (115 dispositivos) | Equipo de Seguridad Técnica | 15/05/2026 | ✅ Completado |
| Configurar alertas y reglas de detección | Equipo de Seguridad Técnica | 31/05/2026 | ✅ Completado |
| Capacitar al equipo de seguridad en uso del EDR | Coordinador de Seguridad | 15/06/2026 | ✅ Completado |

**Costo estimado:** $8M CLP | **Riesgo mitigado:** RSG-001 (8 → 4), RSG-013 (12 → 5)

### 4.2. Implementación de SAST/DAST en TechHealth Platform

| Actividad | Responsable | Fecha Límite | Estado |
|-----------|------------|-------------|--------|
| Integrar SAST (SonarQube) en pipeline CI/CD | CTO + Desarrolladores | 30/04/2026 | ✅ Completado |
| Primera ejecución de SAST y remediación de hallazgos críticos | Desarrolladores | 15/05/2026 | ✅ Completado |
| Primer análisis DAST en Portal Médico y TechHealth | Equipo de Seguridad Técnica | 31/05/2026 | ✅ Completado |
| Definir criterio de calidad de seguridad (security gate) | CTO + CISO | 15/06/2026 | ✅ Completado |

**Costo estimado:** $4M CLP | **Riesgo mitigado:** RSG-006 (12 → 5)

### 4.3. Gestión de Vulnerabilidades (PROC-004)

| Actividad | Responsable | Fecha Límite | Estado |
|-----------|------------|-------------|--------|
| Desplegar herramienta de escaneo (Nessus Essentials) | Equipo de Seguridad Técnica | 15/04/2026 | ✅ Completado |
| Primer escaneo completo de infraestructura | Equipo de Seguridad Técnica | 30/04/2026 | ✅ Completado |
| Remediar todas las vulnerabilidades Críticas y Altas detectadas | Administrador de Sistemas | 31/05/2026 | ✅ Completado |
| Establecer ciclo semanal de escaneo automatizado | Equipo de Seguridad Técnica | 15/06/2026 | ✅ Completado |

**Costo estimado:** $2M CLP

### 4.4. Protección DDoS en AWS

| Actividad | Responsable | Fecha Límite | Estado |
|-----------|------------|-------------|--------|
| Activar AWS Shield Standard (incluido en AWS) | Administrador de Sistemas | 15/04/2026 | ✅ Completado |
| Configurar AWS WAF en TechHealth Platform y portales | CTO | 30/04/2026 | ✅ Completado |
| Definir y activar reglas WAF para OWASP Top 10 | Equipo de Seguridad Técnica | 31/05/2026 | ✅ Completado |
| Prueba de carga y validación de protecciones | CTO | 15/06/2026 | ✅ Completado |

**Costo estimado:** $2M CLP/año | **Riesgo mitigado:** RSG-005 (12 → 5)

### 4.5. Control de Acceso Físico — Biometría Data Center

| Actividad | Responsable | Fecha Límite | Estado |
|-----------|------------|-------------|--------|
| Seleccionar e instalar lector biométrico (huella) en Data Center | CTO | 30/04/2026 | ✅ Completado |
| Enrolar al personal autorizado (5 personas + CISO) | Administrador de Sistemas | 15/05/2026 | ✅ Completado |
| Integrar con sistema de control de acceso físico existente | Administrador de Sistemas | 31/05/2026 | ✅ Completado |

**Costo estimado:** $1.5M CLP

---

## 5. Q3 2026 — MADUREZ OPERACIONAL (Julio–Septiembre 2026)

**Presupuesto Q3:** $15M CLP | **Objetivo:** Consolidar controles y preparar auditoría

### 5.1. Implementación de PAM (Privileged Access Management)

| Actividad | Responsable | Fecha Límite | Estado |
|-----------|------------|-------------|--------|
| Desplegar solución PAM integrada con bóveda | CISO + CTO | 31/07/2026 | ⏳ Pendiente |
| Configurar grabación de sesiones privilegiadas | Equipo de Seguridad Técnica | 15/08/2026 | ⏳ Pendiente |
| Integrar PAM con Active Directory | Administrador de Sistemas | 31/08/2026 | ⏳ Pendiente |

**Costo estimado:** $4M CLP | **Riesgo mitigado:** RSG-011 (12 → 4)

### 5.2. Simulacro de Recuperación ante Desastres (DRP)

| Actividad | Responsable | Fecha Límite | Estado |
|-----------|------------|-------------|--------|
| Planificar simulacro completo DR (activación AWS) | CTO + CISO | 31/07/2026 | ⏳ Pendiente |
| Ejecutar simulacro: fallo total del Data Center | CTO + Administrador de Sistemas | 29/08/2026 | ⏳ Pendiente |
| Medir RTO y RPO reales vs. objetivos | DBA | 05/09/2026 | ⏳ Pendiente |
| Documentar resultados y actualizar PROC-005 | Coordinador de Seguridad | 19/09/2026 | ⏳ Pendiente |

**Costo estimado:** $1M CLP

### 5.3. Segunda Ronda de Capacitación (Anual)

| Actividad | Responsable | Fecha Límite | Estado |
|-----------|------------|-------------|--------|
| Capacitación avanzada al equipo CSIRT | Coordinador de Seguridad | 31/08/2026 | ⏳ Pendiente |
| Capacitación de actualización a todo el personal | Coordinador de Seguridad | 30/09/2026 | ⏳ Pendiente |
| Segundo simulacro de incidente (brecha de datos) | CISO | 26/09/2026 | ⏳ Pendiente |

### 5.4. Implementación de DLP (Data Loss Prevention)

| Actividad | Responsable | Fecha Límite | Estado |
|-----------|------------|-------------|--------|
| Seleccionar e implementar solución DLP (Microsoft Purview) | CTO + CISO | 31/08/2026 | ⏳ Pendiente |
| Configurar políticas para datos de pacientes | Equipo de Seguridad Técnica | 30/09/2026 | ⏳ Pendiente |

**Costo estimado:** $4M CLP | **Riesgo mitigado:** RSG-004 (10 → 4)

### 5.5. Pre-auditoría ISO 27001

| Actividad | Responsable | Fecha Límite | Estado |
|-----------|------------|-------------|--------|
| Contratar consultor de pre-auditoría ISO 27001 | CISO | 31/07/2026 | ⏳ Pendiente |
| Ejecutar pre-auditoría (gap analysis vs. ISO 27001) | Consultor + CISO | 30/09/2026 | ⏳ Pendiente |
| Elaborar plan de cierre de brechas identificadas | CISO | 15/10/2026 | ⏳ Pendiente |

**Costo estimado:** $3M CLP

---

## 6. Q4 2026 — AUDITORÍA Y CERTIFICACIÓN (Octubre–Diciembre 2026)

**Presupuesto Q4:** $8M CLP | **Objetivo:** Obtener certificación ISO 27001:2022

| Actividad | Responsable | Fecha Límite | Estado |
|-----------|------------|-------------|--------|
| Cerrar brechas identificadas en pre-auditoría | CISO + CTO | 31/10/2026 | ⏳ Pendiente |
| Ejecutar auditoría interna completa | Coordinador de Seguridad | 30/10/2026 | ⏳ Pendiente |
| Revisión por la Dirección (ISO 27001 cláusula 9.3) | Comité de Seguridad | 15/11/2026 | ⏳ Pendiente |
| Auditoría externa Etapa 1 (revisión documental) | Organismo certificador | 01/11/2026 | ⏳ Pendiente |
| Auditoría externa Etapa 2 (auditoría in situ) | Organismo certificador | 01/12/2026 | ⏳ Pendiente |
| Obtención certificación ISO 27001:2022 | — | 31/12/2026 | ⏳ Pendiente |

---

## 7. RESUMEN FINANCIERO

| Trimestre | Presupuesto | Ejecutado | Desviación |
|-----------|------------|---------|-----------|
| Q1 2026 | $27M CLP | $8M CLP | −$19M CLP (controles más eficientes) |
| Q2 2026 | $25M CLP | $17.5M CLP | −$7.5M CLP |
| Q3 2026 | $15M CLP | — | — |
| Q4 2026 | $8M CLP | — | — |
| **TOTAL** | **$75M CLP** | **$25.5M CLP** | — |

---

## 8. ESTADO CONSOLIDADO DE RIESGOS PRIORITARIOS

| ID | Riesgo | Score Inicial | Score Actual | Reducción |
|----|--------|-------------|-------------|-----------|
| RSG-003 | Compromiso de credenciales privilegiadas | 16 | 4 | ✅ −75% |
| RSG-001 | Ransomware en datos clínicos | 15 | 4 | ✅ −73% |
| RSG-002 | Brecha masiva de HCE | 15 | 6 | ✅ −60% |
| RSG-005 | DDoS en TechHealth Platform | 12 | 5 | ✅ −58% |
| RSG-006 | Vulnerabilidad crítica en TechHealth | 12 | 5 | ✅ −58% |
| RSG-008 | IoT médico como vector de ataque | 12 | 5 | ✅ −58% |
| RSG-010 | Pérdida de dispositivo sin cifrado | 12 | 4 | ✅ −67% |
| RSG-013 | Malware por USB | 12 | 5 | ✅ −58% |
| RSG-011 | Abuso de privilegios administrativos | 12 | 12 | ⏳ Q3 2026 |
| RSG-015 | API key expuesto | 12 | 4 | ✅ −67% |

**Exposición actual estimada (junio 2026):** ~$62M CLP/año (reducción del 48% vs. inicial)

---

**Elaborado por:** Rodrigo Vásquez Herrera — CISO  
**Fecha:** Diciembre 2025 | **Última actualización:** Junio 2026

---

**FIN DEL DOCUMENTO**
