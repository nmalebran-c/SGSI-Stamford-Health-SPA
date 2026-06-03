# PROCEDIMIENTO DE GESTIÓN DE ACCESOS
## Stamford Health and Solution SpA

---

**Código:** PROC-003  
**Versión:** 1.0  
**Fecha de aprobación:** 2 de junio de 2026  
**Aprobado por:** Comité de Seguridad de la Información  
**Propietario:** CISO  
**Clasificación:** CONFIDENCIAL - USO INTERNO  
**Política asociada:** PSI-002 — Política de Control de Accesos

---

## CONTROL DE CAMBIOS

| Versión | Fecha | Descripción |
|---------|-------|-------------|
| 1.0 | 02/06/2026 | Versión inicial |

---

## 1. PROPÓSITO

Definir los pasos operacionales para ejecutar las solicitudes de alta, modificación, baja y revisión de accesos a los sistemas de información de Stamford Health and Solution SpA, garantizando trazabilidad, aprobaciones formales y cumplimiento de la PSI-002 en cada operación.

---

## 2. ALCANCE

Aplica a todos los accesos lógicos sobre:
- Sistemas corporativos y aplicaciones (Nivel 1, 2 y 3)
- Cuentas de usuario estándar, privilegiadas y de servicio
- Accesos de empleados, médicos externos, contratistas y proveedores

---

## 3. ROLES Y RESPONSABILIDADES

| Rol | Responsabilidad |
|-----|----------------|
| **Solicitante / Jefe Directo** | Iniciar solicitud y definir el perfil requerido |
| **RRHH** | Notificar altas, cambios de área y bajas; verificar contratos |
| **Propietario del Activo** | Aprobar accesos sobre sus sistemas |
| **CISO** | Aprobar accesos privilegiados y accesos a sistemas Nivel 3 |
| **Administrador de Sistemas** | Ejecutar los cambios técnicos en los plazos establecidos |
| **Coordinador de Seguridad** | Supervisar cumplimiento, gestionar revisiones trimestrales |

---

## 4. PROCEDIMIENTO DE ALTA DE USUARIO

### Flujo

```
RRHH notifica alta
       │
       ▼
Jefe Directo completa FORM-001
       │
       ▼
Propietario del Activo aprueba (Nivel 2 y 3)
       │
       ▼
CISO aprueba (si Nivel 3 o acceso privilegiado)
       │
       ▼
Administrador ejecuta en ≤ 24 horas
       │
       ▼
Usuario recibe credenciales temporales
       │
       ▼
Usuario cambia contraseña y activa MFA
       │
       ▼
Registro en log de auditoría
```

### Pasos detallados

| Paso | Acción | Responsable | Herramienta | Plazo |
|------|--------|------------|-------------|-------|
| 1 | RRHH notifica incorporación mediante FORM-001 | RRHH | Correo + FORM-001 | Día 0 |
| 2 | Jefe Directo define perfil de acceso requerido y firma FORM-001 | Jefe Directo | FORM-001 | Día 0 |
| 3 | Propietario del Activo revisa y aprueba en FORM-001 (Sección 7) | Propietario del Activo | FORM-001 | Día 0–1 |
| 4 | CISO aprueba si aplica (Sección 8 del FORM-001) | CISO | FORM-001 | Día 0–1 |
| 5 | Administrador crea cuenta en Active Directory con perfil aprobado | Administrador | AD / Consola de sistema | ≤ 24 h |
| 6 | Administrador configura accesos en cada sistema indicado | Administrador | Consolas de sistemas | ≤ 24 h |
| 7 | Administrador envía credenciales temporales al usuario por canal seguro | Administrador | Correo cifrado | ≤ 24 h |
| 8 | Usuario cambia contraseña en primer acceso y activa MFA (sistemas Nivel 3) | Usuario | Portal de autoservicio | ≤ 24 h de recibir credenciales |
| 9 | Administrador registra la ejecución en Sección 9 del FORM-001 | Administrador | FORM-001 | Al ejecutar |
| 10 | FORM-001 archivado en `/SGSI/Formularios/Accesos/[año]/` | Administrador | Repositorio SGSI | Al ejecutar |

---

## 5. PROCEDIMIENTO DE MODIFICACIÓN DE ACCESOS

### Casos de uso
- Cambio de cargo o área (revocación de accesos anteriores + nuevos accesos)
- Necesidad temporal de acceso adicional
- Escalamiento de privilegios

### Pasos

| Paso | Acción | Responsable | Plazo |
|------|--------|------------|-------|
| 1 | Solicitante o RRHH completa FORM-001 marcando "Modificación" | Solicitante / RRHH | Día 0 |
| 2 | Para cambio de área: propietario del área de origen revoca accesos anteriores | Propietario origen | ≤ 24 h |
| 3 | Propietario del área de destino aprueba nuevos accesos | Propietario destino | ≤ 24 h |
| 4 | CISO aprueba si el cambio involucra acceso privilegiado o Nivel 3 | CISO | ≤ 24 h |
| 5 | Administrador ejecuta revocaciones y nuevos accesos en un solo ciclo | Administrador | ≤ 24 h (urgente) / ≤ 72 h (rutinario) |
| 6 | Usuario notificado de accesos revocados y otorgados | Administrador | Al ejecutar |
| 7 | Registro en log de auditoría y archivo de FORM-001 | Administrador | Al ejecutar |

---

## 6. PROCEDIMIENTO DE BAJA DE USUARIO

### Casos de uso
- Término de contrato laboral o renuncia
- Fin de contrato de médico externo o proveedor
- Caso disciplinario

### Pasos

| Paso | Acción | Responsable | Plazo |
|------|--------|------------|-------|
| 1 | RRHH notifica al Administrador de Sistemas inmediatamente al término de la relación | RRHH | Inmediato |
| 2 | Administrador desactiva la cuenta en Active Directory | Administrador | ≤ 4 horas (estándar) / Inmediato (disciplinario) |
| 3 | Accesos a sistemas Nivel 3 (HCE, AWS) revocados inmediatamente | Administrador | Simultáneo al paso 2 |
| 4 | Sesiones activas del usuario invalidadas en todos los sistemas | Administrador | Simultáneo al paso 2 |
| 5 | Tokens MFA desvinculados | Administrador | Simultáneo al paso 2 |
| 6 | API keys o secretos asignados al usuario transferidos a nuevo propietario o revocados | Administrador + CISO | ≤ 4 horas |
| 7 | Equipo físico recuperado por RRHH; usuario firma FORM-003 (Acta de Devolución) | RRHH | ≤ 24 horas |
| 8 | Cuenta mantenida desactivada 30 días (backup de datos del usuario) | Administrador | — |
| 9 | Cuenta eliminada a los 30 días con backup completo archivado | Administrador | Día 30 |
| 10 | Registro de la baja en log de auditoría | Administrador | Al ejecutar |

### Indicadores de cumplimiento

- Tiempo entre notificación RRHH y desactivación de cuenta: **meta ≤ 4 horas**
- Bajas procesadas sin incumplimiento del plazo: **meta 100%**

---

## 7. PROCEDIMIENTO DE REVISIÓN TRIMESTRAL DE ACCESOS

### Calendario

| Trimestre | Período de Revisión | Fecha Límite |
|-----------|--------------------|-----------  |
| Q1 | Enero — Marzo | 15 de abril |
| Q2 | Abril — Junio | 15 de julio |
| Q3 | Julio — Septiembre | 15 de octubre |
| Q4 | Octubre — Diciembre | 15 de enero (año siguiente) |

### Pasos

| Paso | Acción | Responsable | Plazo |
|------|--------|------------|-------|
| 1 | Coordinador de Seguridad extrae reporte de accesos por sistema desde Active Directory y consolas de aplicaciones | Coordinador de Seguridad | Día 1 del período |
| 2 | Genera FORM-002 pre-completado por sistema y lo envía a cada Propietario del Activo | Coordinador de Seguridad | Día 1–2 |
| 3 | Propietario del Activo revisa cada usuario, decide certificar/revocar/modificar y devuelve FORM-002 firmado | Propietario del Activo | ≤ 10 días hábiles |
| 4 | Coordinador de Seguridad consolida resultados y entrega lista de cambios al Administrador | Coordinador de Seguridad | Día siguiente a cierre |
| 5 | Administrador ejecuta revocaciones y modificaciones | Administrador | ≤ 3 días hábiles |
| 6 | Accesos no certificados dentro del plazo son desactivados automáticamente | Administrador | Al vencer el plazo |
| 7 | Coordinador de Seguridad prepara informe resumen para el Comité de Seguridad | Coordinador de Seguridad | ≤ 5 días hábiles post-ejecución |
| 8 | Informe presentado en reunión del Comité de Seguridad | CISO | Reunión del trimestre |

---

## 8. PROCEDIMIENTO DE AUDITORÍA MENSUAL DE ACCESOS PRIVILEGIADOS

| Paso | Acción | Responsable |
|------|--------|------------|
| 1 | Coordinador de Seguridad extrae lista de cuentas privilegiadas y sus logs del último mes | Coordinador de Seguridad |
| 2 | Verifica que cada cuenta privilegiada tenga propietario, bóveda activa y rotación vigente | Coordinador de Seguridad |
| 3 | Identifica cuentas privilegiadas sin uso en 30 días → propuesta de revocación al CISO | Coordinador de Seguridad |
| 4 | CISO aprueba o rechaza revocaciones propuestas | CISO |
| 5 | Administrador ejecuta los cambios aprobados | Administrador |
| 6 | Registro en log de auditoría y archivo | Coordinador de Seguridad |

---

## 9. GESTIÓN DE CUENTAS INACTIVAS

| Día | Evento | Responsable |
|-----|--------|------------|
| 60 | Sistema envía notificación automática al usuario y su jefe directo | Sistema / Administrador |
| 75 | Si el usuario no ha iniciado sesión: cuenta desactivada automáticamente | Sistema / Administrador |
| 90 | Cuenta eliminada con backup de datos del usuario | Administrador |

**Excepciones:** usuarios con licencia médica o vacaciones prolongadas — RRHH notifica al Administrador con anticipación para suspender el conteo de inactividad.

---

## 10. DOCUMENTOS ASOCIADOS

| Documento | Código | Uso en este procedimiento |
|-----------|--------|--------------------------|
| Formulario de Solicitud de Acceso | FORM-001 | Alta y modificación |
| Formulario de Revisión de Accesos | FORM-002 | Revisión trimestral |
| Acta de Devolución de Activos | FORM-003 | Baja de usuario |
| Registro de Cuentas de Servicio | FORM-005 | Gestión de cuentas svc-* |
| Formulario de Acceso Médico Externo | FORM-006 | Alta de médicos externos |

---

## 11. REVISIÓN

Este procedimiento se revisará anualmente o cuando la PSI-002 sea actualizada.

**Próxima revisión:** Junio 2027

---

**Aprobado por:**

**Firma:** ___________________________  
**Nombre:** Rodrigo Vásquez Herrera  
**Cargo:** Chief Information Security Officer (CISO)  
**Fecha:** 2 de junio de 2026

---

**FIN DEL DOCUMENTO**
