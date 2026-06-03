# INVENTARIO Y CLASIFICACIÓN DE ACTIVOS DE INFORMACIÓN
## Stamford Health and Solution SpA

---

**Código:** DIAG-001  
**Versión:** 1.0  
**Fecha:** Noviembre 2025  
**Fase:** Semana 1 — Diagnóstico Inicial  
**Clasificación:** CONFIDENCIAL - USO INTERNO

---

## 1. METODOLOGÍA DE CLASIFICACIÓN

Los activos se clasifican según dos dimensiones:

**Valor del activo** (impacto ante pérdida):
- **Crítico (4):** Su pérdida o compromiso causa daño irreversible al negocio o a pacientes
- **Alto (3):** Impacto severo en operaciones o en cumplimiento regulatorio
- **Medio (2):** Impacto moderado, recuperable en plazo razonable
- **Bajo (1):** Impacto menor, fácilmente recuperable

**Clasificación de la información contenida:**
- **Confidencial:** Datos clínicos, datos personales sensibles, credenciales
- **Restringido:** Información corporativa interna
- **Interno:** Uso operacional general
- **Público:** Sin restricciones de divulgación

---

## 2. CATEGORÍA 1 — ACTIVOS DE INFORMACIÓN (Datos)

| ID | Activo | Descripción | Valor | Clasificación | Propietario |
|----|--------|-------------|-------|---------------|-------------|
| INF-001 | Historias Clínicas Electrónicas | Registros clínicos de 15.000 pacientes activos | **Crítico (4)** | Confidencial | Jefe Área Clínica |
| INF-002 | Base de datos de pacientes | Datos personales: nombre, RUT, dirección, contacto | **Crítico (4)** | Confidencial | CISO / DBA |
| INF-003 | Imágenes médicas (DICOM) | Radiografías, ecografías, resonancias almacenadas | **Crítico (4)** | Confidencial | Jefe Área Clínica |
| INF-004 | Registros de teleconsulta | Grabaciones y transcripciones de videoconsultas | **Alto (3)** | Confidencial | Jefe Área Clínica |
| INF-005 | Datos biométricos | Registros de huella/reconocimiento facial de empleados | **Alto (3)** | Confidencial | RRHH |
| INF-006 | Información financiera | Facturación, estados de cuenta, transacciones | **Alto (3)** | Restringido | Gerencia Financiera |
| INF-007 | Base de datos de proveedores | Contratos, contactos y condiciones comerciales | **Medio (2)** | Restringido | Gerencia General |
| INF-008 | Registros de empleados | Contratos, liquidaciones, evaluaciones de desempeño | **Alto (3)** | Confidencial | RRHH |
| INF-009 | Propiedad intelectual | Código fuente de TechHealth Platform, algoritmos | **Crítico (4)** | Confidencial | CTO |
| INF-010 | Logs de auditoría | Registros de acceso y actividad en sistemas | **Alto (3)** | Restringido | CISO |
| INF-011 | Políticas y procedimientos SGSI | Documentación del sistema de gestión | **Medio (2)** | Restringido | CISO |
| INF-012 | Credenciales de sistemas | Contraseñas, tokens, certificados digitales | **Crítico (4)** | Confidencial | CISO |
| INF-013 | Datos de investigación clínica | Estudios, ensayos, resultados de investigación | **Alto (3)** | Confidencial | Jefe Área Clínica |

**Subtotal Categoría 1:** 13 activos | **Activos críticos:** INF-001, INF-002, INF-003, INF-009, INF-012 (5)

---

## 3. CATEGORÍA 2 — APLICACIONES Y SOFTWARE

| ID | Activo | Descripción | Valor | Clasificación | Propietario |
|----|--------|-------------|-------|---------------|-------------|
| APP-001 | TechHealth Platform | Plataforma principal de telemedicina (desarrollo propio) | **Crítico (4)** | Restringido | CTO |
| APP-002 | Sistema HCE | Módulo de historias clínicas electrónicas | **Crítico (4)** | Confidencial | CTO |
| APP-003 | Portal de Pacientes | Aplicación web/móvil para pacientes | **Alto (3)** | Restringido | CTO |
| APP-004 | Portal Médico | Portal de acceso para profesionales médicos externos | **Alto (3)** | Restringido | CTO |
| APP-005 | Microsoft 365 | Suite ofimática y correo corporativo (licencia) | **Alto (3)** | Interno | CTO |
| APP-006 | Active Directory | Servicio de directorio y autenticación corporativa | **Crítico (4)** | Restringido | Administrador de Sistemas |
| APP-007 | Sistema de Facturación | ERP financiero para facturación y contabilidad | **Alto (3)** | Restringido | Gerencia Financiera |
| APP-008 | Veeam Backup | Software de respaldo y recuperación | **Alto (3)** | Restringido | Administrador de Sistemas |
| APP-009 | Antivirus / EDR | Solución de protección de endpoints | **Medio (2)** | Interno | Equipo de Seguridad |
| APP-010 | SIEM | Sistema de gestión de eventos de seguridad | **Alto (3)** | Restringido | CISO |
| APP-011 | VPN Corporativa | Solución de acceso remoto seguro | **Alto (3)** | Restringido | Administrador de Red |

**Subtotal Categoría 2:** 11 activos | **Activos críticos:** APP-001, APP-002, APP-006 (3)

---

## 4. CATEGORÍA 3 — INFRAESTRUCTURA FÍSICA (Servidores)

| ID | Activo | Descripción | Valor | Ubicación | Propietario |
|----|--------|-------------|-------|-----------|-------------|
| SRV-001 | Servidor de Aplicaciones Principal | TechHealth Platform y HCE en producción | **Crítico (4)** | Data Center La Serena | CTO |
| SRV-002 | Servidor de Base de Datos | Motor de BD principal (PostgreSQL) | **Crítico (4)** | Data Center La Serena | DBA |
| SRV-003 | Servidor de Respaldo | Almacenamiento de backups locales | **Alto (3)** | Data Center La Serena | Administrador de Sistemas |
| SRV-004 | Servidor de Directorio | Active Directory + DNS + DHCP | **Alto (3)** | Data Center La Serena | Administrador de Sistemas |
| SRV-005 | Servidor de Monitoreo | SIEM, logs centralizados | **Medio (2)** | Data Center La Serena | Equipo de Seguridad |

**Subtotal Categoría 3:** 5 activos | **Activos críticos:** SRV-001, SRV-002 (2)

---

## 5. CATEGORÍA 4 — INFRAESTRUCTURA EN LA NUBE (AWS)

| ID | Activo | Descripción | Valor | Región | Propietario |
|----|--------|-------------|-------|--------|-------------|
| AWS-001 | EC2 — Instancias de producción | Servidores virtuales para aplicaciones web | **Crítico (4)** | us-east-1 | CTO |
| AWS-002 | RDS — Base de datos gestionada | Réplica de base de datos en nube (DR) | **Crítico (4)** | sa-east-1 | DBA |
| AWS-003 | S3 — Almacenamiento de backups | Backups cifrados offsite (región São Paulo) | **Alto (3)** | sa-east-1 | Administrador de Sistemas |
| AWS-004 | S3 — Imágenes médicas | Almacenamiento de archivos DICOM | **Alto (3)** | sa-east-1 | CTO |
| AWS-005 | IAM — Gestión de identidades | Control de acceso a servicios AWS | **Crítico (4)** | Global | CISO |
| AWS-006 | KMS — Gestión de claves | Claves de cifrado para datos en reposo | **Crítico (4)** | sa-east-1 | CISO |
| AWS-007 | CloudTrail | Auditoría de acciones en AWS | **Alto (3)** | Global | CISO |
| AWS-008 | VPC — Red privada virtual | Segmentación de red en nube | **Medio (2)** | sa-east-1 | Administrador de Red |

**Subtotal Categoría 4:** 8 activos | **Activos críticos:** AWS-001, AWS-002, AWS-005, AWS-006 (4)

---

## 6. CATEGORÍA 5 — INFRAESTRUCTURA DE RED

| ID | Activo | Descripción | Valor | Propietario |
|----|--------|-------------|-------|-------------|
| RED-001 | Firewall perimetral | Control de tráfico entrante/saliente | **Alto (3)** | Administrador de Red |
| RED-002 | Switches core | Conmutadores de capa 3 para routing interno | **Alto (3)** | Administrador de Red |
| RED-003 | Access points WiFi | Red inalámbrica corporativa y de invitados (VLANs) | **Medio (2)** | Administrador de Red |
| RED-004 | Enlace de Internet principal | Conexión fibra óptica 1 Gbps | **Alto (3)** | Administrador de Red |
| RED-005 | Enlace de Internet de respaldo | Conexión backup 100 Mbps | **Medio (2)** | Administrador de Red |
| RED-006 | VPN Site-to-Site | Túnel cifrado hacia AWS | **Alto (3)** | Administrador de Red |

**Subtotal Categoría 5:** 6 activos

---

## 7. CATEGORÍA 6 — DISPOSITIVOS ENDPOINT

| ID | Activo | Descripción | Cantidad | Valor | Propietario |
|----|--------|-------------|---------|-------|-------------|
| END-001 | PCs de escritorio | Estaciones de trabajo administrativas | 85 | **Medio (2)** | CTO / RRHH |
| END-002 | Notebooks corporativos | Laptops para trabajo remoto y directivos | 30 | **Medio (2)** | CTO |
| END-003 | Smartphones corporativos | Dispositivos móviles para personal clave | 70 | **Medio (2)** | CTO |
| END-004 | Impresoras de red | Impresoras multifuncionales conectadas | 15 | **Bajo (1)** | CTO |
| END-005 | Cámaras de teleconsulta | Equipos de video para atención remota | 20 | **Medio (2)** | CTO |
| END-006 | Dispositivos IoT médicos | Sensores y monitores de signos vitales conectados | 40 | **Alto (3)** | Jefe Área Clínica |

**Subtotal Categoría 6:** 260 unidades (6 tipos)

---

## 8. CATEGORÍA 7 — INSTALACIONES FÍSICAS

| ID | Activo | Descripción | Valor | Propietario |
|----|--------|-------------|-------|-------------|
| FAC-001 | Data Center | Sala de servidores con control de acceso y CCTV | **Crítico (4)** | CTO |
| FAC-002 | Oficinas corporativas | Espacio de trabajo administrativo y clínico | **Medio (2)** | Gerencia General |
| FAC-003 | Sistema UPS | Alimentación ininterrumpida para equipos críticos | **Alto (3)** | CTO |
| FAC-004 | Sistema de climatización | HVAC del Data Center | **Alto (3)** | CTO |
| FAC-005 | Sistema contra incendios | Supresión automática Data Center | **Alto (3)** | Gerencia General |

**Subtotal Categoría 7:** 5 activos | **Activos críticos:** FAC-001 (1)

---

## 9. CATEGORÍA 8 — ACTIVOS DE PERSONAS Y CONOCIMIENTO

| ID | Activo | Descripción | Valor | Propietario |
|----|--------|-------------|-------|-------------|
| PER-001 | CISO | Conocimiento y experiencia en seguridad de la información | **Crítico (4)** | Directorio |
| PER-002 | CTO | Conocimiento técnico de la plataforma TechHealth | **Alto (3)** | Directorio |
| PER-003 | Administradores de Sistemas | Conocimiento de infraestructura y configuraciones | **Alto (3)** | CTO |
| PER-004 | DBAs | Conocimiento de bases de datos y modelos de datos | **Alto (3)** | CTO |
| PER-005 | Desarrolladores | Conocimiento del código fuente de TechHealth | **Alto (3)** | CTO |

**Subtotal Categoría 8:** 5 activos | **Activos críticos:** PER-001 (1)

---

## 10. RESUMEN CONSOLIDADO

| Categoría | N° Activos | Críticos | Alto | Medio | Bajo |
|-----------|-----------|---------|------|-------|------|
| 1 — Información / Datos | 13 | 5 | 5 | 2 | 1 |
| 2 — Aplicaciones / Software | 11 | 3 | 7 | 1 | 0 |
| 3 — Servidores físicos | 5 | 2 | 2 | 1 | 0 |
| 4 — Infraestructura AWS | 8 | 4 | 3 | 1 | 0 |
| 5 — Red | 6 | 0 | 4 | 2 | 0 |
| 6 — Endpoints | 6 tipos | 0 | 1 | 4 | 1 |
| 7 — Instalaciones | 5 | 1 | 3 | 1 | 0 |
| 8 — Personas | 5 | 1 | 4 | 0 | 0 |
| **TOTAL** | **59 tipos / 487 unidades** | **16** | **29** | **12** | **2** |

### Activos Críticos Identificados (16)

> Los siguientes activos requieren los controles más estrictos del SGSI:

1. INF-001 — Historias Clínicas Electrónicas
2. INF-002 — Base de datos de pacientes
3. INF-003 — Imágenes médicas (DICOM)
4. INF-009 — Código fuente TechHealth Platform
5. INF-012 — Credenciales de sistemas
6. APP-001 — TechHealth Platform
7. APP-002 — Sistema HCE
8. APP-006 — Active Directory
9. SRV-001 — Servidor de Aplicaciones Principal
10. SRV-002 — Servidor de Base de Datos
11. AWS-001 — Instancias EC2 de producción
12. AWS-002 — RDS (base de datos gestionada)
13. AWS-005 — IAM (gestión de identidades AWS)
14. AWS-006 — KMS (gestión de claves de cifrado)
15. FAC-001 — Data Center
16. PER-001 — CISO

---

**Documento elaborado por:** Equipo SGSI — Stamford Health and Solution SpA  
**Fecha:** Noviembre 2025  
**Próxima revisión:** Noviembre 2026

---

**FIN DEL DOCUMENTO**
