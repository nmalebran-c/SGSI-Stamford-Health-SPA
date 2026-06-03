# MATRIZ DE EVALUACIÓN DE RIESGOS DE SEGURIDAD
## Stamford Health and Solution SpA

---

**Código:** DIAG-002  
**Versión:** 1.0  
**Fecha:** Noviembre 2025  
**Fase:** Semana 1 — Diagnóstico Inicial  
**Clasificación:** CONFIDENCIAL - USO INTERNO

---

## 1. METODOLOGÍA

### 1.1. Fórmula de evaluación

```
Nivel de Riesgo = Probabilidad × Impacto
```

### 1.2. Escala de Probabilidad

| Valor | Nivel | Descripción |
|-------|-------|-------------|
| 1 | Muy Baja | Ocurre menos de una vez cada 5 años |
| 2 | Baja | Ocurre aproximadamente una vez cada 2-5 años |
| 3 | Media | Ocurre aproximadamente una vez al año |
| 4 | Alta | Ocurre varias veces al año |
| 5 | Muy Alta | Ocurre frecuentemente (mensual o más) |

### 1.3. Escala de Impacto

| Valor | Nivel | Criterios |
|-------|-------|-----------|
| 1 | Muy Bajo | Sin impacto operacional significativo |
| 2 | Bajo | Interrupción menor, recuperación inmediata |
| 3 | Medio | Interrupción de operaciones 1-8 horas, impacto económico < $5M CLP |
| 4 | Alto | Interrupción 8-48h, impacto económico $5M-$30M CLP, datos comprometidos |
| 5 | Crítico | Interrupción >48h, impacto >$30M CLP, brecha de datos de pacientes, sanciones regulatorias |

### 1.4. Mapa de Calor

| | **Impacto 1** | **Impacto 2** | **Impacto 3** | **Impacto 4** | **Impacto 5** |
|---|---|---|---|---|---|
| **Prob. 5** | 5 🟡 | 10 🟠 | 15 🔴 | 20 🔴 | 25 🔴 |
| **Prob. 4** | 4 🟢 | 8 🟡 | 12 🟠 | 16 🔴 | 20 🔴 |
| **Prob. 3** | 3 🟢 | 6 🟡 | 9 🟡 | 12 🟠 | 15 🔴 |
| **Prob. 2** | 2 🟢 | 4 🟢 | 6 🟡 | 8 🟡 | 10 🟠 |
| **Prob. 1** | 1 🟢 | 2 🟢 | 3 🟢 | 4 🟢 | 5 🟡 |

🟢 Aceptable (1–4) | 🟡 Tolerable (5–9) | 🟠 Importante (10–14) | 🔴 Crítico (15–25)

---

## 2. AMENAZAS IDENTIFICADAS

| ID | Amenaza | Categoría |
|----|---------|-----------|
| AME-001 | Ransomware dirigido a sistemas de salud | Ciberataque externo |
| AME-002 | Phishing / Spear phishing a personal médico y administrativo | Ingeniería social |
| AME-003 | Acceso no autorizado a HCE por personal interno | Amenaza interna |
| AME-004 | Fuga de datos de pacientes (exfiltración) | Pérdida de datos |
| AME-005 | Denegación de servicio (DDoS) a plataforma TechHealth | Ciberataque externo |
| AME-006 | Vulnerabilidades en código fuente de TechHealth Platform | Fallo técnico |
| AME-007 | Fallo catastrófico de hardware (servidor principal) | Fallo físico |
| AME-008 | Desastre natural (terremoto, corte eléctrico prolongado) | Amenaza natural |
| AME-009 | Credenciales comprometidas (reutilización, contraseñas débiles) | Error humano / Ataque |
| AME-010 | Proveedor externo comprometido (ataque a cadena de suministro) | Terceros |
| AME-011 | Dispositivo médico IoT comprometido | Ciberataque externo |
| AME-012 | Pérdida o robo de dispositivo con datos sensibles | Pérdida física |
| AME-013 | Uso indebido de privilegios administrativos | Amenaza interna |
| AME-014 | Inyección SQL / ataques a aplicación web | Ciberataque externo |
| AME-015 | Fallo en proveedor de nube (AWS) | Terceros |
| AME-016 | Ingeniería social a personal de soporte TI | Ingeniería social |
| AME-017 | Malware introducido por USB o dispositivo extraíble | Vector físico |
| AME-018 | Brecha de privacidad por acceso médico externo no autorizado | Cumplimiento |
| AME-019 | Fallo de backup (pérdida de datos irrecuperable) | Fallo técnico |

---

## 3. VULNERABILIDADES IDENTIFICADAS

| ID | Vulnerabilidad | Activos Afectados |
|----|---------------|------------------|
| VUL-001 | Ausencia de MFA en sistemas críticos (HCE, AWS) | APP-002, AWS-001, APP-006 |
| VUL-002 | Contraseñas débiles o reutilizadas en cuentas de servicio | INF-012, APP-006 |
| VUL-003 | Falta de segmentación de red entre áreas clínicas y administrativas | RED-001, RED-002 |
| VUL-004 | Parches de seguridad con más de 30 días de atraso en servidores | SRV-001, SRV-002 |
| VUL-005 | Logs de auditoría sin monitoreo centralizado en tiempo real | INF-010, SRV-005 |
| VUL-006 | Ausencia de política formal de gestión de accesos privilegiados | APP-006, SRV-001 |
| VUL-007 | Backups no verificados mediante prueba de restauración periódica | SRV-003, AWS-003 |
| VUL-008 | Falta de capacitación en seguridad para personal médico externo | PER-001 a PER-005 |
| VUL-009 | Código fuente sin análisis de vulnerabilidades (SAST/DAST) | APP-001, APP-002 |
| VUL-010 | Acceso de proveedores sin monitoreo de sesiones | INF-001, APP-001 |
| VUL-011 | Dispositivos IoT médicos sin segmentación de red | END-006, RED-003 |
| VUL-012 | AWS IAM sin aplicar principio de mínimo privilegio | AWS-001 a AWS-008 |
| VUL-013 | Sin plan de continuidad de negocio documentado y probado | SRV-001, APP-001 |
| VUL-014 | Ausencia de cifrado en tránsito en APIs internas | APP-001, APP-002 |
| VUL-015 | Control de acceso físico al Data Center sin biometría | FAC-001 |
| VUL-016 | Gestión manual de secretos y API keys (fuera de bóveda) | INF-012 |
| VUL-017 | Ausencia de proceso formal de baja de usuarios | APP-006 |
| VUL-018 | Sin proceso de gestión de vulnerabilidades técnicas | SRV-001 a SRV-005 |
| VUL-019 | Médicos externos con acceso a HCE sin restricción de pacientes propios | APP-002, APP-004 |
| VUL-020 | Falta de CSIRT formal y procedimientos de respuesta a incidentes | CISO |
| VUL-021 | Sin cifrado de datos en reposo en discos de endpoints | END-001, END-002 |
| VUL-022 | Política de contraseñas no aplicada técnicamente (solo declarativa) | APP-006 |
| VUL-023 | Ausencia de DLP (Data Loss Prevention) | INF-001, INF-002 |

---

## 4. MATRIZ DE RIESGOS COMPLETA

| ID | Riesgo | Amenaza | Activos Afectados | Prob. | Impacto | **Riesgo** | Nivel |
|----|--------|---------|------------------|-------|---------|------------|-------|
| RSG-001 | Cifrado de datos clínicos por ransomware con interrupción del servicio | AME-001 | SRV-001, SRV-002, APP-002, INF-001 | 3 | 5 | **15** | 🔴 Crítico |
| RSG-002 | Brecha masiva de datos de pacientes (HCE) por acceso no autorizado | AME-003, AME-009 | INF-001, INF-002, APP-002 | 3 | 5 | **15** | 🔴 Crítico |
| RSG-003 | Compromiso de credenciales privilegiadas por phishing | AME-002, AME-009 | APP-006, SRV-001, AWS-005 | 4 | 4 | **16** | 🔴 Crítico |
| RSG-004 | Exfiltración de datos de pacientes por insider malicioso | AME-003, AME-004 | INF-001, INF-002, INF-003 | 2 | 5 | **10** | 🟠 Importante |
| RSG-005 | Ataque DDoS con caída total de TechHealth Platform | AME-005 | APP-001, APP-003, APP-004 | 3 | 4 | **12** | 🟠 Importante |
| RSG-006 | Vulnerabilidad crítica explotada en TechHealth Platform | AME-006, AME-014 | APP-001, APP-002, INF-001 | 3 | 4 | **12** | 🟠 Importante |
| RSG-007 | Fallo catastrófico de servidor principal sin recuperación oportuna | AME-007, AME-019 | SRV-001, SRV-002, APP-002 | 2 | 5 | **10** | 🟠 Importante |
| RSG-008 | Dispositivo médico IoT comprometido como vector de entrada a red | AME-011, VUL-011 | END-006, RED-002, SRV-001 | 3 | 4 | **12** | 🟠 Importante |
| RSG-009 | Proveedor externo comprometido con acceso a datos clínicos | AME-010 | INF-001, APP-001, AWS-001 | 2 | 5 | **10** | 🟠 Importante |
| RSG-010 | Pérdida o robo de dispositivo con datos de pacientes sin cifrar | AME-012, VUL-021 | END-001, END-002, END-003 | 4 | 3 | **12** | 🟠 Importante |
| RSG-011 | Abuso de privilegios administrativos en sistemas críticos | AME-013, VUL-006 | SRV-001, SRV-002, AWS-005 | 3 | 4 | **12** | 🟠 Importante |
| RSG-012 | Terremoto / corte eléctrico prolongado con pérdida de datos | AME-008, VUL-013 | FAC-001, SRV-001, SRV-002 | 2 | 5 | **10** | 🟠 Importante |
| RSG-013 | Malware introducido por USB en equipo corporativo | AME-017 | END-001, SRV-001, APP-001 | 4 | 3 | **12** | 🟠 Importante |
| RSG-014 | Acceso de médico externo a HCE de pacientes ajenos | AME-018, VUL-019 | APP-002, APP-004, INF-001 | 3 | 4 | **12** | 🟠 Importante |
| RSG-015 | API key o secreto expuesto en repositorio o sistema sin bóveda | AME-009, VUL-016 | AWS-005, INF-012 | 4 | 3 | **12** | 🟠 Importante |
| RSG-016 | Ingeniería social a personal de soporte TI con acceso privilegiado | AME-016 | APP-006, SRV-001 | 3 | 3 | **9** | 🟡 Tolerable |
| RSG-017 | Fallo del proveedor AWS (interrupción de servicios en nube) | AME-015 | AWS-001, AWS-002, APP-001 | 2 | 4 | **8** | 🟡 Tolerable |
| RSG-018 | Cuenta de usuario activa tras baja de empleado | AME-003, VUL-017 | APP-006, APP-002 | 4 | 2 | **8** | 🟡 Tolerable |
| RSG-019 | Incumplimiento Ley 20.584 por acceso no autorizado a HCE | AME-018 | INF-001, APP-002 | 3 | 3 | **9** | 🟡 Tolerable |
| RSG-020 | Backup corrupto o fallido sin detección oportuna | AME-019, VUL-007 | SRV-003, AWS-003, INF-001 | 3 | 3 | **9** | 🟡 Tolerable |

---

## 5. RIESGOS PRIORITARIOS (Score ≥ 12)

| Prioridad | ID | Riesgo | Score | Control Principal |
|-----------|-----|--------|-------|-----------------|
| 1 | RSG-003 | Compromiso de credenciales privilegiadas | **16** | MFA obligatorio + bóveda de contraseñas |
| 2 | RSG-001 | Ransomware en datos clínicos | **15** | EDR + backup 3-2-1 + segmentación de red |
| 3 | RSG-002 | Brecha masiva de HCE | **15** | MFA + control de accesos + monitoreo |
| 4 | RSG-005 | DDoS en TechHealth Platform | **12** | DDoS protection + CDN + plan de contingencia |
| 5 | RSG-006 | Vulnerabilidad crítica en TechHealth | **12** | SAST/DAST + gestión de vulnerabilidades |
| 6 | RSG-008 | IoT médico como vector de ataque | **12** | Segmentación VLAN 70 + hardening IoT |
| 7 | RSG-010 | Pérdida de dispositivo sin cifrado | **12** | BitLocker en todos los endpoints |
| 8 | RSG-011 | Abuso de privilegios administrativos | **12** | PAM + doble cuenta + logs |
| 9 | RSG-013 | Malware por USB | **12** | Bloqueo de USB + política PSI-006 |
| 10 | RSG-014 | Médico externo accede a HCE ajena | **12** | FORM-006 + restricción por paciente |
| 11 | RSG-015 | API key expuesto | **12** | Bóveda obligatoria + rotación 90 días |

---

## 6. PLAN DE TRATAMIENTO DE RIESGOS

| ID Riesgo | Tratamiento | Prioridad de Implementación | Costo Estimado |
|-----------|-------------|---------------------------|----------------|
| RSG-003 | **Mitigar:** Implementar MFA Q1 2026 + bóveda contraseñas | Q1 2026 | $3M CLP |
| RSG-001 | **Mitigar:** EDR corporativo + pruebas DR semestrales | Q1 2026 | $8M CLP |
| RSG-002 | **Mitigar:** Control de accesos PSI-002 + SIEM | Q1 2026 | $5M CLP |
| RSG-005 | **Mitigar:** Contratar protección DDoS en AWS | Q2 2026 | $2M CLP/año |
| RSG-006 | **Mitigar:** Integrar SAST en pipeline de desarrollo | Q2 2026 | $4M CLP |
| RSG-008 | **Mitigar:** Implementar VLAN 70 dedicada para IoT | Q1 2026 | $1M CLP |
| RSG-010 | **Mitigar:** Activar BitLocker en 115 dispositivos | Q1 2026 | $0.5M CLP |
| RSG-011 | **Mitigar:** PAM + revisión semanal de logs privilegiados | Q1 2026 | $3M CLP |
| RSG-012 | **Transferir:** Seguro de continuidad de negocio | Q2 2026 | $2M CLP/año |
| RSG-015 | **Mitigar:** Bóveda corporativa + IAM Roles AWS | Q1 2026 | $1M CLP |

**Exposición total estimada sin controles:** $120M CLP/año  
**Exposición proyectada con controles (Q4 2026):** $48M CLP/año  
**Reducción de riesgo objetivo:** 60%

---

**Documento elaborado por:** Equipo SGSI — Stamford Health and Solution SpA  
**Fecha:** Noviembre 2025  
**Próxima revisión:** Noviembre 2026

---

**FIN DEL DOCUMENTO**
