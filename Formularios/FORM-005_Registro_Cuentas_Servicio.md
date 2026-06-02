# FORMULARIO DE REGISTRO DE CUENTAS DE SERVICIO
## Stamford Health and Solution SpA

---

**Código:** FORM-005  
**Versión:** 1.0  
**Fecha de aprobación:** 2 de junio de 2026  
**Asociado a:** PSI-002 — Política de Control de Accesos (Sección 4.4)  
**Clasificación:** CONFIDENCIAL - USO INTERNO

---

## PROPÓSITO

Registrar y controlar todas las cuentas de servicio (`svc-*`) y credenciales no humanas utilizadas para integraciones, automatizaciones y accesos programáticos entre sistemas de Stamford Health and Solution SpA.

---

## SECCIÓN 1 — DATOS DE LA CUENTA DE SERVICIO

| Campo | Datos |
|-------|-------|
| **Nombre de la cuenta** | `svc-` |
| **Descripción de la función** | |
| **Sistema de origen** (que usa la cuenta) | |
| **Sistema de destino** (al que accede la cuenta) | |
| **Tipo de credencial** | ☐ Usuario/Contraseña ☐ API Key ☐ Token OAuth ☐ Certificado digital ☐ AWS IAM Role ☐ Otro: ______ |
| **Clasificación del sistema accedido** | ☐ Nivel 1 — Interno ☐ Nivel 2 — Restringido ☐ Nivel 3 — Crítico |
| **Fecha de creación** | |
| **Fecha de expiración** (si aplica) | |

---

## SECCIÓN 2 — PROPIETARIO RESPONSABLE

La cuenta de servicio debe tener un propietario humano identificado que sea responsable de su uso y mantenimiento.

| Campo | Datos |
|-------|-------|
| **Nombre del propietario** | |
| **Cargo** | |
| **Área** | |
| **Correo corporativo** | |
| **Propietario suplente** | |

---

## SECCIÓN 3 — PERMISOS Y ALCANCE

Detallar los permisos mínimos otorgados, conforme al principio de privilegio mínimo:

| Recurso / Endpoint / Tabla | Nivel de Acceso | Justificación |
|---------------------------|----------------|---------------|
| | ☐ Lectura ☐ Escritura ☐ Ejecución ☐ Administración | |
| | ☐ Lectura ☐ Escritura ☐ Ejecución ☐ Administración | |
| | ☐ Lectura ☐ Escritura ☐ Ejecución ☐ Administración | |

**¿La cuenta tiene acceso interactivo (login) habilitado?**  
☐ No (correcto — debe estar deshabilitado)  
☐ Sí (requiere justificación explícita aprobada por CISO): ___________________________

---

## SECCIÓN 4 — GESTIÓN DE CREDENCIALES

| Campo | Datos |
|-------|-------|
| **¿Credencial registrada en bóveda corporativa?** | ☐ Sí — Nombre del secreto en bóveda: ________________ ☐ No (no permitido) |
| **Fecha de última rotación de credencial** | |
| **Próxima rotación programada** | (máximo 90 días desde la última) |
| **Responsable de rotación** | |

---

## SECCIÓN 5 — CONDICIONES DE VIGENCIA

| Condición | Detalle |
|-----------|---------|
| **¿La cuenta es permanente o temporal?** | ☐ Permanente ☐ Temporal — Fecha de término: _____________ |
| **Proyecto o integración asociada** | |
| **¿Qué sucede si el proyecto termina?** | La cuenta debe eliminarse en ≤5 días hábiles desde el término |

---

## SECCIÓN 6 — APROBACIONES

### Aprobación del Propietario Responsable

Declaro asumir la responsabilidad sobre el uso de esta cuenta de servicio y me comprometo a notificar al Administrador de Sistemas ante cualquier cambio en su uso o al término de la integración.

**Nombre:** ___________________________  
**Firma:** ___________________________  
**Fecha:** ___________________________

### Aprobación del CISO

| Campo | Datos |
|-------|-------|
| **Nombre** | Rodrigo Vásquez Herrera |
| **Decisión** | ☐ Aprobado ☐ Rechazado |
| **Condiciones adicionales** | |
| **Firma** | |
| **Fecha** | |

---

## SECCIÓN 7 — REGISTRO DE REVISIONES ANUALES

| Fecha de Revisión | Propietario que Certifica | Decisión | Cambios realizados |
|-------------------|--------------------------|----------|-------------------|
| | | ☐ Mantener ☐ Modificar ☐ Eliminar | |
| | | ☐ Mantener ☐ Modificar ☐ Eliminar | |
| | | ☐ Mantener ☐ Modificar ☐ Eliminar | |

---

## SECCIÓN 8 — BAJA DE LA CUENTA

*(Completar al dar de baja la cuenta)*

| Campo | Datos |
|-------|-------|
| **Fecha de solicitud de baja** | |
| **Motivo** | ☐ Fin de proyecto ☐ Reemplazo tecnológico ☐ Reorganización ☐ Otro: ______ |
| **Fecha de desactivación de la cuenta** | |
| **Fecha de eliminación de credencial de bóveda** | |
| **Confirmación de eliminación en todos los sistemas** | ☐ Sí |
| **Administrador ejecutor** | |
| **Firma** | |

---

## NOTAS DE ARCHIVO

- Conservar por **5 años** desde la fecha de baja de la cuenta.
- Archivar en: `/SGSI/Formularios/CuentasServicio/`
- Enviar copia al CISO al momento de la aprobación y al momento de la baja.

---

**FIN DEL FORMULARIO**
