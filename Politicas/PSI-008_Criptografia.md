# POLÍTICA DE CRIPTOGRAFÍA
## Stamford Health and Solution SpA

---

**Código:** PSI-008  
**Versión:** 1.0  
**Fecha de aprobación:** 2 de junio de 2026  
**Aprobado por:** Comité de Seguridad de la Información  
**Propietario:** CISO  
**Clasificación:** CONFIDENCIAL - USO INTERNO  
**Controles ISO 27002:2022:** 8.24 (Uso de Criptografía)

---

## 1. PROPÓSITO

Establecer los estándares criptográficos que deben aplicarse en Stamford Health and Solution SpA para proteger la confidencialidad, integridad y autenticidad de la información, en particular los datos clínicos y personales de los 15.000 pacientes activos.

---

## 2. ALCANCE

Esta política aplica a:
- Datos en reposo (bases de datos, backups, discos)
- Datos en tránsito (comunicaciones internas y externas)
- Datos en uso (cuando aplique cifrado en memoria)
- Gestión de claves y certificados digitales
- Código firmado y comunicaciones entre sistemas

---

## 3. ALGORITMOS APROBADOS

### 3.1. Cifrado Simétrico

| Algoritmo | Uso aprobado | Longitud de clave mínima |
|-----------|-------------|--------------------------|
| **AES-256-GCM** | Cifrado de datos en reposo, backups, discos | 256 bits ✅ |
| AES-256-CBC | Cifrado de archivos (legacy compatible) | 256 bits ✅ |
| AES-128 | **Solo** en dispositivos con restricciones de recursos | 128 bits ⚠️ |
| DES / 3DES | **PROHIBIDO** — vulnerables | — ❌ |
| RC4 / RC2 | **PROHIBIDO** — vulnerables | — ❌ |

### 3.2. Cifrado Asimétrico

| Algoritmo | Uso aprobado | Longitud mínima |
|-----------|-------------|----------------|
| **RSA** | Intercambio de claves, firmas digitales, certificados | 4096 bits ✅ (2048 mínimo aceptable) |
| **ECDSA / ECDH** | Certificados TLS, autenticación SSH | Curva P-256 o superior ✅ |
| **Ed25519** | Claves SSH, firmas de código | — ✅ |
| RSA < 2048 bits | **PROHIBIDO** | — ❌ |

### 3.3. Funciones Hash

| Algoritmo | Uso aprobado |
|-----------|-------------|
| **SHA-256 / SHA-384 / SHA-512** | Integridad de archivos, firmas, contraseñas (con salt) ✅ |
| **bcrypt / Argon2id** | Hash de contraseñas de usuarios ✅ |
| MD5 / SHA-1 | **PROHIBIDO** para seguridad (solo checksums no críticos) ❌ |

### 3.4. Protocolos de Comunicación Seguros

| Protocolo | Estado |
|-----------|--------|
| **TLS 1.3** | Requerido para nuevas implementaciones ✅ |
| **TLS 1.2** | Aceptable en sistemas existentes ⚠️ |
| TLS 1.1 / 1.0 | **PROHIBIDO** — deprecado ❌ |
| SSL (todas las versiones) | **PROHIBIDO** ❌ |
| HTTP sin TLS para datos sensibles | **PROHIBIDO** ❌ |

---

## 4. CIFRADO DE DATOS EN REPOSO

| Activo | Requisito |
|--------|-----------|
| Bases de datos de pacientes (HCE, INF-002) | AES-256 obligatorio — gestionado con AWS KMS |
| Backups en AWS S3 | AES-256 con SSE-KMS obligatorio |
| Backups en cintas magnéticas | AES-256 con contraseña en bóveda corporativa |
| Discos de servidores físicos (SRV-001, SRV-002) | Cifrado de disco completo (LUKS o equivalente) |
| Endpoints corporativos (PCs, notebooks) | BitLocker con AES-256 — obligatorio desde Q1 2026 |
| Dispositivos USB corporativos | AES-256 hardware obligatorio (PSI-006) |
| Datos de pacientes en archivos temporales | AES-256; eliminación segura al terminar el proceso |

---

## 5. CIFRADO DE DATOS EN TRÁNSITO

| Comunicación | Requisito |
|-------------|-----------|
| Aplicaciones web (TechHealth, Portal Médico, HCE) | TLS 1.3 con certificado válido |
| APIs internas entre microservicios | TLS 1.2 mínimo con certificado interno |
| VPN corporativa | IKEv2/IPSec con AES-256 |
| SSH a servidores | Ed25519 o RSA-4096; **PROHIBIDO** acceso por contraseña |
| Correo electrónico con datos sensibles | TLS + cifrado de cuerpo del mensaje si contiene datos de pacientes |
| Sincronización de backups a AWS S3 | HTTPS (TLS 1.2+) + SSE-KMS |
| DICOM (imágenes médicas) | TLS 1.2+ para transmisión |

---

## 6. GESTIÓN DE CLAVES CRIPTOGRÁFICAS

### 6.1. Principios

- Toda clave criptográfica debe tener un **propietario responsable** identificado
- Las claves se almacenan exclusivamente en **AWS KMS** o en la **bóveda corporativa**
- **PROHIBIDO** almacenar claves en código fuente, repositorios, archivos de configuración sin cifrar o correo electrónico
- La pérdida o compromiso de una clave debe tratarse como un incidente de seguridad (PROC-005)

### 6.2. Ciclo de vida de claves

| Etapa | Control |
|-------|---------|
| **Generación** | Usando generadores criptográficamente seguros (CSPRNG); nunca manualmente |
| **Distribución** | Canales cifrados únicamente; nunca por correo o chat sin cifrar |
| **Almacenamiento** | AWS KMS (para claves de datos) o bóveda corporativa (para otros secretos) |
| **Rotación** | AES: anual; RSA/ECDSA (certificados): según vigencia del certificado; SSH: cada 2 años |
| **Revocación** | Inmediata ante sospecha de compromiso; notificación a todos los sistemas dependientes |
| **Destrucción** | Eliminación segura con confirmación; registro en bóveda corporativa |

### 6.3. AWS KMS

- Todas las claves de cifrado de datos de pacientes se gestionan en **AWS KMS** (región sa-east-1)
- Las políticas de IAM del KMS siguen el principio de mínimo privilegio
- La rotación automática de claves KMS está habilitada (anual)
- El acceso al KMS se registra en AWS CloudTrail

### 6.4. Certificados Digitales

- Inventario de certificados mantenido por el Administrador de Sistemas
- **Alerta de vencimiento:** 30 días antes de expiración
- **Emisión:** Let's Encrypt (públicos) o PKI interna (internos)
- Las claves privadas de certificados TLS se almacenan exclusivamente en el servidor que las usa, nunca se comparten
- Certificados caducados o revocados: eliminación inmediata

---

## 7. FIRMA DIGITAL Y NO REPUDIO

- El código fuente desplegado en producción debe ser **firmado** por el desarrollador responsable
- Los documentos contractuales o actas del SGSI pueden usar firma digital con certificado válido
- Las comunicaciones médicas que requieran no repudio usarán firma digital del profesional

---

## 8. RESPONSABILIDADES

| Rol | Responsabilidad |
|-----|----------------|
| **CISO** | Aprobar algoritmos, gestionar incidentes por compromiso de claves |
| **CTO** | Asegurar que las aplicaciones implementen los estándares definidos |
| **Administradores de Sistemas** | Mantener inventario de certificados, ejecutar rotaciones |
| **DBA** | Asegurar cifrado en reposo en bases de datos |
| **Desarrolladores** | Usar únicamente algoritmos aprobados en código nuevo |

---

## 9. EXCEPCIONES

Sistemas legados que no soporten los algoritmos aprobados deben:
1. Ser registrados en el inventario de excepciones (FORM-004)
2. Tener un plan de migración con fecha límite aprobada por el CISO
3. Implementar controles compensatorios mientras persiste la excepción

---

## 10. REFERENCIAS NORMATIVAS

- ISO/IEC 27002:2022 — Control 8.24
- NIST SP 800-57 — Recommendation for Key Management
- Ley 19.628 — Protección de datos personales
- Ley 20.584 — Confidencialidad de datos clínicos

---

## 11. REVISIÓN

Anual o cuando NIST o ISO publiquen deprecaciones de algoritmos relevantes.

**Próxima revisión:** Junio 2027

---

**Aprobado por:**

**Firma:** ___________________________  
**Nombre:** Rodrigo Vásquez Herrera  
**Cargo:** CISO  
**Fecha:** 2 de junio de 2026

---

**FIN DEL DOCUMENTO**
