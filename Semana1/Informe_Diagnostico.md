# INFORME DE DIAGNÓSTICO INICIAL — SGSI
## Stamford Health and Solution SpA

---

**Código:** DIAG-000  
**Versión:** 1.0  
**Fecha:** Noviembre 2025  
**Fase:** Semana 1 — Diagnóstico Inicial  
**Clasificación:** CONFIDENCIAL - USO INTERNO

---

## 1. RESUMEN EJECUTIVO

Este informe presenta los resultados del diagnóstico inicial de seguridad de la información realizado para **Stamford Health and Solution SpA**, empresa de telemedicina ubicada en La Serena, Chile. El diagnóstico constituye la primera fase del diseño del Sistema de Gestión de Seguridad de la Información (SGSI) basado en **ISO/IEC 27001:2022**.

### Hallazgos principales

| Indicador | Resultado |
|-----------|-----------|
| Activos catalogados | **487** (59 tipos, 8 categorías) |
| Activos críticos identificados | **16** |
| Amenazas identificadas | **19** |
| Vulnerabilidades identificadas | **23** |
| Riesgos evaluados | **20** |
| Riesgos en nivel crítico (score ≥ 15) | **3** |
| Riesgos en nivel importante (score 10–14) | **8** |
| Exposición financiera estimada | **$120M CLP/año** |
| Nivel de madurez en seguridad (estimado) | **Nivel 1 / 5** |

### Veredicto

La organización **no cuenta con un SGSI formal** ni con controles de seguridad básicos implementados de manera sistemática. La ausencia de MFA en sistemas críticos, la falta de un proceso formal de gestión de accesos, y la inexistencia de un procedimiento de respuesta a incidentes representan los riesgos más inmediatos.

---

## 2. DESCRIPCIÓN DE LA ORGANIZACIÓN

### 2.1. Datos generales

| Campo | Detalle |
|-------|---------|
| **Razón social** | Stamford Health and Solution SpA |
| **Giro** | Telemedicina y servicios de salud digital |
| **Ubicación** | La Serena, Chile |
| **Fundación** | 2020 |
| **Empleados** | 85 colaboradores directos |
| **Médicos asociados** | 250 profesionales externos |
| **Pacientes activos** | 15.000 |
| **Facturación anual estimada** | $2.400M CLP |

### 2.2. Servicios principales

- **Teleconsulta médica:** videollamadas entre pacientes y médicos
- **Gestión de historias clínicas electrónicas (HCE)**
- **Portal de pacientes:** reservas, resultados, recetas electrónicas
- **Plataforma TechHealth:** desarrollo propio, alojada en AWS

### 2.3. Infraestructura tecnológica

- 5 servidores físicos en Data Center en La Serena
- Infraestructura en AWS (EC2, RDS, S3, IAM, KMS)
- 85 PCs + 70 smartphones + 30 notebooks corporativos
- 40 dispositivos IoT médicos conectados a la red

---

## 3. METODOLOGÍA DEL DIAGNÓSTICO

El diagnóstico se llevó a cabo en tres etapas:

**Etapa 1 — Levantamiento de activos:**
- Entrevistas con jefes de área (CTO, CISO, Jefe Clínico, RRHH)
- Revisión de documentación técnica existente
- Inventario físico y lógico de sistemas

**Etapa 2 — Identificación de amenazas y vulnerabilidades:**
- Análisis de amenazas basado en ISO/IEC 27002:2022 y NIST CSF
- Escaneo de vulnerabilidades técnicas en capa de red y aplicación
- Revisión de controles existentes vs. controles requeridos

**Etapa 3 — Evaluación de riesgos:**
- Metodología cualitativa: Probabilidad × Impacto (escala 1–5)
- Clasificación por nivel: Aceptable / Tolerable / Importante / Crítico
- Estimación de exposición financiera

---

## 4. ESTADO ACTUAL DE CONTROLES

### 4.1. Controles inexistentes (brechas críticas)

| Control | Estado | Impacto |
|---------|--------|---------|
| Autenticación multifactor (MFA) | ❌ No implementado | RSG-002, RSG-003 |
| Gestión formal de accesos privilegiados | ❌ No implementado | RSG-011 |
| CSIRT y procedimiento de respuesta a incidentes | ❌ No implementado | RSG-001 |
| Segmentación de red (VLANs) | ❌ Parcial | RSG-008 |
| Bóveda de contraseñas corporativa | ❌ No implementado | RSG-015 |
| Política formal de uso aceptable | ❌ No implementado | Varios |
| Plan de recuperación ante desastres probado | ❌ No implementado | RSG-007, RSG-012 |

### 4.2. Controles parcialmente implementados

| Control | Estado | Brecha |
|---------|--------|--------|
| Backups | ⚠️ Parcial | Sin pruebas de restauración regulares |
| Firewall perimetral | ⚠️ Parcial | Sin reglas de default deny en todos los segmentos |
| Antivirus en endpoints | ⚠️ Parcial | Sin EDR, solo antivirus básico |
| Control de acceso físico al Data Center | ⚠️ Parcial | Sin biometría |
| Gestión de parches | ⚠️ Parcial | Sin proceso formal, parches atrasados |

### 4.3. Controles implementados

| Control | Estado |
|---------|--------|
| Correo corporativo con dominio propio | ✅ |
| Conectividad a internet redundante | ✅ |
| Respaldo básico en AWS S3 | ✅ |
| Política informal de contraseñas | ✅ (no técnicamente aplicada) |

**Nivel de cumplimiento ISO 27002:2022 estimado:** 15% (14 controles de 93)

---

## 5. ANÁLISIS DE CUMPLIMIENTO NORMATIVO

| Norma / Ley | Estado de Cumplimiento | Brechas Principales |
|-------------|----------------------|---------------------|
| Ley 19.628 (Datos personales) | ⚠️ Parcial | Sin política formal de tratamiento de datos, sin registro de actividades de tratamiento |
| Ley 20.584 (Derechos pacientes) | ⚠️ Parcial | Sin control de acceso a HCE por paciente, sin logs de 7 años |
| Ley 21.459 (Ciberseguridad) | ❌ Incumplimiento | Sin CSIRT, sin reporte de incidentes |
| ISO/IEC 27001:2022 | ❌ No certificado | Ausencia de SGSI formal |
| ISO 27799:2016 | ❌ No aplicado | Sin controles específicos para sector salud |

---

## 6. EXPOSICIÓN FINANCIERA ESTIMADA

| Escenario de Riesgo | Probabilidad Anual | Impacto Estimado |
|--------------------|-------------------|-----------------|
| Ransomware con interrupción 48h | 30% | $45M CLP |
| Multa por incumplimiento Ley 19.628 | 40% | $20M CLP |
| Brecha de datos de pacientes (reputacional + legal) | 25% | $35M CLP |
| DDoS con pérdida de ingresos | 50% | $10M CLP |
| Fallo de hardware sin DR | 20% | $15M CLP |
| **Exposición total anualizada estimada** | | **$120M CLP/año** |

---

## 7. RECOMENDACIONES PRIORITARIAS

### Inmediatas (antes de Q1 2026)

1. **Implementar MFA** en HCE, VPN y AWS Console
2. **Activar bóveda de contraseñas** para cuentas privilegiadas y secretos
3. **Establecer CSIRT** con procedimiento documentado de respuesta
4. **Implementar segmentación de red** con VLANs definidas
5. **Activar BitLocker** en todos los endpoints corporativos
6. **Realizar prueba de restauración** de backups críticos

### Corto plazo (Q1–Q2 2026)

7. Certificar al personal en seguridad de la información (100% colaboradores)
8. Implementar análisis de vulnerabilidades (SAST/DAST) en TechHealth
9. Establecer proceso formal de gestión de accesos y revisión trimestral
10. Implantar solución EDR en reemplazo del antivirus básico

### Mediano plazo (Q3–Q4 2026)

11. Completar el SGSI y preparar para certificación ISO 27001:2022
12. Implementar DLP (Data Loss Prevention) para datos de pacientes
13. Establecer red VLAN dedicada para dispositivos IoT médicos
14. Contratar seguro de continuidad de negocio

---

## 8. CONCLUSIÓN

Stamford Health and Solution SpA enfrenta una **exposición de riesgo significativa** estimada en $120M CLP anuales, derivada principalmente de la ausencia de controles básicos de seguridad en un entorno que maneja datos clínicos sensibles de 15.000 pacientes. La implementación del SGSI propuesto permitirá reducir esta exposición en aproximadamente un 60%, a $48M CLP anuales, con una inversión proyectada de $75M CLP durante 2026.

El cumplimiento normativo de las Leyes 19.628, 20.584 y 21.459 es urgente y debe priorizarse en el plan de implementación.

---

**Documento elaborado por:** Equipo SGSI — Stamford Health and Solution SpA  
**Fecha:** Noviembre 2025

---

**FIN DEL DOCUMENTO**
