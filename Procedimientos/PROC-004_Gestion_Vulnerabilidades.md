# PROCEDIMIENTO DE GESTIÓN DE VULNERABILIDADES TÉCNICAS
## Stamford Health and Solution SpA

---

**Código:** PROC-004  
**Versión:** 1.0  
**Fecha de aprobación:** 2 de junio de 2026  
**Aprobado por:** Comité de Seguridad de la Información  
**Propietario:** CISO  
**Clasificación:** CONFIDENCIAL - USO INTERNO  
**Control ISO 27002:2022:** 8.8 (Gestión de Vulnerabilidades Técnicas)

---

## 1. PROPÓSITO

Definir el proceso para identificar, evaluar, priorizar y remediar vulnerabilidades técnicas en los sistemas de información de Stamford Health and Solution SpA, reduciendo la superficie de ataque y previniendo la explotación de debilidades conocidas.

---

## 2. ALCANCE

Aplica a todos los activos de Nivel 2 y 3:
- Servidores físicos (SRV-001 a SRV-005)
- Infraestructura AWS (EC2, RDS, ECS)
- Aplicaciones web (TechHealth Platform, HCE, portales)
- Endpoints corporativos (PCs, notebooks, smartphones)
- Dispositivos de red (firewall, switches)
- Sistemas operativos y middleware

---

## 3. CLASIFICACIÓN DE VULNERABILIDADES (CVSS v3.1)

| Nivel | CVSS Score | Descripción | Tiempo Máximo de Remediación |
|-------|-----------|-------------|------------------------------|
| **Crítico** | 9.0 – 10.0 | Explotación remota sin autenticación, impacto total | **72 horas** |
| **Alto** | 7.0 – 8.9 | Explotación probable, impacto significativo | **7 días** |
| **Medio** | 4.0 – 6.9 | Explotación posible con condiciones | **30 días** |
| **Bajo** | 0.1 – 3.9 | Explotación difícil, impacto limitado | **90 días** |

> Para vulnerabilidades en sistemas Nivel 3 (HCE, AWS producción), los tiempos se reducen a la mitad.

---

## 4. FUENTES DE DETECCIÓN

| Fuente | Frecuencia | Responsable |
|--------|-----------|-------------|
| Escaneo automatizado de vulnerabilidades (Nessus / OpenVAS) | Semanal (infraestructura) | Equipo de Seguridad Técnica |
| Análisis estático de código (SAST) | Cada despliegue | Desarrolladores |
| Análisis dinámico (DAST) | Mensual (aplicaciones web) | Equipo de Seguridad Técnica |
| Penetration testing externo | Anual | Proveedor externo certificado |
| CVE / NVD (feeds de vulnerabilidades públicas) | Diario (monitoreo automático) | Coordinador de Seguridad |
| AWS Security Hub / Inspector | Continuo | Administrador de Sistemas |
| Reportes de fabricantes (Microsoft, AWS, etc.) | Según publicación | Coordinador de Seguridad |
| Reporte interno de usuarios o personal técnico | Ad hoc | Cualquier empleado → seguridad@stamfordhealth.cl |

---

## 5. PROCESO DE GESTIÓN

### Fase 1 — Detección e Inventario

1. La herramienta de escaneo genera un reporte de vulnerabilidades
2. El Equipo de Seguridad Técnica descarta falsos positivos
3. Cada vulnerabilidad confirmada se registra con:
   - ID único (VUL-[año]-[correlativo])
   - CVE asociado (si existe)
   - Activo afectado
   - Score CVSS y nivel
   - Vector de ataque
   - Fecha de detección

### Fase 2 — Evaluación de Riesgo Contextual

El Score CVSS base puede ajustarse según el contexto de Stamford Health:

| Factor | Efecto |
|--------|--------|
| Activo Nivel 3 (datos de pacientes) | +1 nivel de prioridad |
| Vulnerabilidad con exploit público conocido | +1 nivel de prioridad |
| Activo expuesto a internet | +1 nivel de prioridad |
| Mitigación compensatoria activa (WAF, segmentación) | −1 nivel de prioridad |

### Fase 3 — Priorización y Asignación

1. El Coordinador de Seguridad elabora la lista priorizada de vulnerabilidades
2. Asigna responsable de remediación según el activo afectado:
   - Servidores → Administrador de Sistemas
   - Bases de datos → DBA
   - Aplicaciones → Desarrolladores / CTO
   - Red → Administrador de Red
   - AWS → Administrador de Sistemas + CTO
3. Para vulnerabilidades Críticas y Altas: notificación inmediata al CISO

### Fase 4 — Remediación

| Tipo de remediación | Descripción |
|--------------------|-------------|
| **Parche** | Aplicar actualización del fabricante (vía PSI-007 cambio estándar o emergencia) |
| **Mitigación** | Control compensatorio que reduce el riesgo mientras se prepara el parche |
| **Workaround** | Configuración temporal que elimina la superficie de ataque |
| **Aceptación** | Solo para vulnerabilidades Bajas; requiere aprobación del CISO y registro en FORM-004 |

**Para vulnerabilidades Críticas:**
- Si el parche no está disponible: aislar el activo afectado hasta implementar mitigación efectiva
- CISO notificado en ≤ 1 hora desde la detección
- Evaluar si activa PROC-005 (si hay evidencia de explotación activa)

### Fase 5 — Verificación

1. Después de aplicar el parche o mitigación, re-escanear el activo
2. Confirmar que la vulnerabilidad ya no es detectable
3. Actualizar el registro de la vulnerabilidad con fecha de cierre y método de remediación

### Fase 6 — Registro y Reporte

1. Actualizar el Registro de Vulnerabilidades con el resultado
2. Coordinador de Seguridad presenta informe mensual al CISO con:
   - Vulnerabilidades detectadas en el período
   - Estado de remediación (abiertas, cerradas, en proceso)
   - Incumplimientos de plazos
   - Tendencias
3. Informe trimestral al Comité de Seguridad

---

## 6. GESTIÓN DE PARCHES

### 6.1. Priorización de parches de seguridad

| Criticidad | Plazo de aplicación | Proceso |
|-----------|--------------------|---------| 
| Crítico (CVSS ≥ 9.0) | ≤ 72 horas | Cambio de emergencia (PSI-007 Tipo 3) |
| Alto (CVSS 7.0–8.9) | ≤ 7 días | Cambio normal con aprobación CAB |
| Medio / Bajo | ≤ 30 / 90 días | Cambio estándar en ventana programada |

### 6.2. Parches del sistema operativo

- Parches de seguridad críticos de Windows Server / Linux: aplicación en ≤ 72 horas
- Parches mensuales de Microsoft (Patch Tuesday): aplicación en ≤ 7 días
- Actualizaciones de software de terceros (Java, OpenSSL, etc.): según criticidad CVE

### 6.3. Ambientes

- Los parches se aplican primero en el ambiente de **Desarrollo/QA** para verificar compatibilidad
- Si hay incompatibilidad: implementar mitigación y escalar al CTO para plan de actualización
- Los sistemas de producción se parchean en la ventana de cambios autorizada (PSI-007)

---

## 7. PENETRATION TESTING

- **Frecuencia:** Anual (externo) + semestral (interno)
- **Alcance:** Infraestructura interna, aplicaciones web expuestas, red inalámbrica
- **Proveedor:** Empresa externa con certificación OSCP, CEH o equivalente; aprobada por CISO
- **Acuerdo:** Contrato con alcance definido, NDA firmado, reglas de engagement documentadas
- **Resultados:** Informe entregado al CISO; hallazgos ingresados al Registro de Vulnerabilidades
- **Seguimiento:** Remediación de hallazgos críticos y altos en ≤ 30 días; re-test incluido en el contrato

---

## 8. INDICADORES DE DESEMPEÑO (KPIs)

| Indicador | Meta |
|-----------|------|
| Vulnerabilidades Críticas sin remediar en plazo | 0 |
| Vulnerabilidades Altas sin remediar en plazo | 0 |
| Tiempo promedio de remediación (Crítico) | ≤ 48 horas |
| Cobertura de escaneo (% de activos Nivel 2 y 3 escaneados) | 100% semanal |
| Vulnerabilidades reabiertas (regresión) | < 5% |

---

## 9. RESPONSABILIDADES

| Rol | Responsabilidad |
|-----|----------------|
| **CISO** | Supervisar el proceso, aprobar aceptación de vulnerabilidades, recibir alertas Críticas/Altas |
| **Coordinador de Seguridad** | Gestionar el Registro de Vulnerabilidades, reportar al CISO y al Comité |
| **Equipo de Seguridad Técnica** | Ejecutar escaneos, analizar resultados, coordinar remediación |
| **Administradores de Sistemas** | Aplicar parches en servidores e infraestructura |
| **DBA** | Remediar vulnerabilidades en bases de datos |
| **Desarrolladores** | Remediar vulnerabilidades en código fuente (SAST/DAST) |

---

## 10. REVISIÓN

Anual o tras un incidente originado en una vulnerabilidad no gestionada.

**Próxima revisión:** Junio 2027

---

**Aprobado por:**

**Firma:** ___________________________  
**Nombre:** Rodrigo Vásquez Herrera  
**Cargo:** CISO  
**Fecha:** 2 de junio de 2026

---

**FIN DEL DOCUMENTO**
