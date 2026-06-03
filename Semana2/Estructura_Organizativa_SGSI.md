# ESTRUCTURA ORGANIZATIVA DEL SGSI
## Comité de Seguridad y Matriz de Roles y Responsabilidades
### Stamford Health and Solution SpA

---

**Código:** ORG-001  
**Versión:** 1.0  
**Fecha:** 15 de noviembre de 2025  
**Aprobado por:** Directorio Ejecutivo  
**Clasificación:** CONFIDENCIAL - USO INTERNO

---

## 1. COMITÉ DE SEGURIDAD DE LA INFORMACIÓN

### 1.1. Propósito

El Comité de Seguridad de la Información es el órgano de **gobernanza** responsable de supervisar y dirigir el Sistema de Gestión de Seguridad de la Información (SGSI) de Stamford Health and Solution SpA.

### 1.2. Composición

| Rol | Cargo Organizacional | Tipo | Responsabilidad Principal |
|-----|---------------------|------|---------------------------|
| **Presidente** | Director Ejecutivo (CEO) | Permanente | Liderazgo estratégico y aprobación final |
| **Vicepresidente** | CISO | Permanente | Gestión operativa del SGSI |
| **Miembro** | CTO | Permanente | Infraestructura y tecnología |
| **Miembro** | COO | Permanente | Operaciones y procesos |
| **Miembro** | CFO | Permanente | Presupuesto y recursos financieros |
| **Miembro** | Director de RRHH | Permanente | Personal, capacitación y cultura |
| **Miembro** | Asesor Legal | Permanente | Cumplimiento legal y regulatorio |
| **Miembro** | Gerente de Calidad | Permanente | Integración con SGC |
| **Secretario** | Coordinador de Seguridad | Permanente | Actas, seguimiento y coordinación |
| **Invitados** | Según agenda | Variable | Expertise específico según necesidad |

### 1.3. Funciones y Responsabilidades del Comité

#### 1.3.1. Funciones Estratégicas
- Establecer la dirección estratégica del SGSI
- Aprobar la Política de Seguridad de la Información
- Definir objetivos de seguridad alineados con objetivos del negocio
- Asignar presupuesto anual para seguridad de la información
- Aprobar el plan anual de seguridad de la información
- Patrocinar proyectos de seguridad estratégicos

#### 1.3.2. Funciones de Gobernanza
- Revisar el desempeño del SGSI trimestralmente
- Aprobar políticas, procedimientos y estándares de seguridad
- Tomar decisiones sobre tratamiento de riesgos críticos y altos
- Aprobar excepciones a políticas de seguridad (cuando justificadas)
- Supervisar el cumplimiento legal y regulatorio
- Autorizar auditorías internas y externas

#### 1.3.3. Funciones de Supervisión
- Monitorear KPIs de seguridad de la información
- Revisar informes de incidentes de seguridad significativos
- Evaluar la efectividad de controles implementados
- Supervisar proyectos de seguridad en curso
- Revisar resultados de auditorías y planes de acción
- Supervisar el programa de capacitación en seguridad

#### 1.3.4. Funciones de Mejora Continua
- Promover la cultura de seguridad en la organización
- Impulsar iniciativas de concientización
- Aprobar inversiones en mejoras de seguridad
- Facilitar la comunicación entre áreas sobre seguridad
- Asegurar la integración del SGSI con otros sistemas de gestión

### 1.4. Frecuencia de Reuniones

| Tipo de Reunión | Frecuencia | Duración | Convocatoria |
|----------------|-----------|----------|--------------|
| **Ordinaria** | Trimestral | 2-3 horas | CISO (15 días antes) |
| **Extraordinaria** | Cuando sea necesario | Variable | Presidente o CISO (5 días antes) |
| **Emergencia** | Por incidente crítico | Variable | Presidente o CISO (inmediato) |

### 1.5. Quórum y Toma de Decisiones

- **Quórum mínimo:** 60% de miembros permanentes (incluyendo Presidente o CISO)
- **Toma de decisiones:** Consenso preferido; votación simple (mayoría) cuando no hay consenso
- **Voto de calidad:** Presidente tiene voto dirimente en caso de empate
- **Decisiones urgentes:** CISO puede tomar decisiones operativas urgentes, ratificadas posteriormente por el Comité

### 1.6. Agenda Tipo - Reunión Ordinaria

1. Verificación de quórum y aprobación de agenda
2. Aprobación de acta anterior y revisión de compromisos
3. Revisión de KPIs de seguridad del trimestre
4. Informe de incidentes de seguridad
5. Estado de proyectos de seguridad
6. Resultados de auditorías y revisiones
7. Análisis de nuevos riesgos identificados
8. Aprobación de políticas/procedimientos nuevos o actualizados
9. Asignación de presupuesto para iniciativas
10. Asuntos varios
11. Acuerdos y compromisos
12. Próxima reunión

### 1.7. Actas y Documentación

- **Secretario** elabora acta de cada reunión en 5 días hábiles
- Acta incluye: asistentes, temas tratados, decisiones tomadas, compromisos con responsables y plazos
- Actas se aprueban en siguiente reunión
- Actas se archivan en repositorio seguro del SGSI
- Resumen ejecutivo se comunica a áreas relevantes

---

## 2. ESTRUCTURA ORGANIZATIVA DEL SGSI

### 2.1. Organigrama de Seguridad

```
                    ┌─────────────────────┐
                    │  DIRECTORIO         │
                    │  EJECUTIVO          │
                    └──────────┬──────────┘
                               │
                    ┌──────────▼──────────┐
                    │  COMITÉ DE          │
                    │  SEGURIDAD          │
                    └──────────┬──────────┘
                               │
            ┌──────────────────┼──────────────────┐
            │                  │                  │
   ┌────────▼────────┐ ┌──────▼──────┐  ┌───────▼────────┐
   │   CISO          │ │    CTO      │  │  Propietarios  │
   │ (Chief Info     │ │             │  │  de Activos    │
   │  Security       │ │             │  │                │
   │  Officer)       │ │             │  │                │
   └────────┬────────┘ └─────────────┘  └────────────────┘
            │
   ┌────────┴────────┬──────────────┬──────────────────┐
   │                 │              │                  │
┌──▼───────────┐ ┌──▼─────────┐ ┌─▼──────────┐ ┌────▼──────────┐
│ Coordinador  │ │  Equipo    │ │  CSIRT     │ │ Oficial de    │
│ de Seguridad │ │  Seguridad │ │ (Respuesta │ │ Cumplimiento  │
│              │ │  Técnica   │ │ Incidentes)│ │               │
└──────────────┘ └────────────┘ └────────────┘ └───────────────┘
```

### 2.2. Líneas de Reporte

| Rol | Reporta a | Frecuencia |
|-----|-----------|------------|
| CISO | Director Ejecutivo (CEO) | Semanal operativo, mensual estratégico |
| Coordinador de Seguridad | CISO | Diario |
| Equipo de Seguridad Técnica | CISO / CTO (matricial) | Diario técnico, semanal estratégico |
| CSIRT | CISO | Inmediato en incidentes, semanal operativo |
| Oficial de Cumplimiento | CISO | Semanal |
| Propietarios de Activos | Sus gerencias funcionales + CISO (matricial) | Mensual |

---

## 3. MATRIZ DE ROLES Y RESPONSABILIDADES

### 3.1. Roles Ejecutivos y de Gobernanza

#### 3.1.1. DIRECTOR EJECUTIVO (CEO)

**Descripción:** Máxima autoridad ejecutiva, responsable final de la seguridad de la información.

**Responsabilidades:**
- ✅ Aprobar la Política de Seguridad de la Información
- ✅ Presidir el Comité de Seguridad de la Información
- ✅ Asignar recursos necesarios para el SGSI
- ✅ Nombrar al CISO y delegar autoridad
- ✅ Comunicar la importancia de la seguridad a toda la organización
- ✅ Revisar el desempeño del SGSI anualmente
- ✅ Aprobar decisiones estratégicas sobre riesgos críticos
- ✅ Rendir cuentas al Directorio sobre seguridad de la información

**Autoridad:**
- Veto sobre cualquier decisión de seguridad
- Asignación de presupuesto de seguridad
- Contratación y despido de personal clave de seguridad
- Aprobación de excepciones a políticas

**Tiempo dedicado:** 5% (reuniones trimestrales + revisiones estratégicas)

---

#### 3.1.2. CHIEF INFORMATION SECURITY OFFICER (CISO)

**Descripción:** Responsable de diseñar, implementar, mantener y mejorar el SGSI.

**Responsabilidades:**

**Estratégicas:**
- ✅ Diseñar la estrategia de seguridad de la información
- ✅ Definir objetivos de seguridad alineados con el negocio
- ✅ Presentar el estado del SGSI al Comité trimestralmente
- ✅ Gestionar el presupuesto de seguridad de la información
- ✅ Representar a la organización en auditorías externas

**Tácticas:**
- ✅ Desarrollar y mantener políticas y procedimientos de seguridad
- ✅ Coordinar el análisis de riesgos y su tratamiento
- ✅ Supervisar el equipo de seguridad
- ✅ Gestionar relaciones con proveedores de seguridad
- ✅ Coordinar el programa de capacitación en seguridad
- ✅ Aprobar arquitecturas de seguridad

**Operativas:**
- ✅ Supervisar investigaciones de incidentes significativos
- ✅ Revisar y aprobar cambios con impacto en seguridad
- ✅ Coordinar auditorías internas de seguridad
- ✅ Gestionar el programa de gestión de vulnerabilidades
- ✅ Reportar métricas e indicadores de seguridad

**Autoridad:**
- Aprobar o rechazar proyectos por razones de seguridad
- Suspender sistemas o procesos que presenten riesgos críticos
- Autorizar accesos privilegiados
- Aprobar excepciones temporales a políticas
- Contratar consultores de seguridad
- Iniciar investigaciones internas

**Requisitos:**
- Certificación profesional en seguridad (CISSP, CISM o equivalente)
- Mínimo 5 años de experiencia en seguridad de la información
- Conocimiento de ISO 27001, ISO 27002, NIST, normativas chilenas
- Experiencia en sector salud (deseable)

**Tiempo dedicado:** 100% (dedicación completa)

**Reporta a:** Director Ejecutivo (CEO)

---

#### 3.1.3. CHIEF TECHNOLOGY OFFICER (CTO)

**Descripción:** Responsable de la infraestructura tecnológica y su seguridad técnica.

**Responsabilidades:**
- ✅ Implementar controles técnicos de seguridad
- ✅ Gestionar la infraestructura de TI de forma segura
- ✅ Asegurar la disponibilidad de sistemas críticos
- ✅ Coordinar la gestión de parches y actualizaciones
- ✅ Supervisar la seguridad de la arquitectura de red
- ✅ Implementar soluciones de backup y recuperación
- ✅ Colaborar con CISO en proyectos de seguridad
- ✅ Gestionar proveedores de tecnología

**Autoridad:**
- Decisiones sobre arquitectura tecnológica (con aprobación CISO en aspectos de seguridad)
- Asignación de recursos técnicos
- Aprobación de cambios en infraestructura

**Tiempo dedicado:** 30% en temas de seguridad

**Reporta a:** Director Ejecutivo (CEO)

---

### 3.2. Roles Operativos de Seguridad

#### 3.2.1. COORDINADOR DE SEGURIDAD DE LA INFORMACIÓN

**Descripción:** Brazo derecho del CISO, coordina actividades operativas del SGSI.

**Responsabilidades:**
- ✅ Coordinar la implementación de políticas y procedimientos
- ✅ Gestionar el calendario de actividades de seguridad
- ✅ Facilitar reuniones del Comité de Seguridad (secretaría)
- ✅ Mantener la documentación del SGSI actualizada
- ✅ Coordinar auditorías internas y externas
- ✅ Gestionar el registro de riesgos y controles
- ✅ Preparar reportes y métricas de seguridad
- ✅ Coordinar el programa de capacitación
- ✅ Gestionar el inventario de activos de información
- ✅ Facilitar la comunicación entre áreas sobre seguridad

**Autoridad:**
- Solicitar información a cualquier área para fines de seguridad
- Programar capacitaciones obligatorias
- Escalar incumplimientos al CISO

**Requisitos:**
- Título profesional en TI, ingeniería o afines
- Certificación en seguridad (deseable)
- Experiencia en gestión de proyectos
- Conocimiento de ISO 27001

**Tiempo dedicado:** 100%

**Reporta a:** CISO

---

#### 3.2.2. EQUIPO DE SEGURIDAD TÉCNICA (3 personas)

**Descripción:** Especialistas técnicos en seguridad de la información.

**Responsabilidades:**

**Administrador de Seguridad de Infraestructura:**
- ✅ Administrar firewalls, IDS/IPS, sistemas de prevención
- ✅ Configurar y mantener VPNs
- ✅ Gestionar segmentación de red
- ✅ Monitorear logs de seguridad de infraestructura
- ✅ Implementar hardening de servidores

**Administrador de Seguridad de Aplicaciones:**
- ✅ Realizar análisis de vulnerabilidades en aplicaciones
- ✅ Revisar código fuente (code review) de seguridad
- ✅ Gestionar WAF (Web Application Firewall)
- ✅ Implementar seguridad en APIs
- ✅ Coordinar con desarrollo en SDLC seguro

**Analista de Seguridad y Monitoreo:**
- ✅ Monitorear SIEM 24/7 (turnos)
- ✅ Analizar alertas de seguridad
- ✅ Realizar búsqueda proactiva de amenazas (threat hunting)
- ✅ Gestionar antivirus y EDR empresarial
- ✅ Ejecutar escaneos de vulnerabilidades
- ✅ Generar reportes de incidentes

**Autoridad:**
- Implementar controles técnicos aprobados
- Bloquear tráfico sospechoso temporalmente
- Aislar sistemas comprometidos
- Solicitar cambios de configuración

**Requisitos:**
- Título técnico o profesional en TI
- Certificaciones técnicas (Security+, CEH, CCNA Security, etc.)
- Experiencia práctica en seguridad

**Tiempo dedicado:** 100% cada uno

**Reporta a:** CISO (funcionalmente) y CTO (administrativamente)

---

#### 3.2.3. CSIRT (Computer Security Incident Response Team)

**Descripción:** Equipo dedicado a respuesta a incidentes de seguridad.

**Composición:**
- **Líder CSIRT:** CISO o Coordinador de Seguridad
- **Miembros permanentes:** Equipo de Seguridad Técnica (3)
- **Miembros de soporte:** Administradores de sistemas (según necesidad)
- **Apoyo externo:** Proveedores de seguridad (cuando sea necesario)

**Responsabilidades:**
- ✅ Detectar y analizar incidentes de seguridad
- ✅ Contener y erradicar amenazas
- ✅ Coordinar la recuperación de incidentes
- ✅ Documentar lecciones aprendidas
- ✅ Mantener actualizado el Plan de Respuesta a Incidentes
- ✅ Realizar ejercicios y simulacros
- ✅ Coordinar con entidades externas (CSIRT nacional, proveedores)
- ✅ Reportar incidentes al Comité de Seguridad

**Activación:** Inmediata ante incidente confirmado o sospecha seria

**Autoridad en incidentes:**
- Aislar sistemas comprometidos
- Solicitar información forense
- Coordinar con áreas afectadas
- Escalar a Comité de Seguridad
- Contactar autoridades si es necesario

**Tiempo dedicado:** On-demand (activación según incidentes)

---

#### 3.2.4. OFICIAL DE CUMPLIMIENTO (COMPLIANCE OFFICER)

**Descripción:** Responsable de asegurar cumplimiento legal y regulatorio.

**Responsabilidades:**
- ✅ Monitorear cambios en legislación aplicable
- ✅ Evaluar cumplimiento con leyes y regulaciones
- ✅ Coordinar con asesor legal externo
- ✅ Gestionar relaciones con autoridades regulatorias
- ✅ Preparar reportes de cumplimiento
- ✅ Implementar controles de privacidad de datos
- ✅ Gestionar solicitudes de derechos ARCO
- ✅ Mantener registro de tratamiento de datos
- ✅ Coordinar auditorías regulatorias

**Autoridad:**
- Suspender actividades que violen regulaciones
- Solicitar evidencias de cumplimiento
- Escalar incumplimientos a Comité

**Requisitos:**
- Conocimiento de leyes chilenas 19.628, 20.584, 21.459
- Conocimiento de GDPR (deseable)
- Experiencia en compliance

**Tiempo dedicado:** 50% (puede ser rol compartido con Legal)

**Reporta a:** CISO

---

### 3.3. Roles de Áreas Funcionales

#### 3.3.1. PROPIETARIOS DE ACTIVOS (ASSET OWNERS)

**Descripción:** Responsables funcionales de activos de información críticos.

**Identificación:**
- Gerente Médico: Propietario de Sistema HCE y BD Historias Clínicas
- Gerente de Operaciones: Propietario de sistemas operacionales
- CFO: Propietario de sistemas financieros
- Gerente de RRHH: Propietario de información de personal

**Responsabilidades:**
- ✅ Clasificar la información según criticidad
- ✅ Definir quién debe tener acceso al activo
- ✅ Aprobar solicitudes de acceso
- ✅ Revisar accesos periódicamente (trimestral)
- ✅ Reportar incidentes relacionados con el activo
- ✅ Definir requisitos de seguridad del activo
- ✅ Aprobar cambios que afecten el activo
- ✅ Asegurar disponibilidad del activo

**Autoridad:**
- Aprobar o denegar accesos al activo
- Definir controles adicionales para el activo
- Solicitar auditorías del activo

**Tiempo dedicado:** 10% (revisiones periódicas + aprobaciones)

**Reporta a:** Su gerencia funcional + coordinación con CISO

---

#### 3.3.2. CUSTODIOS DE ACTIVOS (ASSET CUSTODIANS)

**Descripción:** Administradores técnicos de sistemas que alojan activos.

**Típicamente:**
- Administradores de Bases de Datos (DBA)
- Administradores de Servidores
- Administradores de Red
- Administradores de Aplicaciones

**Responsabilidades:**
- ✅ Implementar controles técnicos definidos
- ✅ Mantener configuraciones seguras
- ✅ Aplicar parches y actualizaciones
- ✅ Realizar backups según política
- ✅ Monitorear el desempeño del sistema
- ✅ Ejecutar cambios aprobados
- ✅ Reportar anomalías
- ✅ Mantener documentación técnica

**Autoridad:**
- Implementar configuraciones de seguridad
- Ejecutar procedimientos de emergencia
- Solicitar aprobación para cambios

**Reporta a:** CTO / Gerentes técnicos

---

#### 3.3.3. USUARIOS DE INFORMACIÓN

**Descripción:** Todo el personal que accede y utiliza información.

**Categorías:**
1. **Usuarios Privilegiados:** Administradores de sistemas
2. **Usuarios Profesionales:** Personal médico con acceso a HC
3. **Usuarios Estándar:** Personal administrativo
4. **Usuarios Externos:** Proveedores con acceso limitado

**Responsabilidades:**
- ✅ Cumplir con políticas de seguridad
- ✅ Proteger credenciales de acceso
- ✅ Usar información solo para fines autorizados
- ✅ Reportar incidentes y sospechas
- ✅ Completar capacitaciones obligatorias
- ✅ Proteger dispositivos asignados
- ✅ No compartir cuentas
- ✅ Cerrar sesiones al terminar

**Obligaciones:**
- Firmar acuerdo de confidencialidad
- Completar inducción de seguridad
- Capacitación anual obligatoria

---

### 3.4. Roles de Apoyo

#### 3.4.1. DIRECTOR DE RECURSOS HUMANOS

**Responsabilidades en Seguridad:**
- ✅ Incluir seguridad en proceso de onboarding
- ✅ Coordinar programa de capacitación en seguridad
- ✅ Gestionar proceso de offboarding seguro
- ✅ Investigar incidentes con personal involucrado
- ✅ Aplicar sanciones por violaciones
- ✅ Promover cultura de seguridad
- ✅ Realizar verificación de antecedentes (background checks)

**Tiempo dedicado:** 15% en temas de seguridad

---

#### 3.4.2. ASESOR LEGAL

**Responsabilidades en Seguridad:**
- ✅ Asesorar en cumplimiento legal
- ✅ Revisar contratos con proveedores (cláusulas de seguridad)
- ✅ Gestionar incidentes con implicaciones legales
- ✅ Coordinar con autoridades cuando sea necesario
- ✅ Asesorar en notificaciones de brechas
- ✅ Defender la organización en litigios

**Tiempo dedicado:** 10% (on-demand)

---

#### 3.4.3. GERENTE DE CALIDAD

**Responsabilidades en Seguridad:**
- ✅ Integrar SGSI con Sistema de Gestión de Calidad (ISO 9001)
- ✅ Coordinar auditorías integradas
- ✅ Asegurar coherencia entre sistemas de gestión
- ✅ Promover mejora continua

**Tiempo dedicado:** 5%

---

## 4. MATRIZ RACI - PRINCIPALES ACTIVIDADES DEL SGSI

| Actividad | CEO | CISO | CTO | Coord. Seg | Eq. Seg | Propiet. Activos | RRHH | Legal |
|-----------|-----|------|-----|------------|---------|------------------|------|-------|
| Aprobar Política de Seguridad | **A** | R | C | C | I | C | C | C |
| Gestionar SGSI | A | **R** | C | C | I | C | I | I |
| Análisis de Riesgos | A | **R** | C | C | C | C | I | I |
| Implementar Controles Técnicos | A | A | **R** | I | C | I | - | - |
| Gestionar Incidentes | I | **A/R** | C | C | C | I | C | C |
| Auditorías Internas | A | **A** | I | **R** | C | I | I | I |
| Capacitación en Seguridad | A | **A** | I | C | C | I | **R** | I |
| Gestión de Accesos | I | A | C | C | **R** | **A** | I | - |
| Cumplimiento Legal | A | C | I | **R** | I | I | C | **A** |
| Respuesta a Incidentes | I | **A** | C | **R** | **R** | C | C | C |
| Gestión de Vulnerabilidades | I | A | C | C | **R** | I | - | - |
| Clasificación de Información | I | A | I | C | I | **R** | I | - |
| Revisión de Contratos | A | C | I | I | - | I | I | **R** |
| BCP/DRP | A | **A** | **R** | C | C | C | C | - |
| Revisión Trimestral SGSI | **A** | **R** | C | C | I | I | I | I |

**Leyenda RACI:**
- **R** = Responsible (Responsable de ejecutar)
- **A** = Accountable (Autoridad final, rinde cuentas)
- **C** = Consulted (Debe ser consultado)
- **I** = Informed (Debe ser informado)

---

## 5. MATRIZ DE AUTORIDADES

| Autoridad / Decisión | CEO | CISO | CTO | Comité Seg |
|---------------------|-----|------|-----|------------|
| Aprobar política de seguridad | ✅ | Propone | Revisa | Recomienda |
| Asignar presupuesto anual seguridad | ✅ | Propone | - | Aprueba |
| Decisiones sobre riesgos CRÍTICOS | ✅ | Propone | Consulta | Recomienda |
| Decisiones sobre riesgos ALTOS | Informa | ✅ | Consulta | Aprueba |
| Decisiones sobre riesgos MEDIOS | - | ✅ | Consulta | Informa |
| Suspender sistemas por seguridad | Notifica | ✅ | Ejecuta | - |
| Aprobar excepciones a políticas | Notifica | ✅ | - | Revisa |
| Contratar personal de seguridad | ✅ | Propone | - | Consulta |
| Contratar consultores seguridad | Aprueba | ✅ | - | - |
| Autorizar accesos privilegiados | - | ✅ | Implementa | - |
| Iniciar investigaciones internas | Notifica | ✅ | Apoya | - |
| Reportar a autoridades | ✅ | Propone | - | Recomienda |

---

## 6. ORGANIZACIÓN DE CAPACITACIÓN Y AWARENESS

### 6.1. Responsabilidades por Rol

| Rol | Responsabilidad |
|-----|-----------------|
| **CISO** | Definir estrategia y contenidos de capacitación |
| **Coordinador de Seguridad** | Gestionar logística y calendario |
| **RRHH** | Coordinar asistencia y registro |
| **Equipo de Seguridad** | Desarrollar materiales y dictar talleres técnicos |
| **Gerentes** | Asegurar asistencia de su equipo |
| **Todos** | Asistir y completar capacitaciones obligatorias |

### 6.2. Programa de Capacitación por Rol

| Público | Capacitación | Frecuencia | Duración |
|---------|--------------|-----------|----------|
| **Nuevo personal** | Inducción en seguridad | Al ingreso | 2 horas |
| **Todo el personal** | Awareness general | Anual | 4 horas |
| **Personal técnico** | Capacitación técnica especializada | Semestral | 8 horas |
| **Administradores** | Gestión segura de sistemas | Trimestral | 4 horas |
| **Gerentes** | Gestión de riesgos y cumplimiento | Anual | 4 horas |
| **Desarrolladores** | Desarrollo seguro (SDLC) | Semestral | 8 horas |

---

## 7. PLAN DE TRANSICIÓN Y CONTINUIDAD DE ROLES

### 7.1. Sucesión de Roles Críticos

| Rol Crítico | Suplente Primario | Suplente Secundario |
|-------------|-------------------|---------------------|
| **CISO** | Coordinador de Seguridad | CTO |
| **CTO** | Líder de Infraestructura | Líder de Desarrollo |
| **Coordinador Seguridad** | Administrador Seg. Infraestructura | CISO (temporal) |
| **Líder CSIRT** | Analista de Seguridad Sr. | CISO |

### 7.2. Procedimientos de Sucesión

En caso de ausencia o salida de un rol crítico:
1. Activación automática del suplente primario
2. Notificación al Comité de Seguridad en 24 horas
3. Transferencia formal de responsabilidades (1 semana)
4. Inicio de proceso de contratación/promoción permanente
5. Capacitación del nuevo titular (2-4 semanas)

---

## 8. EVALUACIÓN DE DESEMPEÑO

### 8.1. KPIs por Rol

**CISO:**
- % de cumplimiento de plan anual de seguridad
- Nivel de riesgos residuales
- Tiempo de respuesta a incidentes críticos
- % de personal capacitado
- Cumplimiento presupuestario

**Coordinador de Seguridad:**
- % de políticas actualizadas a tiempo
- % de asistencia a capacitaciones
- Calidad de reportes al Comité
- % de compromisos del Comité cumplidos

**Equipo de Seguridad Técnica:**
- Tiempo de respuesta a incidentes
- % de vulnerabilidades remediadas a tiempo
- Uptime de sistemas de seguridad
- Número de falsos positivos (SIEM)

### 8.2. Evaluación Anual

- Evaluación formal de desempeño anual por CISO
- Revisión de objetivos individuales vs. cumplidos
- Identificación de necesidades de capacitación
- Definición de objetivos para próximo año

---

## 9. CONTACTOS Y ESCALAMIENTO

### 9.1. Directorio de Contactos Clave

| Rol | Nombre | Email | Teléfono | Emergencia 24/7 |
|-----|--------|-------|----------|-----------------|
| CEO | [Nombre] | ceo@stamfordhealth.cl | +56 51 XXX XXXX | +56 9 XXXX XXXX |
| CISO | [Nombre] | ciso@stamfordhealth.cl | +56 51 XXX XXXX | +56 9 XXXX XXXX |
| CTO | [Nombre] | cto@stamfordhealth.cl | +56 51 XXX XXXX | +56 9 XXXX XXXX |
| Coord. Seguridad | [Nombre] | seguridad@stamfordhealth.cl | +56 51 XXX XXXX | - |
| CSIRT | Equipo | csirt@stamfordhealth.cl | +56 51 XXX XXXX | +56 9 XXXX XXXX |

### 9.2. Matriz de Escalamiento

| Nivel | Situación | Contactar | Plazo |
|-------|-----------|-----------|-------|
| **Nivel 1** | Incidente menor | Equipo de Seguridad | Inmediato |
| **Nivel 2** | Incidente moderado | Coordinador + CISO | 2 horas |
| **Nivel 3** | Incidente crítico | CISO + CTO + CEO | 1 hora |
| **Nivel 4** | Crisis (brecha datos) | Comité completo + Asesor Legal | Inmediato |

---

## 10. REVISIÓN Y ACTUALIZACIÓN

Esta estructura organizativa será revisada:
- **Anualmente:** Revisión completa en enero de cada año
- **Semestralmente:** Revisión de contactos y suplencias
- **Ad-hoc:** Ante cambios organizacionales significativos

**Última revisión:** 15 de noviembre de 2025  
**Próxima revisión:** Enero de 2026

---

**FIN DEL DOCUMENTO**

*Este documento es propiedad de Stamford Health and Solution SpA.*
