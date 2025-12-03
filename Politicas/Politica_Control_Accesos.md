# POLÍTICA DE CONTROL DE ACCESOS
## Stamford Health and Solution SpA

---

**Código:** PSI-002  
**Versión:** 1.0  
**Fecha de aprobación:** 15 de noviembre de 2025  
**Aprobado por:** Comité de Seguridad de la Información  
**Propietario:** CISO  
**Clasificación:** CONFIDENCIAL - USO INTERNO

---

## 1. PROPÓSITO

Establecer los criterios y procedimientos para gestionar los accesos a los sistemas de información, aplicaciones y datos de Stamford Health and Solution SpA, garantizando que solo personas autorizadas accedan a los recursos necesarios para desempeñar sus funciones, protegin

do la confidencialidad, integridad y disponibilidad de la información.

---

## 2. ALCANCE

Esta política aplica a:
- Todos los empleados de Stamford Health
- Profesionales médicos asociados (250 usuarios)
- Contratistas y proveedores con acceso a sistemas
- Todos los sistemas de información corporativos
- Aplicaciones críticas (TechHealth Platform, HCE, portales)
- Bases de datos
- Infraestructura de servidores y red
- Servicios en la nube (AWS)

---

## 3. PRINCIPIOS FUNDAMENTALES

### 3.1. Necesidad de Conocer (Need-to-Know)
Los usuarios tendrán acceso únicamente a la información estrictamente necesaria para realizar sus funciones.

### 3.2. Privilegio Mínimo (Least Privilege)
Los usuarios recibirán los permisos mínimos necesarios para desempeñar sus tareas.

### 3.3. Separación de Funciones (Segregation of Duties)
Las funciones críticas serán distribuidas entre diferentes usuarios para evitar conflictos de interés y fraude.

### 3.4. Revisión Periódica
Los accesos serán revisados trimestralmente para asegurar que permanezcan apropiados y vigentes.

---

## 4. GESTIÓN DE IDENTIDADES

### 4.1. Proceso de Alta de Usuarios

**Responsable:** Administrador de Seguridad, con aprobación del Propietario del Activo

**Procedimiento:**
1. RRHH notifica incorporación de nuevo usuario (Formulario FORM-001)
2. Jefe directo define perfil de acceso requerido
3. Propietario del activo aprueba solicitud
4. Administrador crea cuenta con perfil aprobado
5. Usuario recibe credenciales temporales
6. Usuario completa capacitación de seguridad
7. Usuario activa cuenta y cambia contraseña

**Plazo:** 24 horas desde aprobación

**Documentación:** Formulario de Solicitud de Acceso (FORM-001) archivado 5 años

### 4.2. Proceso de Modificación de Accesos

**Cuándo aplicar:**
- Cambio de rol o posición
- Cambio de responsabilidades
- Necesidad de acceso adicional temporal
- Retiro de accesos ya no necesarios

**Procedimiento:**
1. Usuario o jefe directo solicita modificación
2. Propietario del activo aprueba
3. Administrador ejecuta cambio
4. Usuario es notificado
5. Modificación es registrada en log de auditoría

**Plazo:** 24 horas (cambios urgentes), 72 horas (cambios rutinarios)

### 4.3. Proceso de Baja de Usuarios

**Cuándo aplicar:**
- Término de contrato laboral
- Renuncia
- Cambio de rol que no requiere accesos anteriores

**Procedimiento:**
1. RRHH notifica baja de usuario (inmediato al término de relación laboral)
2. Administrador desactiva cuenta en <4 horas
3. Accesos a sistemas críticos se revocan inmediatamente
4. Después de 30 días, cuenta es eliminada (backup de datos personales del usuario)
5. Equipo físico es recuperado
6. Firma de acta de devolución de activos

**Plazo crítico:** Desactivación en 4 horas (empleados) o inmediato (casos disciplinarios)

---

## 5. AUTENTICACIÓN

### 5.1. Credenciales de Acceso

**Cuentas Personales:**
- Cada usuario tendrá una cuenta única y personal
- **PROHIBIDO** compartir credenciales bajo cualquier circunstancia
- Las cuentas son responsabilidad del usuario titular

**Formato de Nombres de Usuario:**
- Formato: `nombre.apellido` (e.g., juan.perez)
- Para usuarios médicos externos: `med.nombre.apellido`
- Cuentas de servicio: `svc-nombreservicio`

### 5.2. Política de Contraseñas

**Requisitos Mínimos:**
- **Longitud mínima:** 12 caracteres
- **Complejidad:** Al menos 3 de 4 categorías:
  - Mayúsculas (A-Z)
  - Minúsculas (a-z)
  - Números (0-9)
  - Caracteres especiales (!@#$%^&*)
- **Historial:** No reutilizar últimas 5 contraseñas
- **Expiración:** 90 días (usuarios estándar), 60 días (usuarios privilegiados)
- **Bloqueo temporal:** Tras 5 intentos fallidos (15 minutos)
- **Bloqueo permanente:** Tras 10 intentos fallidos (requiere reset por administrador)

**Prohibiciones:**
- Palabras del diccionario
- Información personal obvia (nombre, fecha nacimiento, RUT)
- Secuencias simples (123456, abcdef, qwerty)
- Contraseñas por defecto de sistemas

**Almacenamiento:**
- Las contraseñas DEBEN almacenarse cifradas (hash + salt)
- PROHIBIDO anotar contraseñas en papel o archivos sin cifrar
- Uso de administrador de contraseñas corporativo (recomendado)

**Contraseñas Temporales:**
- Validez máxima: 24 horas
- Cambio obligatorio al primer inicio de sesión
- No reutilizable

### 5.3. Autenticación Multifactor (MFA)

**Obligatorio para:**
- Acceso al Sistema de Historias Clínicas Electrónicas (HCE)
- Portal Médico (APP-004)
- Microsoft 365
- Acceso VPN desde fuera de la red corporativa
- Todos los accesos administrativos y privilegiados
- Acceso a AWS Console
- Acceso remoto a servidores

**Métodos aceptados:**
- Aplicación autenticadora (Google Authenticator, Microsoft Authenticator)
- SMS a número registrado (solo como segundo factor)
- Token físico (para administradores)
- Biometría (cuando esté disponible)

**No aceptado:**
- Email como único segundo factor
- Pregunta de seguridad

**Implementación:** Q1 2026 (antes de 31 de marzo 2026)

### 5.4. Inicio de Sesión Único (SSO)

- Se implementará SSO basado en Active Directory para aplicaciones corporativas
- Los usuarios se autenticarán una vez y accederán a múltiples sistemas sin reingresar credenciales
- SSO no exime de MFA cuando este sea requerido

---

## 6. GESTIÓN DE ACCESOS PRIVILEGIADOS

### 6.1. Definición de Usuario Privilegiado

Son usuarios privilegiados aquellos con:
- Acceso administrativo a servidores (root, Administrator)
- Acceso a consolas de administración de bases de datos
- Capacidad de modificar configuraciones de seguridad
- Acceso a herramientas de auditoría o monitoreo
- Permisos de aprobación de cambios críticos

**Usuarios privilegiados identificados:**
- Administradores de sistemas (3 usuarios)
- Administradores de bases de datos - DBA (2 usuarios)
- Administradores de red (2 usuarios)
- CISO
- CTO

### 6.2. Controles Adicionales

**Aprobación:**
- Toda solicitud de acceso privilegiado requiere aprobación escrita del CISO
- Revisión y revalidación trimestral obligatoria

**Uso:**
- Usar cuentas privilegiadas SOLO cuando sea estrictamente necesario
- Para tareas administrativas rutinarias, usar cuenta estándar
- Principio de "doble cuenta": Cuenta administrativa + Cuenta usuario estándar

**Monitoreo:**
- 100% de acciones con cuentas privilegiadas son registradas en logs
- Revisión semanal de logs de accesos privilegiados por Coordinador de Seguridad
- Alertas automáticas por uso fuera de horario laboral

**Acceso a Producción:**
- Acceso a servidores de producción requiere aprobación previa (ticket)
- Sesiones administrativas limitadas a 4 horas (extensión requiere nueva aprobación)
- Uso de ventana de cambios autorizadas (change window)

**Contraseñas Privilegiadas:**
- Cambio cada 60 días (vs 90 días usuarios estándar)
- Complejidad aumentada: Mínimo 16 caracteres
- Uso de bóveda de contraseñas (Password Vault) obligatorio

---

## 7. CONTROL DE ACCESO FÍSICO

### 7.1. Data Center

**Acceso Autorizado:**
- Personal de TI designado (5 personas)
- CISO
- Proveedores (solo con escolta)

**Controles:**
- Tarjeta de acceso con registro de entradas/salidas
- CCTV 24/7 con retención de 90 días
- Implementar biometría (antes de Q2 2026)
- Bitácora manual de visitas

**Horario:**
- Personal autorizado: 24/7
- Proveedores: Solo horario laboral (9:00-18:00) con autorización previa

### 7.2. Oficinas Corporativas

**Control de Acceso:**
- Tarjeta de acceso para empleados
- Visitantes registran en recepción
- Áreas restringidas identificadas con señalética

**Política de Escritorio Limpio:**
- No dejar documentos confidenciales en escritorio al finalizar jornada
- Bloquear pantalla al ausentarse (Win+L o Ctrl+Alt+Del)
- No dejar credenciales de acceso visibles

---

## 8. CONTROL DE ACCESO LÓGICO

### 8.1. Segmentación de Red

**VLANs Definidas:**
- VLAN 10: Servidores de Producción (acceso restringido)
- VLAN 20: Servidores de Desarrollo/QA
- VLAN 30: Estaciones de trabajo administrativas
- VLAN 40: Estaciones de trabajo estándar
- VLAN 50: WiFi corporativa (segmentada de producción)
- VLAN 60: WiFi invitados (sin acceso a red interna)
- VLAN 70: Dispositivos IoT (cámaras, sensores)

**Reglas de Firewall:**
- Denegar todo por defecto (default deny)
- Permitir solo tráfico específicamente autorizado
- No comunicación directa entre VLAN 50/60 y VLAN 10
- Auditoría de reglas de firewall trimestral

### 8.2. Acceso Remoto

**VPN Obligatoria:**
- Todo acceso remoto a red corporativa debe usar VPN
- VPN configurada con split-tunneling deshabilitado
- MFA obligatorio para conexión VPN
- Antivirus actualizado requerido en dispositivo remoto

**Acceso desde Dispositivos Personales (BYOD):**
- Política: **PROHIBIDO** acceso a sistemas de producción desde dispositivos personales
- Excepción: Portales web públicos con MFA (e.g., Webmail)
- Médicos externos: Acceso solo vía Portal Médico (APP-004) con MFA

### 8.3. Control de Acceso a Bases de Datos

**Acceso Directo:**
- PROHIBIDO acceso directo a bases de datos desde estaciones de trabajo
- Acceso solo vía aplicaciones autorizadas
- DBAs pueden acceder con cuentas privilegiadas desde servidor de salto (jump server)

**Consultas:**
- Queries de lectura masiva requieren aprobación del DBA
- Exportaciones de datos requieren aprobación del Propietario del Activo + CISO
- Logs de todas las consultas a tablas con datos sensibles

---

## 9. REVISIÓN Y CERTIFICACIÓN DE ACCESOS

### 9.1. Revisión Trimestral

**Proceso:**
1. Coordinador de Seguridad genera reporte de accesos por sistema
2. Reporte es enviado a Propietarios de Activos
3. Propietarios revisan y certifican accesos vigentes en 10 días hábiles
4. Accesos no certificados son desactivados automáticamente
5. Resultados son presentados al Comité de Seguridad

**Información Revisada:**
- Lista de usuarios con acceso
- Nivel de privilegios
- Fecha de último uso
- Fecha de última revisión
- Justificación de negocio

### 9.2. Revisión de Cuentas Inactivas

**Definición de Inactividad:**
- Usuario no ha iniciado sesión en 60 días

**Acción:**
- Día 60: Notificación automática al usuario y jefe directo
- Día 75: Desactivación automática de cuenta
- Día 90: Eliminación de cuenta (con backup de datos del usuario)

**Excepciones:**
- Cuentas de servicio (revisión anual)
- Usuarios con licencia médica o vacaciones prolongadas (notificación previa a RRHH)

### 9.3. Auditoría de Accesos Privilegiados

**Frecuencia:** Mensual

**Auditoría incluye:**
- Lista de usuarios privilegiados actualizada
- Justificación de cada acceso privilegiado
- Revisión de logs de uso de cuentas privilegiadas
- Identificación de accesos privilegiados no utilizados en 30 días
- Verificación de cumplimiento de controles adicionales

---

## 10. MONITOREO Y DETECCIÓN

### 10.1. Eventos a Monitorear

**Tiempo Real (Alertas Inmediatas):**
- Intentos de acceso fuera de horario laboral (cuentas privilegiadas)
- Múltiples intentos fallidos de inicio de sesión
- Acceso simultáneo desde ubicaciones geográficamente distantes
- Escalamiento de privilegios
- Acceso a sistemas desde ubicaciones no autorizadas

**Revisión Diaria:**
- Accesos exitosos con cuentas privilegiadas
- Cambios en permisos de usuarios
- Creación de nuevas cuentas

**Revisión Semanal:**
- Tendencias de acceso inusuales
- Cuentas con privilegios excesivos

### 10.2. Logs de Auditoría

**Retención:**
- Logs de acceso a sistemas críticos: 1 año
- Logs de acceso con cuentas privilegiadas: 3 años
- Logs de acceso a historias clínicas: 7 años (Ley 20.584)

**Protección:**
- Logs almacenados en servidor centralizado (solo lectura)
- Respaldo diario de logs
- Logs de seguridad cifrados

---

## 11. CASOS ESPECIALES

### 11.1. Acceso de Emergencia

**Situación:** Incidente crítico que requiere acceso inmediato fuera del procedimiento normal

**Proceso:**
1. CISO o CTO (en ausencia del CISO) autorizan verbalmente
2. Acceso es otorgado con cuenta de emergencia (break-glass account)
3. Todas las acciones son registradas en log de auditoría
4. Dentro de 24 horas: Documentación formal del incidente y justificación
5. Revisión por Comité de Seguridad en próxima reunión

**Cuentas de Emergencia:**
- Contraseña almacenada en sobre sellado (en caja fuerte)
- Apertura del sobre requiere 2 testigos
- Contraseña se cambia después de cada uso

### 11.2. Acceso de Terceros (Proveedores)

**Tipos de Acceso:**
- **Presencial:** Proveedor en sitio con escolta
- **Remoto:** VPN con credenciales temporales

**Requisitos:**
- Contrato con cláusulas de confidencialidad (NDA)
- Aprobación del CISO para acceso remoto
- Acceso limitado al alcance del servicio contratado
- Duración limitada (máximo 30 días, renovable)
- Monitoreo de sesiones
- Desactivación inmediata al término del servicio

**Proveedores de Servicios Críticos:**
- AWS: Acceso gestionado vía IAM con MFA
- Microsoft: Acceso con cuenta corporativa
- Proveedores de mantenimiento: Solo acceso presencial con escolta

### 11.3. Acceso de Auditores

**Auditorías Internas:**
- Acceso de solo lectura a sistemas y logs
- Aprobación del CISO

**Auditorías Externas:**
- Acceso según alcance de auditoría
- Aprobación del Comité de Seguridad
- NDA firmado
- Acceso supervisado

---

## 12. RESPONSABILIDADES

### 12.1. Usuarios

- Proteger sus credenciales de acceso
- No compartir cuentas bajo ninguna circunstancia
- Reportar inmediatamente sospechas de compromiso de cuenta
- Cerrar sesión al ausentarse del equipo
- Cumplir con política de contraseñas

### 12.2. Jefes Directos

- Solicitar accesos apropiados para su equipo
- Notificar cambios en roles o responsabilidades
- Notificar inmediatamente término de relación laboral

### 12.3. Propietarios de Activos

- Aprobar o rechazar solicitudes de acceso
- Revisar y certificar accesos trimestralmente
- Definir niveles de acceso apropiados

### 12.4. Administradores de Sistemas

- Implementar solicitudes de acceso aprobadas en plazo
- Desactivar cuentas según procedimiento
- Mantener logs de auditoría
- Generar reportes de acceso para revisiones

### 12.5. CISO

- Aprobar accesos privilegiados
- Supervisar cumplimiento de esta política
- Revisar logs de auditoría
- Investigar violaciones a la política

---

## 13. SANCIONES

Las violaciones a esta política pueden resultar en:

**Violaciones Leves:**
- Compartir contraseña (primera vez): Amonestación escrita + capacitación obligatoria
- No cerrar sesión: Advertencia verbal

**Violaciones Graves:**
- Compartir contraseña (reincidencia): Suspensión temporal
- Acceso no autorizado intencional: Suspensión o terminación de contrato
- Uso indebido de accesos privilegiados: Terminación de contrato + acciones legales

**Todas las violaciones son reportadas al Comité de Seguridad.**

---

## 14. EXCEPCIONES

Excepciones a esta política deben:
- Ser solicitadas por escrito al CISO
- Incluir justificación de negocio
- Definir controles compensatorios
- Tener aprobación del Comité de Seguridad
- Ser temporales (máximo 90 días, renovable)
- Ser documentadas en registro de excepciones

---

## 15. DOCUMENTOS RELACIONADOS

- PSI-001: Política de Seguridad de la Información (principal)
- PROC-003: Procedimiento de Gestión de Accesos
- FORM-001: Formulario de Solicitud de Acceso
- FORM-002: Formulario de Revisión de Accesos

---

## 16. REFERENCIAS NORMATIVAS

- ISO/IEC 27002:2022 - Controles 5.15, 5.16, 5.17, 5.18, 8.2, 8.3, 8.5
- Ley 19.628 - Artículos sobre acceso a datos personales
- Ley 20.584 - Artículo 12 (reserva de información clínica)

---

## 17. REVISIÓN

Esta política será revisada anualmente o cuando cambien las circunstancias tecnológicas u organizacionales.

**Próxima revisión:** Noviembre de 2026

---

**Aprobado por:**

**Firma:** ___________________________  
**Nombre:** [CISO]  
**Fecha:** 15 de noviembre de 2025

---

**FIN DEL DOCUMENTO**
