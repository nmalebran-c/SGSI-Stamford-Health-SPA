# POLÍTICA DE GESTIÓN DE PROVEEDORES Y TERCEROS
## Stamford Health and Solution SpA

---

**Código:** PSI-009  
**Versión:** 1.0  
**Fecha de aprobación:** 2 de junio de 2026  
**Aprobado por:** Comité de Seguridad de la Información  
**Propietario:** CISO  
**Clasificación:** CONFIDENCIAL - USO INTERNO  
**Controles ISO 27002:2022:** 5.19, 5.20, 5.21, 5.22

---

## 1. PROPÓSITO

Establecer los requisitos de seguridad de la información que deben cumplir los proveedores y terceros que accedan, procesen, almacenen o transmitan información de Stamford Health and Solution SpA, en particular datos de pacientes y datos personales protegidos por la Ley 19.628 y la Ley 20.584.

---

## 2. ALCANCE

Esta política aplica a toda relación con terceros que involucre:
- Acceso a sistemas de información o infraestructura de Stamford Health
- Procesamiento de datos de pacientes o datos personales de empleados
- Provisión de servicios en la nube o servicios gestionados
- Desarrollo o mantenimiento de software
- Soporte técnico con acceso a sistemas internos

**Proveedores actuales sujetos a esta política:**
- AWS (infraestructura en nube)
- Microsoft (M365, Active Directory)
- Veeam (backup y recuperación)
- Proveedores de mantenimiento de hardware
- Consultores externos de seguridad

---

## 3. CLASIFICACIÓN DE PROVEEDORES

| Nivel | Descripción | Ejemplos | Controles Aplicados |
|-------|-------------|---------|---------------------|
| **Crítico** | Accede o procesa datos de pacientes o datos personales | AWS, proveedores de HCE | Todos los controles de esta política |
| **Alto** | Accede a infraestructura interna sin datos de pacientes | Proveedor de red, soporte TI | Evaluación, contrato, monitoreo |
| **Medio** | Servicios con acceso limitado o indirecto | Licencias de software, consultoría | Contrato con cláusulas básicas |
| **Bajo** | Sin acceso a información de Stamford Health | Servicios de courier, limpieza | NDA básico |

---

## 4. EVALUACIÓN DE PROVEEDORES

Antes de contratar un proveedor Crítico o Alto, el CISO debe completar una evaluación de seguridad:

### 4.1. Criterios de evaluación

| Criterio | Peso | Cómo verificar |
|----------|------|---------------|
| Certificaciones de seguridad (ISO 27001, SOC 2) | 30% | Solicitar certificado vigente |
| Política de privacidad y tratamiento de datos | 25% | Revisión documental |
| Historial de incidentes de seguridad | 20% | Declaración jurada + fuentes públicas |
| Controles técnicos (cifrado, MFA, acceso mínimo) | 15% | Cuestionario de seguridad |
| Capacidad de respuesta ante incidentes | 10% | Tiempo de respuesta contractual |

### 4.2. Resultado mínimo para contratación

- Proveedores Críticos: puntaje ≥ 75 / 100
- Proveedores Altos: puntaje ≥ 60 / 100
- Puntaje menor: requiere aprobación expresa del Comité de Seguridad con controles compensatorios

---

## 5. REQUISITOS CONTRACTUALES

Todo contrato con proveedor Crítico o Alto debe incluir cláusulas que cubran:

### 5.1. Seguridad de la información
- Obligación de implementar controles mínimos equivalentes a los de Stamford Health
- Prohibición de compartir información de Stamford Health con subcontratistas sin autorización previa
- Obligación de notificar incidentes de seguridad que afecten datos de Stamford Health en **≤ 24 horas**
- Derecho de Stamford Health a auditar al proveedor con 30 días de anticipación

### 5.2. Protección de datos (Ley 19.628)
- El proveedor actúa como **encargado de tratamiento** y solo puede tratar los datos según instrucciones de Stamford Health
- Prohibición de usar datos de pacientes para fines distintos al servicio contratado
- Obligación de eliminar o devolver los datos al término del contrato
- Medidas de seguridad técnicas y organizativas proporcionales al riesgo

### 5.3. Confidencialidad
- Acuerdo de No Divulgación (NDA) firmado antes del inicio del servicio
- Vigencia del NDA: durante el contrato + 5 años adicionales
- Extensible al personal del proveedor que acceda a información de Stamford Health

### 5.4. Continuidad
- Proveedor debe contar con plan de continuidad que garantice los SLA acordados
- Notificación a Stamford Health con ≥ 30 días si el proveedor planea discontinuar el servicio

---

## 6. GESTIÓN DE ACCESOS DE PROVEEDORES

Los accesos de proveedores se gestionan conforme a PSI-002 §11.2:

| Control | Detalle |
|---------|---------|
| **Acceso presencial** | Solo con escolta de personal autorizado de Stamford Health |
| **Acceso remoto** | VPN con credenciales temporales, aprobación del CISO, duración ≤ 30 días (renovable) |
| **MFA** | Obligatorio para acceso remoto a sistemas Nivel 2 y 3 |
| **Monitoreo** | 100% de sesiones de proveedores con acceso remoto son monitoreadas |
| **Alcance** | Acceso estrictamente limitado al alcance del servicio contratado |
| **Revocación** | Inmediata al término del servicio o del contrato |

---

## 7. MONITOREO CONTINUO DE PROVEEDORES

### 7.1. Revisión periódica

| Frecuencia | Actividad |
|-----------|-----------|
| **Mensual** | Revisión de logs de acceso de proveedores con acceso remoto activo |
| **Trimestral** | Verificación de vigencia de certificaciones de seguridad |
| **Anual** | Re-evaluación completa de todos los proveedores Críticos y Altos |
| **Al renovar contrato** | Nueva evaluación de seguridad antes de renovar |

### 7.2. Indicadores de alerta

Escalar al CISO si se detecta:
- Proveedor con incidente de seguridad público que afecte datos similares a los de Stamford Health
- Acceso del proveedor a sistemas fuera del horario o alcance acordado
- Cambio en la estructura de propiedad o gestión del proveedor
- Pérdida de certificación de seguridad relevante

---

## 8. GESTIÓN DE SERVICIOS EN LA NUBE (AWS)

AWS es el proveedor de nube crítico de Stamford Health. Los controles adicionales son:

- Acceso gestionado exclusivamente vía **AWS IAM** con principio de mínimo privilegio
- **MFA obligatorio** para todos los usuarios IAM con acceso a consola
- **Ninguna clave de acceso de larga duración** (IAM Access Keys); se usan IAM Roles con STS
- Revisión trimestral de políticas IAM
- AWS CloudTrail habilitado en todas las regiones activas
- Alertas de AWS Security Hub activas para hallazgos críticos y altos
- Los datos de pacientes residen exclusivamente en la región **sa-east-1** (São Paulo)

---

## 9. TÉRMINO DE RELACIÓN CON PROVEEDOR

Al término de cualquier contrato con proveedor Crítico o Alto:

1. Revocar todos los accesos lógicos en ≤ 24 horas
2. Solicitar confirmación escrita de eliminación de datos de Stamford Health en los sistemas del proveedor
3. Recuperar activos físicos si aplica
4. Revocar certificados o API keys asociados al proveedor
5. Actualizar la documentación de riesgos si el proveedor era mitigador de algún riesgo identificado

---

## 10. RESPONSABILIDADES

| Rol | Responsabilidad |
|-----|----------------|
| **CISO** | Aprobar proveedores Críticos, revisar contratos, monitorear cumplimiento |
| **Gerencia General** | Aprobar contratos, asegurar cláusulas de seguridad |
| **CTO** | Gestionar accesos técnicos de proveedores de TI |
| **Asesor Legal** | Revisar cláusulas de protección de datos y NDA |
| **Coordinador de Seguridad** | Mantener el registro de proveedores, ejecutar revisiones periódicas |

---

## 11. REGISTRO DE PROVEEDORES

El Coordinador de Seguridad mantiene un **Registro de Proveedores** con:
- Nombre y RUT del proveedor
- Clasificación (Crítico / Alto / Medio / Bajo)
- Servicios contratados
- Fecha de evaluación de seguridad y puntaje
- Vigencia del contrato y NDA
- Accesos activos
- Historial de incidentes relacionados

---

## 12. REFERENCIAS NORMATIVAS

- ISO/IEC 27002:2022 — Controles 5.19, 5.20, 5.21, 5.22
- Ley 19.628 — Artículos sobre encargados de tratamiento
- Ley 20.584 — Confidencialidad de datos clínicos con terceros

---

## 13. REVISIÓN

Anual o tras un incidente involucrando a un proveedor.

**Próxima revisión:** Junio 2027

---

**Aprobado por:**

**Firma:** ___________________________  
**Nombre:** Rodrigo Vásquez Herrera  
**Cargo:** CISO  
**Fecha:** 2 de junio de 2026

---

**FIN DEL DOCUMENTO**
