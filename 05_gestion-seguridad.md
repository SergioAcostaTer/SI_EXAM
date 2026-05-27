# UA 5: Instrumentos para la Gestión de la Seguridad

---

## 1. ITIL (Information Technology Infrastructure Library)

### 1.1 Definición y Conceptos Fundamentales

| Concepto | Descripción |
|---|---|
| **¿Qué ES ITIL?** | Una **biblioteca de buenas prácticas** en gestión de Tecnologías de la Información. Recopila experiencias y conocimiento acumulado sobre cómo gestionar servicios TI de forma eficaz. |
| **¿Qué NO ES ITIL?** | ❌ Una norma europea de obligado cumplimiento |
| | ❌ Un conjunto de estándares técnicos |
| | ❌ Una metodología de trabajo (es una recopilación de buenas prácticas en gestión de **servicios**) |
| | ❌ Una norma de la familia ISO 27000 (esas son de seguridad de la información) |
| | ❌ Un conjunto de reglas rígidas que deban aplicarse sin adaptación |

> **Clave de examen:** ITIL = Biblioteca de buenas prácticas en gestión de servicios TI. No es norma, no es estándar, no es metodología, no es ISO 27000.

### 1.2 Origen

ITIL nace a raíz del **fracaso del proyecto Taurus** en los años 80. El gobierno del Reino Unido encargó a la CCTA (Central Computer and Telecommunications Agency) la recopilación de buenas prácticas en gestión de TI observadas tanto en el sector público como en el privado. El resultado fue la primera versión de ITIL.

| Hito | Año | Detalle |
|---|---|---|
| Proyecto Taurus | Años 80 | Fracaso de un gran proyecto informático del gobierno británico |
| Creación ITIL | Finales 80 | La CCTA recopila buenas prácticas de gestión TI |
| Evolución | 2000→ | ITIL se convierte en el marco de referencia mundial para ITSM |

### 1.3 Versiones de ITIL

| Versión | Año | Estructura | Objetivo Principal | Enfoque |
|---|---|---|---|---|
| **ITIL V2** | ~2001 | 7 libros | **Alinear** la tecnología con el negocio | Procesos (Service Support, Service Delivery) |
| **ITIL V3** | 2008 / 2011 | 5 libros | **Alinear/Integrar** la tecnología en el negocio | **Ciclo de Vida del Servicio** |
| **ITIL V4** | 2019 | Dimensiones, SVS, Cadena de Valor, Prácticas | Adaptación a la era digital | Industria 4.0, co-creación de valor, principios guía |

**Ejemplo real:** Una gran aseguradora española (Mapfre, Mutua Madrileña) adopta ITIL para estructurar su departamento TI: define un Service Desk único (ITIL V3 - Operación del Servicio), implanta gestión de cambios (Transición del Servicio) y establece catálogos de servicio (Diseño del Servicio). Esto reduce el tiempo de resolución de incidencias un 40%.

### 1.4 Ciclo de Vida del Servicio (ITIL V3)

El corazón de ITIL V3 son sus **5 etapas** (NO confundir con el ciclo PDCA de Deming):

| # | Etapa | Propósito | Ejemplo real |
|---|---|---|---|
| 1 | **Estrategia del Servicio** | Definir qué servicios ofrecer, a quién y con qué valor. | Un banco decide ofrecer banca móvil como servicio estratégico diferenciador. |
| 2 | **Diseño del Servicio** | Diseñar el servicio para que cumpla los requisitos de calidad, seguridad y disponibilidad. | Se diseña la app de banca móvil con requisitos de disponibilidad 24×7 y cifrado de datos. |
| 3 | **Transición del Servicio** | Construir, probar y desplegar el servicio sin impactar al negocio. | Se migran los datos de clientes a la nueva plataforma, con pruebas de rendimiento y plan de rollback. |
| 4 | **Operación del Servicio** | Operar el servicio en el día a día, gestionando incidencias y peticiones. | El Service Desk atiende a clientes que reportan fallos en la app; se monitoriza el rendimiento 24×7. |
| 5 | **Mejora Continua** | Analizar métricas y proponer mejoras iterativas. | Tras detectar que un 15% de transferencias fallan en hora punta, se escala la infraestructura cloud. |

> **Trampa de examen:** El Ciclo de Vida del Servicio **NO** es Plan → Do → Check → Act (PDCA de Deming). **NO** incluye etapas como "Publicación" o "Difusión". Son exactamente 5 etapas, en ese orden.

### 1.5 ITIL V4 (2019) — Novedades

- Introduce el **SVS** (Service Value System): cómo todos los componentes y actividades de la organización funcionan juntos para crear valor.
- Define **4 Dimensiones**: Organizaciones y Personas, Información y Tecnología, Socios y Proveedores, Flujos de Valor y Procesos.
- **Cadena de Valor del Servicio**: Planificar → Mejorar → Involucrar → Diseñar y Transicionar → Obtener/Construir → Entregar y Soportar.
- **7 Principios Guía**: Enfocarse en el valor, Empezar donde estés, Progresar iterativamente, Colaborar y promover visibilidad, Pensar y trabajar holísticamente, Mantenerlo simple y práctico, Optimizar y automatizar.

**Ejemplo real (ITIL V4):** Telefónica aplica ITIL V4 para su transformación digital: usa el SVS para alinear sus equipos de desarrollo, operaciones y proveedores cloud (AWS, Azure) en torno a la co-creación de valor para el cliente, aplicando principios Lean y Agile junto con las prácticas de ITIL.

---

## 2. Análisis de Riesgos

### 2.1 Terminología Básica

| Término | Definición | NO es... |
|---|---|---|
| **Activo** | Recurso software, hardware, personal, administrativo o funcional necesario para el funcionamiento del servicio. | Solo hardware. Incluye: bases de datos, aplicaciones, personal cualificado, reputación, infraestructuras, documentación. |
| **Vulnerabilidad** | **Debilidad** del sistema susceptible de ser explotada. | Una amenaza, un incidente, un riesgo. Es un tipo de DEBILIDAD (ej: puerto abierto, software sin parche, falta de formación). |
| **Amenaza** | Posibilidad de que se produzca una vulnerabilidad con éxito. Puede ser natural, humana accidental o humana intencionada. | Una vulnerabilidad. La amenaza explota la vulnerabilidad. |
| **Impacto** | Medida del grado de **DAÑO** producido sobre un activo. Cuantificable (económico, reputacional, operativo). | La importancia de la vulnerabilidad ni el número de activos afectados. |
| **Riesgo** | Probabilidad de que ocurra un **evento adverso** que supone un impacto negativo. **Riesgo = Daño × Probabilidad**. | Certeza de pérdida. Es una probabilidad ponderada. |
| **Incidente** | Hecho que **debe evitarse** pues causa impacto en el negocio. | Solo averías. Incluye: brechas de seguridad, fugas de datos, caídas de servicio, errores de configuración con consecuencias. |
| **Ataque** | Amenaza de terceros que **intencionadamente** buscan comprometer la seguridad. | Un error humano, una vulnerabilidad, una negligencia. Requiere INTENCIONALIDAD. |

> **Clave de examen — Pirámide conceptual:**
> Activo tiene → Vulnerabilidad (debilidad) → que es explotada por → Amenaza → generando un → Riesgo (probabilidad × daño) → que al materializarse se convierte en → Incidente. Si la amenaza es intencionada → Ataque.

### 2.2 Tipos de Riesgo

| Tipo | Características | Ejemplo |
|---|---|---|
| **Riesgos conocidos** | Pueden identificarse, analizarse y gestionarse de forma proactiva. | Se sabe que el datacenter está en zona sísmica → se refuerza la estructura antisísmica. |
| **Riesgos desconocidos** | Situaciones imprevistas que no permiten medidas a priori. Requieren estrategias de resiliencia general. | Un fallo en cascada por una combinación nunca antes vista de errores de configuración. |

### 2.3 Opciones para Tratar los Riesgos (4 estrategias)

| Estrategia | Descripción | Ejemplo real |
|---|---|---|
| **Mitigar** | Reducir la probabilidad o el impacto a un nivel aceptable. | Instalar un firewall y antivirus corporativo para reducir el riesgo de malware. |
| **Asumir** | Aceptar el riesgo conscientemente cuando el coste de tratarlo supera el beneficio. | Una PYME asume el riesgo de no tener datacenter redundante porque el coste es inviable. |
| **Transferir** | Desplazar el impacto a un tercero (normalmente mediante seguro o externalización). | Contratar un seguro de ciberriesgos con cobertura de pérdida de datos y responsabilidad civil. |
| **Eliminar** | Suprimir la causa del riesgo por completo (dejar de realizar la actividad que lo genera). | Cerrar un servicio web vulnerable que ya no es necesario para el negocio, eliminando el vector de ataque. |

> **Clave de examen:** Las 4 opciones son Mitigar, Asumir, Transferir y Eliminar. NO son 3 (sin Transferir), ni se limita a mitigar/asumir/eliminar.

### 2.4 Análisis de Riesgos — ¿En qué consiste?

El análisis de riesgos consiste en **AMBAS** de las siguientes:

1. **Identificar los riesgos** a los que están expuestos los activos del sistema de información.
2. **Identificar problemas de seguridad** que evidencian vulnerabilidades en los sistemas.

Es decir, combina la identificación de activos y sus vulnerabilidades con la evaluación de las amenazas y el impacto potencial.

**Ejemplo real (Sanidad):** Un hospital realiza análisis de riesgos sobre su sistema de historias clínicas electrónicas:
- Activo: base de datos de pacientes (datos sensibles).
- Vulnerabilidad: sistema operativo del servidor sin parches de seguridad.
- Amenaza: atacante externo que explota la vulnerabilidad para exfiltrar datos.
- Impacto: sanción por RGPD (hasta 4% facturación anual), daño reputacional irreversible.
- Riesgo calculado: Alta probabilidad × Impacto crítico = Riesgo Alto → **Mitigar** aplicando parches y segmentando la red.

### 2.5 Gestión del Riesgo

> **Definición:** Identificar y desplegar medidas técnicas y organizativas para **evitar, minimizar o controlar** los riesgos, eliminando o reduciendo el daño.

- **NO** es únicamente eliminar los riesgos (opción inviable en la mayoría de casos).
- **NO** es subcontratar la seguridad (eso sería una forma de transferir, no gestionar).
- **NO** es solo mitigar (la gestión incluye las 4 estrategias de tratamiento).

---

## 3. Metodologías de Análisis de Riesgos

### 3.1 Cuadro Comparativo

| Metodología | Origen | Año | Fases/Estructura | Enfoque principal |
|---|---|---|---|---|
| **MAGERIT III** | España (CNI/CCN) | 2012 | 3 libros (Método, Catálogo, Guías Técnicas) | Administraciones Públicas españolas. Análisis y **gestión** de riesgos. Obligatorio para cumplir el ENS. |
| **CRAMM** | Reino Unido | 1987 | 3 fases | Originalmente para gobierno UK. Adoptada por la OTAN. |
| **EBIOS** | Francia (ANSSI) | 1995 | 5 fases | Sector público francés. Eventos temidos y escenarios de riesgo. |
| **ISO/IEC 27005** | Internacional | 2008/2011 | Modelo PDCA (Plan-Do-Check-Act) genérico | Estándar genérico para gestión de riesgos en el marco de un SGSI (ISO 27001). |
| **UNE 71504** | España (AENOR) | 2008 | — | Metodología española de análisis de riesgos. |

> **Clave de examen:** Las metodologías de análisis de riesgos **reconocidas** son: **CRAMM, EBIOS y MAGERIT II** (todas ellas). ITIL e ISO 27001 **NO** son metodologías de análisis de riesgos.

### 3.2 MAGERIT III (Detalle)

**Origen:** Desarrollada por el Consejo Superior de Administración Electrónica de España, mantenida por el CCN-CNI (Centro Criptológico Nacional). Es la metodología de referencia para el cumplimiento del **Esquema Nacional de Seguridad (ENS)** en las Administraciones Públicas españolas.

**Estructura (3 libros):**

| Libro | Contenido |
|---|---|
| **Libro I: Método** | Descripción detallada del método de análisis de riesgos: caracterización de activos, valoración de dependencias, identificación y valoración de amenazas, evaluación del impacto y el riesgo, identificación de salvaguardas adecuadas. |
| **Libro II: Catálogo de Elementos** | Catálogo estructurado de activos, amenazas (con tasas de ocurrencia) y salvaguardas típicos. Sirve de guía para el analista. |
| **Libro III: Guías Técnicas** | Guías complementarias: cómo desarrollar las tareas del proyecto, cómo integrar MAGERIT con otras metodologías, modelos de madurez, etc. |

**Ejemplo real:** La Agencia Tributaria Española utilizó MAGERIT para analizar los riesgos de sus sistemas de información tributaria, identificando más de 500 activos y aplicando salvaguardas como cifrado de datos en tránsito, doble factor de autenticación para funcionarios, y segregación de funciones en entornos virtualizados.

**Herramienta asociada:** PILAR (entorno de trabajo software del CCN para realizar análisis de riesgos siguiendo MAGERIT). PILAR = Plataforma Informática para el Análisis y Gestión de Riesgos.

### 3.3 CRAMM (CCTA Risk Analysis and Management Method)

| Característica | Detalle |
|---|---|
| Origen | Reino Unido, 1987 |
| 3 fases | 1. Identificación y valoración de activos. 2. Identificación de amenazas y vulnerabilidades. 3. Selección de contramedidas. |
| Adopción | Gobiernos, sector público británico, OTAN para sistemas clasificados. |
| Fortaleza | Integra la valoración cualitativa y cuantitativa con una base de datos de amenazas y contramedidas. |

### 3.4 EBIOS (Expression des Besoins et Identification des Objectifs de Sécurité)

| Característica | Detalle |
|---|---|
| Origen | Francia, ANSSI (Agence Nationale de la Sécurité des Systèmes d'Information) |
| 5 fases | 1. Estudio del contexto. 2. Estudio de eventos temidos. 3. Elaboración de escenarios de riesgo. 4. Estudio de riesgos (gravedad y probabilidad). 5. Estudio de medidas de tratamiento. |
| Enfoque | Orientado a "eventos temidos" y "escenarios de riesgo", muy gráfico y participativo. |

### 3.5 ISO/IEC 27005 — Gestión de Riesgos en la Seguridad de la Información

- Es un estándar **genérico**, aplicable a organizaciones de cualquier tipo que ya tengan implantado (o planeen implantar) un SGSI según ISO 27001.
- Sigue el modelo **PDCA** (Plan, Do, Check, Act).
- Proporciona directrices para la gestión del riesgo, pero no especifica un método concreto: puede adaptarse a MAGERIT, CRAMM, etc.

**Ejemplo real:** Una multinacional de retail certificada en ISO 27001 realiza su análisis de riesgos anual siguiendo ISO 27005 como marco, pero utilizando MAGERIT como método concreto para la identificación y valoración de activos.

---

## 4. Auditoría Informática

### 4.1 Definición

> Recoger, agrupar y evaluar **evidencias** para determinar si un Sistema de Información realiza de forma **eficaz** los fines de la organización y utiliza **eficientemente** los recursos.

También cubre:
- La **integridad de los datos** (que la información no ha sido alterada de forma no autorizada).
- La **protección del activo empresarial** (salvaguarda de los recursos de información).

> **NO confundir** auditoría informática con:
> - **Análisis de seguridad** (hacking ético, pentesting): eso es ofensivo/técnico.
> - **Análisis de riesgos**: identificar amenazas y proponer salvaguardas → eso es análisis de riesgos, **NO** auditoría.

### 4.2 Objetivos de la Auditoría Informática

- ✅ **Verificar disponibilidad** de los sistemas y servicios tecnológicos.
- ✅ **Verificar controles** de integridad, confidencialidad y autenticación.
- ✅ **Verificar cumplimiento normativo** (LOPD/RGPD, ENS, ISO 27001, etc.).
- ✅ **Eliminar/minimizar** la probabilidad de pérdida de información.
- ✅ **Verificar el control interno** de la función informática (segregación de funciones, gestión de accesos, etc.).
- ❌ **Identificar amenazas y proponer salvaguardas** → eso NO es auditoría, es análisis de riesgos.

> **Examen:** A la pregunta de cuáles son los objetivos de la auditoría informática, son correctas **AMBAS** opciones C y D (cuando aparecen combinadas verificaciones de disponibilidad/integridad y control interno/cumplimiento).

### 4.3 Tipos de Auditoría Informática

| Tipo | Descripción | Ejemplo real |
|---|---|---|
| **Auditoría de datos** | Revisión de la calidad, integridad y protección de los datos. Clasificación de la información según criticidad. | Auditar la base de datos de RRHH para verificar que los datos de nómina solo sean accesibles por personal autorizado. |
| **Auditoría de comunicaciones** | Evaluación de la seguridad y eficiencia de las redes y sistemas de comunicación. | Verificar que las VPN de teletrabajo usan cifrado AES-256 y que los cortafuegos segmentan correctamente las subredes. |
| **Auditoría legal/LOPD/RGPD** | Verificar el cumplimiento de la normativa de protección de datos personales. | Revisar el registro de actividades de tratamiento, consentimientos de clientes, y contratos de encargados de tratamiento. |
| **Auditoría de seguridad** | Evaluación de controles técnicos y organizativos de seguridad de la información. | Revisar políticas de contraseñas, control de acceso físico y lógico, registros de auditoría (logs). |
| **Auditoría de sistemas** | Verificar la eficacia y eficiencia de los sistemas operativos y plataformas. | Auditar la configuración de servidores Linux según estándares CIS Benchmark. |
| **Auditoría de aplicaciones** | Evaluar el desarrollo, despliegue y mantenimiento del software. | Revisar la metodología de desarrollo seguro (SDL), pruebas de seguridad en el pipeline CI/CD. |

> **Examen:** A la pregunta "¿Qué tipos de auditoría informática existen?", la respuesta es **TODAS son correctas** cuando aparecen como opciones: de datos, de comunicaciones, legal de la LOPD/RGPD, de seguridad, etc.

### 4.4 Formas de Desarrollar una Auditoría

| Enfoque | Descripción | Técnicas |
|---|---|---|
| **Alrededor del ordenador** | Revisión del entorno que rodea al sistema sin acceder directamente a los programas ni datos. | Entrevistas, revisión documental, inspección física, análisis de procedimientos y organigramas. |
| **A través del ordenador** | Se analizan los procesos automatizados internos del sistema, los programas y los datos. | Trazas de ejecución, revisión de código, pruebas lógicas de controles internos, análisis de logs. |
| **Con el ordenador** | Se utilizan herramientas informáticas auxiliares para realizar pruebas y simulaciones sobre el sistema auditado. | Software de auditoría generalizado (ACL, IDEA), herramientas CAAT (Computer-Assisted Audit Techniques), scripts de verificación masiva. |

### 4.5 Referencia Técnica: CCN-STIC 802

La guía **CCN-STIC 802** del Centro Criptológico Nacional es la guía de **Auditoría del Esquema Nacional de Seguridad (ENS)**. Establece:

- El procedimiento de auditoría para verificar el cumplimiento del ENS.
- Los criterios de evaluación.
- Las evidencias que deben recogerse.
- Los requisitos del equipo auditor.

### 4.6 Dictamen Final de Auditoría

| Dictamen | Significado |
|---|---|
| **Conforme** | El sistema auditado cumple sustancialmente los requisitos y controles esperados. Sin deficiencias significativas. |
| **Conforme con deficiencias** | Se han encontrado deficiencias que no invalidan globalmente el sistema, pero requieren acciones correctivas. |
| **No conforme** | Se han detectado incumplimientos graves que comprometen significativamente los objetivos del sistema. |

**Ejemplo real:** Una auditoría del ENS sobre la plataforma de licitación electrónica del Estado arroja "Conforme con deficiencias" porque, aunque los controles de acceso son correctos, el registro de auditoría (logging) no retiene los logs durante el período mínimo exigido de 1 año.

### 4.7 Resultados de una Auditoría

El resultado principal de una auditoría es:

> **Evidencias de los riesgos** asociados a los sistemas que soportan la información, y en su caso, la identificación de salvaguardas insuficientes o ausentes.

> **Trampa de examen:** No es "propuesta de salvaguardas" (eso es análisis de riesgos). Es "evidencias" de la situación real, tanto de los riesgos detectados como de los controles existentes.

---

## 5. Plan Director de Seguridad

### 5.1 Definición

> Define la **estrategia en seguridad TIC** de la organización durante un período determinado (generalmente 2-4 años), estableciendo objetivos, acciones, recursos y plazos.

- **NO** es solamente seguridad física y lógica.
- **NO** es la estrategia de negocio general.
- **ES** el documento rector que marca el rumbo de la seguridad de la información en la organización a medio-largo plazo.

### 5.2 Objetivos del Plan Director de Seguridad

| Objetivo | Descripción |
|---|---|
| **Definir objetivos y criterios básicos** en seguridad de la información | Establecer el "norte" de la seguridad: qué nivel se quiere alcanzar. |
| **Establecer el marco normativo y cumplimiento legal** | Asegurar que se cumplen RGPD, LSSI, ENS, LOPD, normativa sectorial (banca, sanidad, etc.). |
| **Conocer y planificar costes e inversiones** | Dimensionar el presupuesto necesario para alcanzar los niveles de seguridad deseados. |
| **Aportar confianza** sobre los servicios ofrecidos | Generar seguridad en clientes, proveedores y terceros sobre la fiabilidad de los servicios. |

- ❌ **NO** es objetivo específico "realizar análisis de riesgos" (eso es un medio, no un fin).
- ❌ **NO** es objetivo "cumplir la LSSIE" (Ley de Servicios de la Sociedad de la Información — la seguridad no solo se limita a esa ley).

### 5.3 Factores Clave de Éxito

| # | Factor | Importancia |
|---|---|---|
| 1 | **Compromiso de la Dirección** | ⭐ **El más importante.** Sin apoyo explícito y sostenido de la alta dirección, el Plan Director está abocado al fracaso. |
| 2 | **Designar un responsable del Plan** | Una persona o comité con autoridad y responsabilidad clara para liderar el Plan. |
| 3 | **Marco metodológico definido** | Usar una metodología reconocida (ISO 27001, MAGERIT, etc.) para estructurar el análisis y las acciones. |
| 4 | **Recursos y medios adecuados** | Presupuesto, personal, herramientas y tiempo suficientes. |
| 5 | **Seguimiento permanente** | Indicadores de cumplimiento (KPI), revisiones periódicas, cuadros de mando. |

### 5.4 Norma Básica de Referencia

La **ISO/IEC 27002** (Código de Buenas Prácticas para los Controles de Seguridad de la Información) sirve como catálogo de controles de referencia sobre los que se estructura el Plan Director de Seguridad.

> Relación clave: ISO 27001 define los requisitos del SGSI, ISO 27002 proporciona el catálogo de controles que se implementan en el Plan Director.

### 5.5 Resultados del Plan Director

| Resultado | Descripción |
|---|---|
| **Nivel de seguridad actual** | Diagnóstico de la situación de partida (AS-IS). |
| **Nivel de seguridad deseado** | Objetivo a alcanzar (TO-BE). |
| **Necesidades identificadas** | Brechas entre la situación actual y la deseada (GAP analysis). |
| **Hoja de ruta** | Secuencia temporal de proyectos y acciones priorizadas. |
| **Estudio económico** | Presupuesto estimado con coste de inversión y coste operativo recurrente. |

**Ejemplo real:** Una universidad pública española desarrolla su Plan Director de Seguridad 2024-2027:
- Situación actual: 40 servicios web sin certificado SSL, 300 cuentas de usuario sin política de contraseñas robusta.
- Situación deseada: todos los servicios con HTTPS y autenticación federada (eduGAIN/SIR), acceso multrifactor para servicios críticos.
- Hoja de ruta: Año 1 → implantar MFA y reforzar políticas de contraseñas. Año 2 → migrar sistemas legacy. Año 3 → certificación ENS categoría media.
- Presupuesto: 1.2M€ distribuidos en 3 años.

---

## 6. Plan de Respuesta ante Incidentes

### 6.1 Definición

> Documento que detalla una relación de **tareas y actividades** para dar respuesta a cualquier incidente **genérico** que afecte a la **seguridad de la información**.

- **NO** es un plan para "cualquier incidente de la organización" (demasiado amplio: solo cubre incidentes de seguridad de la información).
- **NO** es solo documentar la seguridad de la organización.
- **NO** es simplemente cumplir con un requisito legal (aunque también ayude a ello).

### 6.2 Elementos del Plan de Respuesta ante Incidentes

| Elemento | Descripción | Ejemplo real |
|---|---|---|
| **CSIRT** (Computer Security Incident Response Team) | Equipo de respuesta, roles definidos (coordinador, analistas, responsables de comunicación). Contactos 24×7. | El CSIRT del INCIBE en España coordina la respuesta a ciberincidentes en ciudadanía y empresas. |
| **Procedimientos documentados** | Pasos detallados para cada tipo de incidente grave: ransomware, fuga de datos, DDoS, intrusión. | Playbook de respuesta a ransomware: aislar segmento de red afectado, identificar variante, evaluar backups, notificar a AEPD si hay datos personales. |
| **Detección y análisis** | Métodos y herramientas para detectar incidentes (SIEM, IDS/IPS, antivirus EDR, alertas de usuarios). | Un SIEM (Splunk, ELK, Elastic) correlaciona eventos: múltiples intentos fallidos de login desde IP extranjera + escaneo de puertos → alerta de intrusión. |
| **Contención** | Acciones para limitar el daño y evitar la propagación. | Desconectar de la red un servidor comprometido, bloquear una IP atacante en el firewall perimetral. |
| **Erradicación** | Eliminar la causa raíz del incidente. | Eliminar malware, cerrar puertas traseras, parchear la vulnerabilidad explotada. |
| **Recuperación** | Restaurar los sistemas y servicios a su estado operativo normal. | Restaurar desde backup, validar integridad de datos, re-conectar servicios progresivamente. |
| **Comunicación** | A quién informar, cuándo y cómo: dirección, usuarios, afectados, autoridad de control (AEPD), fuerzas de seguridad si procede. | Protocolo de notificación: < 72 h desde detección para incidentes con datos personales (RGPD), comunicado público si hay impacto masivo. |
| **Valoración y lecciones aprendidas** | Análisis post-mortem del incidente: qué falló, qué funcionó, cómo evitar que se repita. | Reunión post-incidente: el ataque fue por spear-phishing → mejorar formación de empleados en concienciación. |
| **Revisión y mejora** | Actualizar el plan de respuesta tras cada incidente real o simulacro. | Incorporar nuevas IoCs (Indicators of Compromise) al SIEM, añadir reglas de detección. |

### 6.3 Ciclo de Respuesta a Incidentes (NIST SP 800-61)

```
Preparación → Detección y Análisis → Contención, Erradicación y Recuperación → Actividad Post-Incidente
     ↑                                                                                      |
     └──────────────────────────────────────────────────────────────────────────────────────┘
                                        (retroalimentación continua)
```

**Ejemplo real (Ransomware en el SEPE, 2021):**
- El Servicio Público de Empleo Estatal sufrió un ataque de ransomware.
- **Detección:** Se detectó la mañana del 9 de marzo al no poder acceder a sistemas internos.
- **Contención:** Se aislaron los equipos afectados y se cortó el acceso desde Internet.
- **Erradicación:** Colaboración con el CCN-CERT para analizar el malware y eliminarlo.
- **Recuperación:** Restauración progresiva de servicios (la web del SEPE funcionaba, pero la intranet tardó varios días en restaurarse).
- **Comunicación:** Nota de prensa oficial del Ministerio. Notificación al CCN-CERT.
- **Lecciones:** Se reforzó la segmentación de red y se implantó EDR en todos los endpoints.

---

## 7. Plan de Continuidad del Negocio (PCN / SGCN)

### 7.1 Definición

El Plan de Continuidad del Negocio (PCN) o Sistema de Gestión de la Continuidad del Negocio (SGCN) es el conjunto de estrategias, planes y procedimientos que permiten a una organización **seguir funcionando** en caso de una interrupción grave, minimizando el impacto sobre sus actividades críticas.

### 7.2 Métricas Clave: RTO, MTD y RPO

| Métrica | Significado | Definición | Ejemplo |
|---|---|---|---|
| **RPO** (Recovery Point Objective) | Objetivo de Punto de Recuperación | Cantidad máxima de datos que la organización se puede permitir perder, medida en tiempo. Define la frecuencia de los backups. | RPO = 1 hora → Los backups deben realizarse cada hora. En caso de desastre, se pierden como máximo 60 minutos de datos. Un banco con RPO de 15 minutos usa replicación síncrona de bases de datos. |
| **RTO** (Recovery Time Objective) | Objetivo de Tiempo de Recuperación | Tiempo máximo tolerable para restaurar el servicio tras una interrupción. Define cuánto puede estar caído un sistema. | RTO = 4 horas → Si el ERP corporativo cae a las 10:00, debe estar operativo antes de las 14:00. Un hospital con RTO de 5 minutos para el sistema de urgencias necesita un datacenter en caliente (hot site). |
| **MTD** (Maximum Tolerable Downtime) | Tiempo Máximo de Inactividad Tolerable | Límite absoluto de tiempo que un proceso/servicio puede estar inactivo antes de que las consecuencias sean catastróficas para la organización. | MTD = 24 horas para la pasarela de pagos de un e-commerce: tras 24 horas sin poder cobrar, las pérdidas son irrecuperables y puede haber quiebra. |

> **Relación entre métricas:** RTO ≤ MTD (el objetivo de recuperación debe ser menor o igual que el tiempo máximo tolerable). RPO determina la estrategia de backup (a menor RPO, más costosa la solución).

```
       RPO                          RTO                        MTD
←───|───|───────────────────────────|──────────────────────────|────→ tiempo
    ↑                               ↑                          ↑
 Último backup                  Recuperación                Colapso del negocio
 (pérdida máxima               del servicio                 si no se recupera
  de datos aceptable)
```

### 7.3 Norma de Referencia: ISO 22301

La **ISO 22301** es el estándar internacional que especifica los requisitos para un Sistema de Gestión de la Continuidad del Negocio (SGCN):

- Es certificable (una organización puede obtener certificación ISO 22301).
- Alineada con ISO 27001 (SGSI), ISO 9001 (Calidad) e ISO 14001 (Medio Ambiente) mediante la estructura de alto nivel (HLS – High Level Structure).
- Fomenta el ciclo PDCA de mejora continua.

**Ejemplo real:** Eurocontrol (gestión del tráfico aéreo europeo) está certificado en ISO 22301: sus centros de control tienen redundancia completa (dos centros que pueden asumir el tráfico del otro en minutos), con un RTO de menos de 5 minutos para sistemas de control aéreo.

### 7.4 Fases del PCN

| Fase | Descripción | Actividades Clave |
|---|---|---|
| **1. Alcance y Contexto** | Definir qué partes de la organización cubre el PCN y en qué contexto opera. | Identificar productos/servicios críticos, partes interesadas, requisitos legales y regulatorios. Análisis del contexto externo e interno. |
| **2. Análisis / BIA** (Business Impact Analysis) | Evaluar el impacto de una interrupción en cada proceso de negocio y determinar los requisitos de continuidad. | Identificar procesos críticos, calcular RTO, MTD y RPO para cada proceso, priorizar la recuperación según impacto en el negocio. |
| **3. Estrategia** | Definir las estrategias de continuidad adecuadas para cada proceso crítico. | Seleccionar alternativas de recuperación: sitio alternativo (hot site, warm site, cold site), teletrabajo, proveedores alternativos, redundancia de sistemas. |
| **4. Respuesta / Planes** | Desarrollar los planes de continuidad detallados, incluyendo recursos, equipos y protocolos. | Elaborar plan de respuesta ante emergencias, plan de recuperación de TI (DRP – Disaster Recovery Plan), plan de continuidad de procesos de negocio. |
| **5. Pruebas y Mantenimiento** | Verificar que los planes funcionan y mantenerlos actualizados. | Simulacros periódicos (al menos 1 al año), pruebas de restauración de backups, revisión y actualización tras cambios organizativos o tecnológicos. |

### 7.5 Tipos de Sitios Alternativos (DRP)

| Tipo | Características | Coste | RTO típico |
|---|---|---|---|
| **Cold site** | Espacio físico vacío con electricidad y climatización, sin equipamiento. Requiere instalar todo. | Bajo | Días / Semanas |
| **Warm site** | Espacio con hardware y conectividad básica, pero sin datos sincronizados. Requiere restauración de backups. | Medio | Horas / Días |
| **Hot site** | Réplica completa del entorno de producción, con datos sincronizados en tiempo real. Funciona en minutos. | Alto | Minutos / Horas |

**Ejemplo real:** Un servicio cloud como AWS o Azure ofrece Disaster Recovery as a Service (DRaaS) con RTO de minutos y RPO cercano a cero mediante replicación entre regiones.

---

## Resumen para el Examen

### Conceptos "Filtro" (preguntas trampa detectadas)

| Pregunta típica | Respuesta correcta |
|---|---|
| ITIL es... | Una **biblioteca de buenas prácticas** en gestión de servicios TI |
| ITIL es una norma europea de obligado cumplimiento | ❌ **NO** |
| ITIL es una norma ISO 27000 | ❌ **NO** |
| ITIL es una metodología de trabajo | ❌ **NO** (es recopilación de buenas prácticas en gestión de SERVICIOS) |
| Objetivo ITIL V2 | **Alinear** la tecnología con el negocio |
| Objetivo ITIL V3 | **Alinear / Integrar** la tecnología en el negocio |
| Ciclo de Vida del Servicio ITIL V3 | Estrategia → Diseño → Transición → Operación → Mejora Continua (5 etapas) |
| Ciclo de Vida = PDCA (Plan, Do, Check, Act) | ❌ **NO** (eso es Deming) |
| ¿Incluye "Publicación" o "Difusión" en el ciclo? | ❌ **NO** |
| ¿Qué es un Activo? | Recurso software, hardware, personal, administrativo o funcional |
| Activo = solo hardware | ❌ **NO** |
| Vulnerabilidad es... | Una **debilidad** del sistema |
| Vulnerabilidad = amenaza | ❌ **NO** |
| Riesgo = | Daño × Probabilidad |
| Ataque se caracteriza por... | **Intencionalidad** de terceros |
| Opciones para tratar riesgos (4) | **Mitigar, Asumir, Transferir, Eliminar** |
| Análisis de riesgos consiste en... | Identificar riesgos + identificar vulnerabilidades (**AMBAS**) |
| Gestión del riesgo = solo eliminar | ❌ **NO** (es evitar, minimizar o controlar) |
| Metodologías reconocidas de análisis de riesgos | **CRAMM, EBIOS y MAGERIT II** (todas) |
| ITIL es metodología de análisis de riesgos | ❌ **NO** |
| ISO 27001 es metodología de análisis de riesgos | ❌ **NO** |
| MAGERIT III — libros | 3 libros: Método, Catálogo, Guías Técnicas |
| MAGERIT III — origen | Española, CNI/CCN, enfocada a AA.PP. |
| MAGERIT es metodología de... | Análisis y **gestión** de riesgos |
| Auditoría = identificar amenazas y proponer salvaguardas | ❌ **NO** (eso es análisis de riesgos) |
| Tipos de auditoría | De datos, comunicaciones, legal LOPD/RGPD → **TODAS** |
| Formas de auditoría | Alrededor, a través, y con el ordenador |
| Guía de auditoría del ENS | **CCN-STIC 802** |
| Dictámenes de auditoría | Conforme, Conforme con deficiencias, No conforme |
| Plan Director de Seguridad define... | Estrategia en seguridad TIC de la organización |
| Factor clave de éxito principal del Plan Director | **Compromiso de la Dirección** |
| Norma básica del Plan Director | **ISO 27002** |
| Plan de Respuesta ante Incidentes cubre... | Incidentes genéricos de **seguridad de la información** |
| PCN — ISO de referencia | **ISO 22301** |
| RPO → | Punto de Recuperación (pérdida máxima de datos) |
| RTO → | Tiempo de Recuperación (tiempo máximo para restaurar) |
| MTD → | Tiempo Máximo de Inactividad Tolerable |

### Jerarquía de Normas y Marcos

```
ITIL → Buenas prácticas de gestión de servicios TI
ISO 27001 → Requisitos del SGSI (Sistema de Gestión de Seguridad de la Información)
ISO 27002 → Catálogo de controles (Plan Director de Seguridad)
ISO 27005 → Directrices de gestión de riesgos (modelo PDCA)
ISO 22301 → Sistema de Gestión de Continuidad del Negocio
MAGERIT III → Metodología de análisis y gestión de riesgos (España, AA.PP.)
CRAMM → Metodología de análisis y gestión de riesgos (UK, OTAN)
EBIOS → Metodología de análisis y gestión de riesgos (Francia, ANSSI)
ENS → Esquema Nacional de Seguridad (España, ámbito legal-administrativo)
CCN-STIC 802 → Guía de Auditoría del ENS
```

### Truco Mnemotécnico para las 5 Etapas de ITIL V3

**"E D T O M"** → **E**strategia, **D**iseño, **T**ransición, **O**peración, **M**ejora Continua

**Frase:** *"El Director Técnico Opera Mejoras"*

---

*Documento elaborado como material de referencia para la UA 5: Instrumentos para la Gestión de la Seguridad.*
