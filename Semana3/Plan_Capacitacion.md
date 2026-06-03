# PLAN DE CAPACITACIÓN EN SEGURIDAD DE LA INFORMACIÓN 2026
## Stamford Health and Solution SpA

---

**Código:** IMPL-003  
**Versión:** 1.0  
**Fecha de aprobación:** 15 de enero de 2026  
**Aprobado por:** Comité de Seguridad de la Información  
**Responsable:** Coordinador de Seguridad  
**Clasificación:** USO INTERNO

---

## 1. PROPÓSITO

Desarrollar y ejecutar un programa de capacitación que asegure que todo el personal de Stamford Health y los profesionales médicos externos comprendan sus obligaciones de seguridad de la información, los controles implementados y las normativas aplicables (Ley 19.628, Ley 20.584).

---

## 2. AUDIENCIAS

| ID | Audiencia | Cantidad | Nivel de detalle requerido |
|----|-----------|---------|---------------------------|
| AUD-01 | Personal administrativo y operativo | 55 personas | Básico — usuario final |
| AUD-02 | Personal técnico de TI | 10 personas | Avanzado — técnico |
| AUD-03 | Equipo de seguridad (CSIRT) | 4 personas | Especialista |
| AUD-04 | Directivos y jefes de área | 8 personas | Estratégico — gerencial |
| AUD-05 | Profesionales médicos externos | 250 personas | Básico — uso HCE y Ley 20.584 |
| AUD-06 | Contratistas y proveedores con acceso | Variable | Básico — uso aceptable |

---

## 3. MÓDULOS DE CAPACITACIÓN

### MÓDULO 1 — Fundamentos de Seguridad de la Información
**Duración:** 2 horas | **Modalidad:** E-learning + quiz de evaluación  
**Audiencia:** AUD-01, AUD-04, AUD-05, AUD-06  
**Frecuencia:** Anual (obligatorio en inducción)

| Tema | Tiempo |
|------|--------|
| ¿Qué es la seguridad de la información y por qué importa? | 20 min |
| Clasificación de información: confidencial, restringido, interno, público | 20 min |
| Contraseñas seguras y uso del MFA | 20 min |
| Reconocimiento de phishing y correos maliciosos | 20 min |
| Política de escritorio limpio y bloqueo de pantalla | 10 min |
| Cómo reportar un incidente de seguridad | 10 min |
| Evaluación final | 20 min |

**Nota de aprobación:** ≥ 70 / 100 | **Re-capacitación si:** < 70 puntos

---

### MÓDULO 2 — Uso Aceptable de Recursos Tecnológicos (PSI-003)
**Duración:** 1.5 horas | **Modalidad:** E-learning  
**Audiencia:** AUD-01, AUD-02, AUD-04  
**Frecuencia:** Anual

| Tema | Tiempo |
|------|--------|
| Uso permitido de equipos corporativos, correo e internet | 20 min |
| Prohibiciones: USB personales, software no autorizado, redes WiFi públicas | 20 min |
| Trabajo remoto: VPN, entorno seguro, dispositivos personales | 20 min |
| Monitoreo corporativo: qué se monitorea y por qué | 15 min |
| Sanciones por incumplimiento | 10 min |
| Evaluación | 15 min |

---

### MÓDULO 3 — Gestión de Accesos y Contraseñas (PSI-002)
**Duración:** 1 hora | **Modalidad:** E-learning  
**Audiencia:** AUD-01, AUD-02, AUD-04  
**Frecuencia:** Anual

| Tema | Tiempo |
|------|--------|
| Por qué no compartir contraseñas | 15 min |
| Cómo usar el MFA paso a paso | 20 min |
| Bóveda de contraseñas: qué es y cómo usarla (privilegiados) | 15 min |
| Qué hacer si sospecho que mi cuenta fue comprometida | 10 min |

---

### MÓDULO 4 — Seguridad para Personal Técnico de TI
**Duración:** 6 horas | **Modalidad:** Presencial (taller)  
**Audiencia:** AUD-02, AUD-03  
**Frecuencia:** Anual

| Tema | Tiempo |
|------|--------|
| Gestión de identidades y accesos privilegiados (PAM) | 60 min |
| Gestión de vulnerabilidades: escaneo, CVSS, remediación | 60 min |
| Hardening de servidores Linux y Windows Server | 60 min |
| Seguridad en AWS: IAM, KMS, CloudTrail, Security Hub | 60 min |
| Gestión segura de cambios y CMDB | 30 min |
| Criptografía aplicada: TLS, cifrado de disco, gestión de claves | 30 min |
| Laboratorio práctico: detección de anomalías en logs | 60 min |

---

### MÓDULO 5 — Respuesta a Incidentes (PROC-005)
**Duración:** 4 horas | **Modalidad:** Taller práctico + simulacro tabletop  
**Audiencia:** AUD-03 (CSIRT)  
**Frecuencia:** Semestral

| Tema | Tiempo |
|------|--------|
| Clasificación de incidentes (Niveles 1–4) y criterios de activación | 30 min |
| Fases de respuesta: contención, análisis forense, erradicación, recuperación | 60 min |
| Manejo de evidencia y cadena de custodia | 30 min |
| Comunicaciones durante un incidente (interno + regulatorio) | 30 min |
| Simulacro tabletop (escenario asignado) | 60 min |
| Debriefing y lecciones aprendidas | 30 min |

**Escenarios de simulacro:**
- Q1: Ransomware en servidor de producción
- Q3: Brecha de datos de pacientes por insider

---

### MÓDULO 6 — Normativa para Personal Médico y Directivos
**Duración:** 30 minutos | **Modalidad:** E-learning  
**Audiencia:** AUD-04, AUD-05  
**Frecuencia:** Anual (obligatorio antes de primer acceso a HCE)

| Tema | Tiempo |
|------|--------|
| Ley 20.584: confidencialidad de la información clínica | 10 min |
| Ley 19.628: protección de datos personales de pacientes | 10 min |
| Consecuencias legales del acceso indebido a HCE | 5 min |
| Cómo acceder al Portal Médico con MFA | 5 min |

---

## 4. CALENDARIO DE EJECUCIÓN 2026

| Mes | Actividad | Audiencia | Modalidad |
|-----|-----------|-----------|-----------|
| Enero | Módulo 5 — Capacitación inicial CSIRT | AUD-03 | Presencial |
| Enero | Módulo 6 — Normativa médica (inducción médicos enero) | AUD-05 | E-learning |
| Febrero | Módulo 1 — Fundamentos (todos) | AUD-01/04/05/06 | E-learning |
| Febrero | Módulo 3 — Gestión de accesos y MFA (todos) | AUD-01/02/04 | E-learning |
| Febrero | Simulacro tabletop: ransomware | AUD-03 | Presencial |
| Marzo | Módulo 2 — Uso aceptable (todos) | AUD-01/02/04 | E-learning |
| Marzo | Módulo 4 — Seguridad TI avanzado | AUD-02/03 | Presencial |
| Marzo | Módulo 6 — Normativa médica (médicos restantes) | AUD-05 | E-learning |
| Agosto | Módulo 4 — Segunda edición avanzada | AUD-02/03 | Presencial |
| Septiembre | Módulo 1 y 2 — Actualización anual (todos) | AUD-01/04 | E-learning |
| Septiembre | Simulacro tabletop: brecha de datos | AUD-03 | Presencial |
| Continuo | Módulo 6 en inducción de nuevos médicos externos | AUD-05 | E-learning |

---

## 5. MÉTRICAS DE CUMPLIMIENTO

| Indicador | Meta | Frecuencia de medición |
|-----------|------|----------------------|
| % de personal que completó Módulo 1 | 100% | Trimestral |
| % de personal técnico con Módulo 4 completado | 100% | Semestral |
| Nota promedio en evaluaciones | ≥ 80 / 100 | Por cohorte |
| % de médicos externos con Módulo 6 antes del primer acceso | 100% | Mensual |
| Simulacros ejecutados | 2 por año | Semestral |
| % de colaboradores que identificaron phishing en campaña de prueba | ≥ 85% | Trimestral |

---

## 6. RECURSOS

| Recurso | Responsable | Costo estimado |
|---------|------------|----------------|
| Plataforma LMS (Microsoft Viva Learning) | CTO | Incluido en M365 |
| Contenido e-learning (módulos 1, 2, 3, 6) | Coordinador de Seguridad | $1M CLP |
| Tallerista externo (módulos 4 y 5) | CISO | $2M CLP |
| Materiales impresos y campañas de concientización | Coordinador de Seguridad | $0.5M CLP |
| **Total** | | **$3.5M CLP** |

---

**Aprobado por:**

**Firma:** ___________________________  
**Nombre:** Rodrigo Vásquez Herrera  
**Cargo:** CISO  
**Fecha:** 15 de enero de 2026

---

**FIN DEL DOCUMENTO**
