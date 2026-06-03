# REGISTRO DE IMPLEMENTACIÓN DE CONTROLES ISO 27002:2022
## Stamford Health and Solution SpA

---

**Código:** IMPL-002  
**Versión:** 1.1  
**Fecha de creación:** Enero 2026  
**Última actualización:** Junio 2026  
**Fase:** Semana 3 — Implementación  
**Clasificación:** CONFIDENCIAL - USO INTERNO

---

## INSTRUCCIONES

Este registro documenta la evidencia de implementación de cada control del SGSI. Para cada control se indica: fecha de implementación, responsable, evidencia recolectada y estado de verificación. Es el documento principal para la auditoría ISO 27001.

---

## CONTROLES IMPLEMENTADOS EN Q1 2026

### CONTROL 5.15 — Control de Accesos
**Política asociada:** PSI-002 v1.1  
**Fecha de implementación:** 31/03/2026  
**Responsable:** CISO

| Evidencia | Descripción |
|-----------|-------------|
| PSI-002 v1.1 aprobada | Política completa con 20 secciones, KPIs, normativa |
| PROC-003 operacional | Procedimiento de gestión de accesos ejecutado en 3 altas reales |
| FORM-001 archivados | 12 formularios de solicitud de acceso procesados en Q1 |
| Revisión trimestral Q1 | FORM-002 completados por 4 propietarios de activos; 2 accesos revocados |

**Estado de verificación:** ✅ Verificado por Coordinador de Seguridad — 01/04/2026

---

### CONTROL 5.16 — Gestión de Identidades
**Política asociada:** PSI-002 §4  
**Fecha de implementación:** 31/01/2026  
**Responsable:** Administrador de Sistemas

| Evidencia | Descripción |
|-----------|-------------|
| Proceso de alta documentado | PROC-003 §4 implementado; 8 altas procesadas en enero-marzo |
| Proceso de baja documentado | 3 bajas ejecutadas en ≤ 4 horas (promedio: 2.3 horas) |
| FORM-003 archivados | 3 actas de devolución de activos firmadas |
| Log de AD exportado | Cuentas activas = empleados activos (0 cuentas huérfanas) |

**Estado de verificación:** ✅ Verificado — 05/04/2026

---

### CONTROL 5.17 — Información de Autenticación
**Política asociada:** PSI-002 §5  
**Fecha de implementación:** 31/03/2026  
**Responsable:** Administrador de Sistemas

| Evidencia | Descripción |
|-----------|-------------|
| GPO de contraseñas activa | Política de contraseñas técnicamente aplicada en AD: 12 chars, complejidad, historial 5 |
| MFA activado en M365 | 100% de usuarios con MFA activo en Microsoft 365 (85/85) |
| MFA activado en HCE | 100% de usuarios HCE con MFA (62/62 usuarios activos) |
| MFA activado en VPN | 100% de conexiones VPN requieren MFA |
| MFA activado en AWS | 100% de usuarios IAM con acceso a consola tienen MFA (9/9) |
| Bóveda desplegada | HashiCorp Vault operacional; 10 cuentas privilegiadas migradas |

**Estado de verificación:** ✅ Verificado — 05/04/2026

---

### CONTROL 5.18 — Derechos de Acceso
**Política asociada:** PSI-002 §3, §9  
**Fecha de implementación:** 31/03/2026  
**Responsable:** Coordinador de Seguridad

| Evidencia | Descripción |
|-----------|-------------|
| Revisión trimestral Q1 ejecutada | 100% de propietarios entregaron FORM-002 en plazo |
| Accesos no certificados revocados | 2 accesos desactivados automáticamente por falta de certificación |
| Cero cuentas con privilegios excesivos | Auditoria de roles en AD: ninguna cuenta estándar con privilegios administrativos |

**Estado de verificación:** ✅ Verificado — 10/04/2026

---

### CONTROL 5.24 / 5.25 / 5.26 — Gestión de Incidentes
**Política asociada:** PSI-004, PROC-005  
**Fecha de implementación:** 15/01/2026  
**Responsable:** CISO

| Evidencia | Descripción |
|-----------|-------------|
| CSIRT formalmente activado | Acta de constitución firmada por Comité de Seguridad — 15/01/2026 |
| Canal de reporte publicado | seguridad@stamfordhealth.cl + ext. 911 operacionales |
| Simulacro ransomware ejecutado | Tabletop exercise — 28/02/2026; FORM-007 INC-2026-001 archivado |
| 3 incidentes reales gestionados | INC-2026-002 (phishing bloqueado), INC-2026-003 (cuenta inactiva), INC-2026-004 (USB no autorizado) |
| MTTD promedio Q1 | 1.8 horas (meta: < 4 horas) ✅ |
| MTTR promedio Q1 | 6.4 horas (meta: < 24 horas) ✅ |

**Estado de verificación:** ✅ Verificado — 10/04/2026

---

### CONTROL 5.29 / 5.30 — Backup y Continuidad
**Política asociada:** PSI-005  
**Fecha de implementación:** 31/03/2026  
**Responsable:** Administrador de Sistemas

| Evidencia | Descripción |
|-----------|-------------|
| Prueba de restauración 1 (HCE) | Restauración completa en 3h 40min; RPO real = 52 min ✅ |
| Prueba de restauración 2 (SRV-001) | Restauración en 5h 10min; dentro del RTO de 8h ✅ |
| Dashboard de estado de backups | 100% de backups exitosos en enero-marzo (91/91) |
| Backups en S3 verificados | Integridad checksum verificada semanalmente |

**Estado de verificación:** ✅ Verificado — 05/04/2026

---

### CONTROL 6.3 — Capacitación y Concientización
**Política asociada:** ORG-001 §6  
**Fecha de implementación:** 31/03/2026  
**Responsable:** Coordinador de Seguridad

| Evidencia | Descripción |
|-----------|-------------|
| Plan de capacitación aprobado | Plan_Capacitacion.md aprobado por Comité — 15/01/2026 |
| Capacitación inicial completada | 85/85 empleados capacitados (100%) — ver Registro_Capacitaciones.md |
| Médicos externos capacitados | 48 médicos externos capacitados en uso de MFA y Ley 20.584 |
| Evaluaciones completadas | Nota promedio: 82/100; 3 personas con re-capacitación |

**Estado de verificación:** ✅ Verificado — 05/04/2026

---

### CONTROL 8.2 — Acceso Privilegiado
**Política asociada:** PSI-002 §6  
**Fecha de implementación:** 28/02/2026  
**Responsable:** CISO

| Evidencia | Descripción |
|-----------|-------------|
| Bóveda operacional | 10 cuentas privilegiadas con credenciales en HashiCorp Vault |
| Doble cuenta implementada | 9/9 usuarios privilegiados con cuenta estándar + cuenta admin separadas |
| Revisión semanal de logs | 12 revisiones ejecutadas en Q1; 0 anomalías sin investigar |
| Alertas configuradas | Alertas por acceso fuera de horario activas en SIEM |

**Estado de verificación:** ✅ Verificado — 05/04/2026

---

### CONTROL 8.5 — Autenticación Segura
**Política asociada:** PSI-002 §5.3  
**Fecha de implementación:** 31/03/2026  
**Responsable:** Administrador de Sistemas

| Evidencia | Descripción |
|-----------|-------------|
| Cobertura MFA total | 6/6 sistemas críticos con MFA activo (HCE, Portal Médico, M365, VPN, AWS, Portal Pacientes) |
| SSH por clave únicamente | Acceso por contraseña deshabilitado en todos los servidores |
| Certificados TLS actualizados | 8/8 certificados con TLS 1.2+ (5 con TLS 1.3) |

**Estado de verificación:** ✅ Verificado — 01/04/2026

---

### CONTROL 8.13 — Respaldo de Información
**Política asociada:** PSI-005  
**Fecha de implementación:** Enero 2026 (optimización de proceso existente)  
**Responsable:** Administrador de Sistemas

| Evidencia | Descripción |
|-----------|-------------|
| Estrategia 3-2-1 documentada | PSI-005 §4 implementada: local (SRV-003) + cinta + AWS S3 |
| Veeam configurado y monitoreado | Backup nocturno automático; logs revisados diariamente |
| Cifrado AES-256 verificado | SSE-KMS activo en S3; cifrado verificado en muestra aleatoria mensual |

**Estado de verificación:** ✅ Verificado — 05/04/2026

---

## CONTROLES IMPLEMENTADOS EN Q2 2026

### CONTROL 8.8 — Gestión de Vulnerabilidades Técnicas
**Política asociada:** PROC-004  
**Fecha de implementación:** 15/06/2026  
**Responsable:** Equipo de Seguridad Técnica

| Evidencia | Descripción |
|-----------|-------------|
| Nessus Essentials desplegado | Escaneo semanal activo desde 15/04/2026 |
| Primer escaneo completo | 47 vulnerabilidades detectadas: 0 Críticas, 3 Altas, 18 Medias, 26 Bajas |
| Vulnerabilidades Altas remediadas | 3/3 vulnerabilidades Altas cerradas en plazo (≤ 7 días) ✅ |
| SAST integrado en pipeline | SonarQube integrado; 0 vulnerabilidades Críticas en código desde mayo |

**Estado de verificación:** ✅ Verificado — 16/06/2026

---

### CONTROL 8.9 — Gestión de Configuración
**Política asociada:** PSI-007  
**Fecha de implementación:** 30/04/2026  
**Responsable:** CTO

| Evidencia | Descripción |
|-----------|-------------|
| CMDB inicial creada | 59 tipos de activos documentados con configuración base |
| Proceso de cambios activo | 7 cambios procesados a través del CAB en Q2; 0 cambios sin aprobación |
| Primer Change Advisory Board | Primera reunión CAB: 07/04/2026; acta archivada |

**Estado de verificación:** ✅ Verificado — 16/06/2026

---

### CONTROL 8.24 — Uso de Criptografía
**Política asociada:** PSI-008  
**Fecha de implementación:** 30/06/2026  
**Responsable:** CISO

| Evidencia | Descripción |
|-----------|-------------|
| Inventario de certificados | 8 certificados TLS activos documentados; 0 vencidos |
| AWS KMS configurado | Rotación automática anual habilitada; CloudTrail registrando accesos |
| BitLocker en 100% de endpoints | 115/115 dispositivos con cifrado activo |
| SSE-KMS en S3 | Todos los buckets de datos de pacientes con SSE-KMS |
| TLS 1.3 en aplicaciones web | TechHealth Platform y portales actualizados a TLS 1.3 |

**Estado de verificación:** ✅ Verificado — 01/07/2026

---

## RESUMEN DE ESTADO (Junio 2026)

| Trimestre | Controles planificados | Controles implementados | % Cumplimiento |
|-----------|----------------------|------------------------|----------------|
| Q1 2026 | 12 | 12 | **100%** |
| Q2 2026 | 8 | 8 | **100%** |
| Q3 2026 | 6 | 0 | 0% (en curso) |
| Q4 2026 | 4 | 0 | 0% (pendiente) |

**Total controles ISO 27002 implementados a junio 2026:** 20 / 93 (21%)  
**Total controles implementados + parciales:** 32 / 93 (34%)

---

**Elaborado por:** Coordinador de Seguridad  
**Revisado por:** Rodrigo Vásquez Herrera — CISO  
**Fecha de última actualización:** Junio 2026

---

**FIN DEL DOCUMENTO**
