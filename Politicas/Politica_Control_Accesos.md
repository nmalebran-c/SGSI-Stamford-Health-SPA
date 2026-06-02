# POLÍTICA DE CONTROL DE ACCESOS
## Stamford Health and Solution SpA

---

**Código:** PSI-002  
**Versión:** 1.1  
**Fecha de aprobación:** 15 de noviembre de 2025  
**Fecha de última actualización:** 2 de junio de 2026  
**Aprobado por:** Comité de Seguridad de la Información  
**Propietario:** CISO  
**Clasificación:** CONFIDENCIAL - USO INTERNO

---

## CONTROL DE CAMBIOS

| Versión | Fecha | Descripción del Cambio |
|---------|-------|------------------------|
| 1.0 | 15/11/2025 | Versión inicial aprobada |
| 1.1 | 02/06/2026 | Incorporación de: gestión de secretos y API keys, procedimiento ante compromiso de credenciales, matriz de accesos por clasificación de activo, ciclo de vida de cuentas de servicio, procedimiento diferenciado para médicos externos, KPIs de cumplimiento, integración con gestión de incidentes y aplicación concreta Ley 19.628 |

---

## 1. PROPÓSITO

Establecer los criterios y procedimientos para gestionar los accesos a los sistemas de información, aplicaciones y datos de Stamford Health and Solution SpA, garantizando que solo personas autorizadas accedan a los recursos necesarios para desempeñar sus funciones, protegiendo la confidencialidad, integridad y disponibilidad de la información.

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

### 3.5. Proporcionalidad al Riesgo
Los controles de acceso serán proporcionales al valor, sensibilidad y criticidad del activo protegido, de acuerdo a la clasificación definida en la sección 3.6.

### 3.6. Matriz de Clasificación de Accesos

Los sistemas se clasifican en tres niveles de criticidad que determinan los controles mínimos obligatorios:

| Nivel | Clasificación | Sistemas | Controles Mínimos |
|-------|--------------|----------|-------------------|
| **Nivel 3 — Crítico** | Datos clínicos, datos personales sensibles | HCE, bases de datos de pacientes, AWS (producción) | MFA obligatorio, acceso privilegiado con ticket, logs 7 años, revisión mensual |
| **Nivel 2 — Restringido** | Información corporativa confidencial | TechHealth Platform, Microsoft 365, VPN, servidores internos | MFA obligatorio, logs 3 años, revisión trimestral |
| **Nivel 1 — Interno** | Información operacional general | Portal web, correo corporativo, herramientas colaborativas | Contraseña fuerte, logs 1 año, revisión trimestral |

Todo acceso a sistemas Nivel 3 requiere base legal válida bajo la Ley 19.628 y la Ley 20.584 (ver sección 17).

---

## 4. GESTIÓN DE IDENTIDADES

### 4.1. Proceso de Alta de Usuarios

**Responsable:** Administrador de Seguridad, con aprobación del Propietario del Activo

**Procedimiento:**
1. RRHH notifica incorporación de nuevo usuario (Formulario FORM-001)
2. Jefe directo define perfil de acceso requerido según rol y nivel de clasificación del sistema
3. Propietario del activo aprueba solicitud
4. Administrador crea cuenta con perfil aprobado
5. Usuario recibe credenciales temporales
6. Usuario completa capacitación de seguridad
7. Usuario activa cuenta y cambia contraseña

**Plazo:** 24 horas desde aprobación

**Documentación:** Formulario de Solicitud de Acceso (FORM-001) archivado 5 años

### 4.2. Proceso de Modificación de Accesos

**Cuándo aplicar:**
- Cambio de rol, posición o departamento
- Cambio de responsabilidades
- Necesidad de acceso adicional temporal
- Retiro de accesos ya no necesarios

**Principio de revocación por cambio de departamento:** Cuando un usuario cambia de área, todos los accesos del área anterior son revocados automáticamente al momento de la transferencia, sin necesidad de solicitud adicional. El nuevo jefe directo solicita los accesos del nuevo rol mediante FORM-001.

**Procedimiento:**
1. RRHH o jefe directo notifica cambio (Formulario FORM-001)
2. Propietario del activo del área de origen revoca accesos anteriores
3. Propietario del activo del área de destino aprueba nuevos accesos
4. Administrador ejecuta los cambios en un solo ciclo
5. Usuario es notificado de los accesos revocados y otorgados
6. Modificación es registrada en log de auditoría

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

### 4.4. Ciclo de Vida de Cuentas de Servicio

Las cuentas de servicio (formato `svc-nombreservicio`) requieren controles específicos dado que no corresponden a un usuario humano:

**Creación:**
- Requiere aprobación del CISO
- Debe tener un propietario responsable identificado (persona natural)
- El propietario es responsable de la actividad de la cuenta de servicio
- Documentada en el Registro de Cuentas de Servicio (FORM-005)

**Controles:**
- Permisos mínimos estrictamente necesarios para la función automatizada
- Contraseñas o tokens gestionados exclusivamente en la bóveda corporativa
- Rotación de credenciales cada 90 días como mínimo (o al cambio de propietario)
- Las cuentas de servicio no tienen acceso interactivo habilitado (login deshabilitado)
- No se aplican a las reglas de inactividad de 60 días (ver sección 9.2)

**Revisión:**
- Revisión anual por el propietario responsable, con revalidación ante el CISO
- Al término de la integración o servicio: eliminación inmediata de la cuenta y sus credenciales

### 4.5. Proceso de Alta de Profesionales Médicos Externos

Los 250 profesionales médicos asociados tienen un procedimiento diferenciado debido a su naturaleza de usuarios externos con acceso a datos clínicos de Nivel 3.

**Responsable de aprobación:** Jefe de Área Clínica correspondiente + CISO

**Procedimiento:**
1. Jefe de Área Clínica solicita el alta mediante FORM-006 (Formulario de Acceso Médico Externo)
2. RRHH verifica vigencia del contrato o convenio con el profesional
3. CISO aprueba el perfil de acceso (restringido al Portal Médico APP-004 y HCE de sus pacientes)
4. Administrador crea cuenta con formato `med.nombre.apellido`
5. Profesional recibe credenciales temporales y completa capacitación de 30 minutos sobre manejo de datos clínicos y Ley 20.584
6. Profesional activa MFA antes del primer acceso a HCE

**Restricciones aplicables a médicos externos:**
- Acceso exclusivamente vía Portal Médico (APP-004) con MFA
- Acceso restringido a los registros clínicos de sus propios pacientes atendidos en Stamford Health
- Acceso desde dispositivos personales: solo vía Portal Médico con MFA (PROHIBIDO acceso directo a HCE)
- Sesiones limitadas a 8 horas continuas

**Médicos que rotan entre centros o especialidades:**
- El Jefe de Área Clínica de origen revoca el acceso al área anterior
- El Jefe de Área Clínica de destino solicita el nuevo perfil mediante FORM-006
- Plazo de actualización: 24 horas

**Vigencia:** El acceso tiene vigencia igual a la del contrato o convenio. RRHH notifica al Administrador con 5 días de anticipación al vencimiento para desactivación.

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

### 6.3. Gestión de Secretos, API Keys y Tokens de Integración

Los secretos de aplicación son credenciales no humanas que otorgan acceso programático a sistemas y deben recibir el mismo nivel de protección que las contraseñas privilegiadas.

**Tipos de secretos bajo esta política:**
- AWS IAM Access Keys y Secret Access Keys
- Tokens de integración entre sistemas (TechHealth ↔ HCE, TechHealth ↔ AWS)
- Certificados digitales TLS/SSL y claves privadas asociadas
- Claves de API de servicios de terceros (Microsoft, proveedores externos)
- Secrets de bases de datos usados por aplicaciones

**Controles obligatorios:**
- Todo secreto debe estar registrado en la bóveda corporativa (Password Vault) con su propietario responsable, sistema al que otorga acceso y fecha de expiración
- **PROHIBIDO** almacenar secretos en código fuente, repositorios git, archivos de configuración sin cifrar o mensajería
- Las AWS IAM Access Keys de larga duración están **PROHIBIDAS**; se utilizarán IAM Roles con credenciales temporales (STS AssumeRole) para todos los servicios
- Rotación de secretos: cada 90 días o inmediatamente ante sospecha de compromiso

**Certificados digitales:**
- Inventario de certificados mantenido por el Administrador de Sistemas
- Renovación gestionada con 30 días de anticipación al vencimiento
- Claves privadas almacenadas en AWS KMS o bóveda corporativa; nunca en texto plano

**Al término de una integración o servicio:**
- Revocación inmediata del secreto o API key
- Eliminación del registro en la bóveda
- Rotación de credenciales en todos los sistemas que pudieran haber tenido exposición

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
- Cuentas de servicio (revisión anual, ver sección 4.4)
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
- Uso de secretos o API keys fuera del sistema registrado como propietario

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

### 10.3. Integración con Gestión de Incidentes

Cuando el monitoreo detecta un evento de seguridad relacionado con accesos, se activa el procedimiento de gestión de incidentes definido en **PROC-005: Procedimiento de Respuesta a Incidentes de Seguridad**.

**Clasificación de eventos y escalamiento:**

| Tipo de Evento | Clasificación | Acción Inmediata |
|---------------|---------------|------------------|
| Acceso no autorizado confirmado a HCE | Crítico | Desactivación de cuenta + activación PROC-005 en ≤15 min |
| Escalamiento de privilegios no autorizado | Alto | Alerta al CISO + investigación en ≤1 hora |
| Múltiples intentos fallidos de login | Medio | Bloqueo automático + notificación al Coordinador de Seguridad |
| Acceso fuera de horario (cuentas estándar) | Bajo | Registro y revisión al día siguiente |

**Responsable de escalamiento:** Coordinador de Seguridad activa PROC-005; en su ausencia, el CISO.

---

## 11. RESPUESTA ANTE COMPROMISO DE CREDENCIALES

### 11.1. Detección y Reporte

**El usuario debe reportar inmediatamente** si sospecha que sus credenciales han sido comprometidas. El reporte se realiza:
- En horario laboral: al Coordinador de Seguridad en persona o al correo `seguridad@stamfordhealth.cl`
- Fuera de horario: al número de guardia de seguridad TI (ext. 911 interna o celular de guardia publicado en la intranet)

**Indicadores de compromiso a reportar:**
- Inicio de sesión exitoso desde ubicación o dispositivo desconocido
- Notificación de cambio de contraseña no solicitado
- Actividad en sistemas en horario en que el usuario no estaba conectado
- Solicitud de MFA no iniciada por el usuario

### 11.2. Procedimiento de Respuesta

1. **Contención inmediata (0–15 minutos):**
   - Coordinador de Seguridad invalida todas las sesiones activas del usuario afectado
   - Fuerza cambio de contraseña en el próximo inicio de sesión
   - Revoca temporalmente tokens MFA registrados y solicita re-enrolamiento
   - Si el compromiso involucra una cuenta privilegiada: desactivación inmediata hasta investigación completada

2. **Investigación inicial (15 min – 4 horas):**
   - Revisión de logs de los últimos 30 días de la cuenta afectada
   - Identificación del vector de compromiso (phishing, reutilización de contraseña, malware)
   - Determinación del alcance: qué sistemas fueron accedidos con las credenciales comprometidas

3. **Recuperación (4–24 horas):**
   - Restablecimiento de accesos con nuevas credenciales
   - Re-enrolamiento MFA verificado en persona o por videoconferencia
   - Revisión de cambios realizados con la cuenta comprometida durante el período de exposición

4. **Notificación regulatoria:**
   - Si el compromiso afectó datos personales (Ley 19.628) o datos clínicos (Ley 20.584): el CISO evalúa en ≤24 horas si corresponde notificación a la autoridad competente
   - Notificación a pacientes afectados según lo exija la normativa aplicable

5. **Documentación:**
   - Registro del incidente en el sistema de gestión de incidentes
   - Informe post-incidente al Comité de Seguridad en ≤72 horas

---

## 12. CASOS ESPECIALES

### 12.1. Acceso de Emergencia

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

### 12.2. Acceso de Terceros (Proveedores)

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

### 12.3. Acceso de Auditores

**Auditorías Internas:**
- Acceso de solo lectura a sistemas y logs
- Aprobación del CISO

**Auditorías Externas:**
- Acceso según alcance de auditoría
- Aprobación del Comité de Seguridad
- NDA firmado
- Acceso supervisado

---

## 13. RESPONSABILIDADES

### 13.1. Usuarios

- Proteger sus credenciales de acceso
- No compartir cuentas bajo ninguna circunstancia
- Reportar inmediatamente sospechas de compromiso de cuenta al Coordinador de Seguridad (ver sección 11)
- Cerrar sesión al ausentarse del equipo
- Cumplir con política de contraseñas

### 13.2. Jefes Directos

- Solicitar accesos apropiados para su equipo
- Notificar cambios en roles, responsabilidades o departamento
- Notificar inmediatamente término de relación laboral

### 13.3. Propietarios de Activos

- Aprobar o rechazar solicitudes de acceso
- Revisar y certificar accesos trimestralmente
- Definir niveles de acceso apropiados según clasificación del activo

### 13.4. Administradores de Sistemas

- Implementar solicitudes de acceso aprobadas en plazo
- Desactivar cuentas según procedimiento
- Mantener logs de auditoría
- Generar reportes de acceso para revisiones
- Mantener el inventario de cuentas de servicio y secretos en la bóveda corporativa

### 13.5. CISO

- Aprobar accesos privilegiados y de médicos externos
- Supervisar cumplimiento de esta política
- Revisar logs de auditoría
- Investigar violaciones a la política
- Evaluar notificaciones regulatorias ante compromiso de datos

---

## 14. SANCIONES

Las violaciones a esta política pueden resultar en:

**Violaciones Leves:**
- Compartir contraseña (primera vez): Amonestación escrita + capacitación obligatoria
- No cerrar sesión: Advertencia verbal

**Violaciones Graves:**
- Compartir contraseña (reincidencia): Suspensión temporal
- Acceso no autorizado intencional: Suspensión o terminación de contrato
- Uso indebido de accesos privilegiados: Terminación de contrato + acciones legales
- Almacenamiento de secretos o API keys fuera de la bóveda corporativa (reincidencia): Suspensión temporal

**Todas las violaciones son reportadas al Comité de Seguridad.**

---

## 15. EXCEPCIONES

Excepciones a esta política deben:
- Ser solicitadas por escrito al CISO
- Incluir justificación de negocio
- Definir controles compensatorios
- Tener aprobación del Comité de Seguridad
- Ser temporales (máximo 90 días, renovable)
- Ser documentadas en registro de excepciones

---

## 16. INDICADORES DE CUMPLIMIENTO (KPIs)

El Coordinador de Seguridad medirá mensualmente los siguientes indicadores y los presentará trimestralmente al Comité de Seguridad:

| Indicador | Fórmula | Meta |
|-----------|---------|------|
| Tasa de certificación trimestral | Accesos certificados / Total accesos revisados × 100 | ≥ 95% |
| Tiempo promedio de desactivación en baja | Promedio de horas entre notificación RRHH y desactivación de cuenta | ≤ 4 horas |
| Cuentas inactivas detectadas | N° de cuentas desactivadas por inactividad en el período | Tendencia decreciente |
| Cobertura de bóveda de contraseñas | Usuarios privilegiados con bóveda activa / Total usuarios privilegiados × 100 | 100% |
| Secretos sin propietario registrado | N° de API keys o secretos sin propietario en la bóveda | 0 |
| Cobertura MFA en sistemas Nivel 3 | Usuarios con MFA activo en HCE / Total usuarios HCE × 100 | 100% (desde Q1 2026) |
| Accesos privilegiados no utilizados en 30 días | N° de cuentas privilegiadas sin uso en el último mes | 0 |
| Tiempo de respuesta ante compromiso de credenciales | Tiempo desde reporte hasta contención (sesión invalidada) | ≤ 15 minutos |

Los KPIs son insumo para la revisión de eficacia del SGSI según ISO/IEC 27001 Cláusula 9.1.

---

## 17. CUMPLIMIENTO NORMATIVO

### 17.1. Ley 19.628 — Protección de Datos Personales

El acceso a datos personales almacenados en los sistemas de Stamford Health requiere base legal válida. En el contexto de esta política:

- **Empleados:** el acceso a datos personales de pacientes está justificado por la relación contractual laboral y las funciones expresamente asignadas; no se requiere consentimiento adicional, pero el acceso debe limitarse al mínimo necesario para la función.
- **Médicos externos:** el acceso a datos clínicos de pacientes que no son suyos está **PROHIBIDO**. El acceso a datos de sus propios pacientes está justificado por la relación médico-paciente y el consentimiento de atención.
- **Terceros y proveedores:** solo acceden a datos personales en el marco de un contrato que incluya cláusulas de tratamiento de datos y confidencialidad, y únicamente en el alcance mínimo necesario para el servicio.
- Cualquier exportación o transferencia de datos personales a sistemas externos requiere evaluación legal previa y aprobación del CISO.

### 17.2. Ley 20.584 — Derechos y Deberes de los Pacientes

- Los registros clínicos electrónicos (HCE) tienen carácter reservado conforme al Artículo 12 de la Ley 20.584.
- El acceso a HCE está restringido al equipo de salud tratante y al personal administrativo con función explícita que lo justifique.
- Los logs de acceso a HCE se conservan durante 7 años (ver sección 10.2).
- Cualquier acceso a HCE por parte de personas distintas al equipo tratante requiere autorización escrita del paciente o mandato judicial.

---

## 18. DOCUMENTOS RELACIONADOS

- PSI-001: Política de Seguridad de la Información (principal)
- PROC-003: Procedimiento de Gestión de Accesos
- PROC-005: Procedimiento de Respuesta a Incidentes de Seguridad
- FORM-001: Formulario de Solicitud de Acceso
- FORM-002: Formulario de Revisión de Accesos
- FORM-005: Formulario de Registro de Cuentas de Servicio
- FORM-006: Formulario de Acceso Médico Externo

---

## 19. REFERENCIAS NORMATIVAS

- ISO/IEC 27002:2022 - Controles 5.15, 5.16, 5.17, 5.18, 8.2, 8.3, 8.5
- ISO/IEC 27001:2022 - Cláusula 9.1 (Seguimiento, medición, análisis y evaluación)
- Ley 19.628 - Protección de la vida privada y datos personales
- Ley 20.584 - Artículo 12 (reserva de información clínica)

---

## 20. REVISIÓN

Esta política será revisada anualmente o cuando cambien las circunstancias tecnológicas u organizacionales.

**Próxima revisión:** Noviembre de 2026

---

**Aprobado por:**

**Firma:** ___________________________  
**Nombre:** Rodrigo Vásquez Herrera  
**Cargo:** Chief Information Security Officer (CISO)  
**Fecha:** 15 de noviembre de 2025

---

**FIN DEL DOCUMENTO**
