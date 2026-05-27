# UA 5: Instrumentos para la Gestion de la Seguridad

> **Navegacion:**
> - [← README](../README.md)
> - [← Tema 4](04-mecanismos-defensa.md)
> - [GLOSARIO](../GLOSARIO.md)
> - [Chuleta numerica](08-cheat-sheet-numeros.md)
> - [Tema 6 →](06-legislacion-normativa.md)

---

## 1. ITIL (Information Technology Infrastructure Library)

### 1.1 Definicion y Conceptos Fundamentales

| Concepto | Descripcion |
|---|---|
| **Que ES ITIL?** | Una **biblioteca de buenas practicas** en gestion de Tecnologias de la Informacion. Recopila experiencias y conocimiento acumulado sobre como gestionar servicios TI de forma eficaz. Es el **estandar "de facto" en buenas practicas de provision de servicios de TIs**. |
| **Que NO ES ITIL?** | ❌ Una norma europea de obligado cumplimiento |
| | ❌ Un conjunto de estandares tecnicos |
| | ❌ Una metodologia de trabajo (es una recopilacion de buenas practicas en gestion de **servicios**) |
| | ❌ Una norma de la familia ISO 27000 (esas son de seguridad de la informacion) |
| | ❌ Un conjunto de reglas rigidas que deban aplicarse sin adaptacion |

> **Clave de examen:** ITIL = Biblioteca de buenas practicas en gestion de servicios TI. No es norma, no es estandar, no es metodologia, no es ISO 27000.

### 1.2 Origen

ITIL nace a raiz del **fracaso del proyecto Taurus** en los anos 80. El gobierno del Reino Unido encargo a la CCTA (Central Computer and Telecommunications Agency) la recopilacion de buenas practicas en gestion de TI observadas tanto en el sector publico como en el privado. El resultado fue la primera version de ITIL.

| Hito | Ano | Detalle |
|---|---|---|
| Proyecto Taurus | Anos 80 | Fracaso de un gran proyecto informatico del gobierno britanico |
| Creacion ITIL | Finales 80 | La CCTA recopila buenas practicas de gestion TI |
| Evolucion | 2000→ | ITIL se convierte en el marco de referencia mundial para ITSM |

> **Evolucion de la biblioteca:** La biblioteca original de ITIL contaba con **50 libros**. En **ITIL V2** se redujo a **7 libros**, y en **ITIL V3** se estructuro en **5 libros** (uno por cada fase del Ciclo de Vida del Servicio).

### 1.3 Versiones de ITIL

| Version | Ano | Estructura | Objetivo Principal | Enfoque |
|---|---|---|---|---|
| **ITIL V2** | ~2001 | 7 libros | **Alinear** la tecnologia con el Negocio | Procesos (Service Support, Service Delivery) |
| **ITIL V3** | 2008 / ITIL V2011 | 5 libros | **Integrar** la tecnologia en el Negocio | **Ciclo de Vida del Servicio** |
| **ITIL V4** | 2019 | Dimensiones, SVS, Cadena de Valor, Practicas | Adaptacion a la era digital | Industria 4.0, co-creacion de valor, principios guia |

> **Clave de examen:** ITIL V2 busca **ALINEAR** la tecnologia con el negocio. ITIL V3 busca **INTEGRAR** la tecnologia en el negocio. Son conceptos distintos.

**Ejemplo real:** Una gran aseguradora espanola (Mapfre, Mutua Madrilena) adopta ITIL para estructurar su departamento TI: define un Service Desk unico (ITIL V3 - Operacion del Servicio), implanta gestion de cambios (Transicion del Servicio) y establece catalogos de servicio (Diseno del Servicio). Esto reduce el tiempo de resolucion de incidencias un 40%.

### 1.4 Ciclo de Vida del Servicio (ITIL V3)

El corazon de ITIL V3 son sus **5 etapas** (NO confundir con el ciclo PDCA de Deming):

| # | Etapa | Proposito | Ejemplo real |
|---|---|---|---|
| 1 | **Estrategia del Servicio** | Definir que servicios ofrecer, a quien y con que valor. | Un banco decide ofrecer banca movil como servicio estrategico diferenciador. |
| 2 | **Diseno del Servicio** | Disenar el servicio para que cumpla los requisitos de calidad, seguridad y disponibilidad. | Se disena la app de banca movil con requisitos de disponibilidad 24x7 y cifrado de datos. |
| 3 | **Transicion del Servicio** | Construir, probar y desplegar el servicio sin impactar al negocio. | Se migran los datos de clientes a la nueva plataforma, con pruebas de rendimiento y plan de rollback. |
| 4 | **Operacion del Servicio** | Operar el servicio en el dia a dia, gestionando incidencias y peticiones. | El Service Desk atiende a clientes que reportan fallos en la app; se monitoriza el rendimiento 24x7. |
| 5 | **Mejora Continua** | Analizar metricas y proponer mejoras iterativas. | Tras detectar que un 15% de transferencias fallan en hora punta, se escala la infraestructura cloud. |

> **Trampa de examen:** El Ciclo de Vida del Servicio **NO** es Plan → Do → Check → Act (PDCA de Deming). **NO** incluye etapas como "Publicacion" o "Difusion". Son exactamente 5 etapas, en ese orden.

> **Actividades y Procesos en ITIL V3:** Cada fase del Ciclo de Vida se compone de **Actividades** (tareas importantes dentro de la fase) y **Procesos** (conjunto de actividades con un objetivo especifico). Esta distincion es fundamental para entender la estructura de ITIL V3.

### 1.5 ITIL V4 (2019) -- Novedades

- Introduce el **SVS** (Service Value System): como todos los componentes y actividades de la organizacion funcionan juntos para crear valor.
- Define **4 Dimensiones**: Organizaciones y Personas, Informacion y Tecnologia, Socios y Proveedores, Flujos de Valor y Procesos.
- **Cadena de Valor del Servicio**: Planificar → Mejorar → Involucrar → Disenar y Transicionar → Obtener/Construir → Entregar y Soportar.
- **7 Principios Guia**: Enfocarse en el valor, Empezar donde estes, Progresar iterativamente, Colaborar y promover visibilidad, Pensar y trabajar holisticamente, Mantenerlo simple y practico, Optimizar y automatizar.
- **En lugar de hablar de procesos, se utiliza el concepto de practica** (Practice): enfoque mas amplio y flexible que los procesos tradicionales de ITIL V3.
- **Integracion con metodologias modernas:** ITIL V4 se integra explicitamente con **Agile, DevOps, Lean** y **Gobierno TI**, reconociendo que las organizaciones modernas utilizan multiples marcos de trabajo simultaneamente.

**Ejemplo real (ITIL V4):** Telefonica aplica ITIL V4 para su transformacion digital: usa el SVS para alinear sus equipos de desarrollo, operaciones y proveedores cloud (AWS, Azure) en torno a la co-creacion de valor para el cliente, aplicando principios Lean y Agile junto con las practicas de ITIL.

### 1.6 Definiciones Formales de Valor

| Concepto | Definicion |
|---|---|
| **Valor** | **Funcionalidad** (lo que recibe el cliente: el servicio en si, lo que hace) + **Garantia** (la forma en como se proporciona: disponibilidad, rendimiento, seguridad, continuidad) |
| **Funcionalidad** | El "que": las caracteristicas y capacidades del servicio que el cliente utiliza. |
| **Garantia** | El "como": la calidad con la que se entrega el servicio (niveles de servicio, disponibilidad, seguridad). |

> **Clave:** Un servicio puede tener buena funcionalidad pero mala garantia (ej: la app hace todo lo necesario pero se cae cada 2 horas), o viceversa. El valor real solo se alcanza cuando ambas dimensiones estan presentes.

---

## 2. Analisis de Riesgos

### 2.1 Terminologia Basica

| Termino | Definicion | NO es... |
|---|---|---|
| **Activo** | Recurso software, hardware, personal, administrativo o funcional necesario para el funcionamiento del servicio. | Solo hardware. Incluye: bases de datos, aplicaciones, personal cualificado, reputacion, infraestructuras, documentacion. |
| **Vulnerabilidad** | **Debilidad** del sistema susceptible de ser explotada. | Una amenaza, un incidente, un riesgo. Es un tipo de DEBILIDAD (ej: puerto abierto, software sin parche, falta de formacion). |
| **Amenaza** | Posibilidad de que se produzca una vulnerabilidad con exito. Puede ser natural, humana accidental o humana intencionada. | Una vulnerabilidad. La amenaza explota la vulnerabilidad. |
| **Impacto** | Medida del grado de **DANO** producido sobre un activo. Cuantificable (economico, reputacional, operativo). | La importancia de la vulnerabilidad ni el numero de activos afectados. |
| **Riesgo** | Probabilidad de que ocurra un **evento adverso** que supone un impacto negativo. **Riesgo = Dano x Probabilidad**. | Certeza de perdida. Es una probabilidad ponderada. |
| **Incidente** | Hecho que **debe evitarse** pues causa impacto en el negocio. | Solo averias. Incluye: brechas de seguridad, fugas de datos, caidas de servicio, errores de configuracion con consecuencias. |
| **Ataque** | Amenaza de terceros que **intencionadamente** buscan comprometer la seguridad. | Un error humano, una vulnerabilidad, una negligencia. Requiere INTENCIONALIDAD. |

> **Clave de examen -- Piramide conceptual:**
> Activo tiene → Vulnerabilidad (debilidad) → que es explotada por → Amenaza → generando un → Riesgo (probabilidad x dano) → que al materializarse se convierte en → Incidente. Si la amenaza es intencionada → Ataque.

### 2.2 Tipos de Riesgo

| Tipo | Caracteristicas | Ejemplo |
|---|---|---|
| **Riesgos conocidos** | Pueden identificarse, analizarse y gestionarse de forma proactiva. | Se sabe que el datacenter esta en zona sismica → se refuerza la estructura antisismica. |
| **Riesgos desconocidos** | Situaciones imprevistas que no permiten medidas a priori. Requieren estrategias de resiliencia general. | Un fallo en cascada por una combinacion nunca antes vista de errores de configuracion. |

### 2.3 Opciones para Tratar los Riesgos (4 estrategias)

| Estrategia | Descripcion | Ejemplo real |
|---|---|---|
| **Mitigar** | Reducir la probabilidad o el impacto a un nivel aceptable. | Instalar un firewall y antivirus corporativo para reducir el riesgo de malware. |
| **Asumir** | Aceptar el riesgo conscientemente cuando el coste de tratarlo supera el beneficio. | Una PYME asume el riesgo de no tener datacenter redundante porque el coste es inviable. |
| **Transferir** | Desplazar el impacto a un tercero (normalmente mediante seguro o externalizacion). | Contratar un seguro de ciberriesgos con cobertura de perdida de datos y responsabilidad civil. |
| **Eliminar** | Suprimir la causa del riesgo por completo (dejar de realizar la actividad que lo genera). | Cerrar un servicio web vulnerable que ya no es necesario para el negocio, eliminando el vector de ataque. |

> **Clave de examen:** Las 4 opciones son Mitigar, Asumir, Transferir y Eliminar. NO son 3 (sin Transferir), ni se limita a mitigar/asumir/eliminar.

### 2.4 Analisis de Riesgos -- En que consiste?

El analisis de riesgos consiste en **AMBAS** de las siguientes:

1. **Identificar los riesgos** a los que estan expuestos los activos del sistema de informacion.
2. **Identificar problemas de seguridad** que evidencian vulnerabilidades en los sistemas.

Es decir, combina la identificacion de activos y sus vulnerabilidades con la evaluacion de las amenazas y el impacto potencial.

**Ejemplo real (Sanidad):** Un hospital realiza analisis de riesgos sobre su sistema de historias clinicas electronicas:
- Activo: base de datos de pacientes (datos sensibles).
- Vulnerabilidad: sistema operativo del servidor sin parches de seguridad.
- Amenaza: atacante externo que explota la vulnerabilidad para exfiltrar datos.
- Impacto: sancion por RGPD (hasta 4% facturacion anual), dano reputacional irreversible.
- Riesgo calculado: Alta probabilidad x Impacto critico = Riesgo Alto → **Mitigar** aplicando parches y segmentando la red.

### 2.5 Gestion del Riesgo

> **Definicion:** Identificar y desplegar medidas tecnicas y organizativas para **evitar, minimizar o controlar** los riesgos, eliminando o reduciendo el dano.

- **NO** es unicamente eliminar los riesgos (opcion inviable en la mayoria de casos).
- **NO** es subcontratar la seguridad (eso seria una forma de transferir, no gestionar).
- **NO** es solo mitigar (la gestion incluye las 4 estrategias de tratamiento).

### 2.6 Formulas y Metricas del Analisis de Riesgos

#### Formula Expandida del Riesgo

> **R = Σ (Li x Pi)**
>
> Donde:
> - **Li** = impacto (dano) sobre el activo i
> - **Pi** = probabilidad de ocurrencia de la amenaza sobre el activo i
> - **R** = riesgo total, suma ponderada de todos los riesgos individuales

#### Fase I: Valoracion de Activos con Dependencias

En la primera fase se calcula el valor de cada activo considerando sus dependencias:

> **Valor acumulado (b) = valor(b) + valor(a) x dependencia**
>
> **Impacto acumulado (a) = impacto(a) + impacto(b) x dependencia**

Donde:
- Si el activo **a** depende del activo **b**, el valor de **b** se incrementa proporcionalmente al valor de **a** multiplicado por el grado de dependencia.
- De forma analoga, el impacto sobre **a** se propaga a **b** en funcion de la dependencia.

#### Fase II: Analisis de Vulnerabilidad en 2 Vertientes

Las vulnerabilidades se analizan desde dos perspectivas complementarias:

| Vertiente | Descripcion | Ejemplos |
|---|---|---|
| **Degradacion** | Porcentaje de afectacion: en que medida la vulnerabilidad reduce la capacidad del activo. | 0% (sin degradacion), 50% (parcial), 100% (inutilizacion total). |
| **Frecuencia** | Periodicidad con la que la vulnerabilidad puede manifestarse. | Diaria, semanal, mensual, anual, una vez, nunca. |

#### Fase III: Alineacion de Salvaguardas con Amenazas

En la tercera fase se seleccionan y valoran las salvaguardas adecuadas:

- **Repositorios de referencia para salvaguardas:**
  - **ISO 27002** (Codigo de Buenas Practicas para Controles de Seguridad)
  - **MAGERIT** (Catalogo de Elementos, Libro II)
  - **Anexos del ENS** (Esquema Nacional de Seguridad)
- **Valoracion:** Las salvaguardas se evaluan segun su **grado de eficacia (%)** frente a cada amenaza. Una salvaguarda puede cubrir total o parcialmente una amenaza.

---

## 3. Metodologias de Analisis de Riesgos

### 3.1 Cuadro Comparativo

| Metodologia | Origen | Ano | Fases/Estructura | Enfoque principal |
|---|---|---|---|---|
| **MAGERIT III** | Espana (CNI/CCN) | 1997 (V1) / 2012 (V3) | 3 libros (Metodo, Catalogo, Guias Tecnicas) | Administraciones Publicas espanolas. Analisis y **gestion** de riesgos. Obligatorio para cumplir el ENS. |
| **CRAMM** | Reino Unido | 1987 | 3 fases (Objetivos, Analisis de Riesgos, Salvaguardas) | Originalmente para gobierno UK. Adoptada por la OTAN y el Gobierno Holandes. |
| **EBIOS** | Francia (ANSSI) | 1995 | 5 fases | Sector publico frances. Eventos temidos y escenarios de riesgo. |
| **ISO/IEC 27005** | Internacional | 2008/2011 | Modelo PDCA (Plan-Do-Check-Act) generico | Estandar generico para gestion de riesgos en el marco de un SGSI (ISO 27001). |
| **UNE 71504** | Espana (AENOR) | 2008 | Metodologia de analisis y gestion de riesgos para SSII | Metodologia espanola de analisis y gestion de riesgos para Sistemas de Informacion. |

> **Clave de examen:** Las metodologias de analisis de riesgos **reconocidas** son: **CRAMM, EBIOS y MAGERIT II** (todas ellas). ITIL e ISO 27001 **NO** son metodologias de analisis de riesgos.

### 3.2 MAGERIT III (Detalle)

**Origen:** Desarrollada por el Consejo Superior de Administracion Electronica de Espana, mantenida por el CCN-CNI (Centro Criptologico Nacional). Es la metodologia de referencia para el cumplimiento del **Esquema Nacional de Seguridad (ENS)** en las Administraciones Publicas espanolas. La **primera version data de 1997**, siendo MAGERIT III (2012) la version actual.

**Estructura (3 libros):**

| Libro | Contenido |
|---|---|
| **Libro I: Metodo** | Descripcion detallada del metodo de analisis de riesgos: caracterizacion de activos, valoracion de dependencias, identificacion y valoracion de amenazas, evaluacion del impacto y el riesgo, identificacion de salvaguardas adecuadas. |
| **Libro II: Catalogo de Elementos** | Catalogo estructurado de activos, amenazas (con tasas de ocurrencia) y salvaguardas tipicos. Sirve de guia para el analista. |
| **Libro III: Guias Tecnicas** | Guias complementarias: como desarrollar las tareas del proyecto, como integrar MAGERIT con otras metodologias, modelos de madurez, etc. |

**Ejemplo real:** La Agencia Tributaria Espanola utilizo MAGERIT para analizar los riesgos de sus sistemas de informacion tributaria, identificando mas de 500 activos y aplicando salvaguardas como cifrado de datos en transito, doble factor de autenticacion para funcionarios, y segregacion de funciones en entornos virtualizados.

**Herramienta asociada:** PILAR (entorno de trabajo software del CCN para realizar analisis de riesgos siguiendo MAGERIT). PILAR = Plataforma Informatica para el Analisis y Gestion de Riesgos.

### 3.3 CRAMM (CCTA Risk Analysis and Management Method)

| Caracteristica | Detalle |
|---|---|
| Origen | Reino Unido, 1987 |
| 3 fases | **1. Objetivos** (Identificacion y valoracion de activos). **2. Analisis de Riesgos** (Identificacion de amenazas y vulnerabilidades). **3. Salvaguardas** (Seleccion de contramedidas). |
| Adopcion | Gobiernos, sector publico britanico. Adoptada por la **OTAN** para sistemas clasificados y por el **Gobierno Holandes**. |
| Fortaleza | Integra la valoracion cualitativa y cuantitativa con una base de datos de amenazas y contramedidas. |

### 3.4 EBIOS (Expression des Besoins et Identification des Objectifs de Securite)

| Caracteristica | Detalle |
|---|---|
| Origen | Francia, ANSSI (Agence Nationale de la Securite des Systemes d'Information) |
| 5 fases | **1. Analisis del Contexto** (Estudio del contexto). **2. Requisitos de Seguridad y Amenazas** (Estudio de eventos temidos). **3. Objetivos de Seguridad** (Elaboracion de escenarios de riesgo). **4.** Estudio de riesgos (gravedad y probabilidad). **5.** Estudio de medidas de tratamiento. |
| Enfoque | Orientado a "eventos temidos" y "escenarios de riesgo", muy grafico y participativo. |

### 3.5 ISO/IEC 27005 -- Gestion de Riesgos en la Seguridad de la Informacion

- Es un estandar **generico**, aplicable a organizaciones de cualquier tipo que ya tengan implantado (o planeen implantar) un SGSI segun ISO 27001.
- Sigue el modelo **PDCA** (Plan, Do, Check, Act).
- Proporciona directrices para la gestion del riesgo, pero no especifica un metodo concreto: puede adaptarse a MAGERIT, CRAMM, etc.

**Ejemplo real:** Una multinacional de retail certificada en ISO 27001 realiza su analisis de riesgos anual siguiendo ISO 27005 como marco, pero utilizando MAGERIT como metodo concreto para la identificacion y valoracion de activos.

---

## 4. Auditoria Informatica

### 4.1 Definicion

> Recoger, agrupar y evaluar **evidencias** para determinar si un Sistema de Informacion realiza de forma **eficaz** los fines de la organizacion y utiliza **eficientemente** los recursos.

Tambien cubre:
- La **integridad de los datos** (que la informacion no ha sido alterada de forma no autorizada).
- La **proteccion del activo empresarial** (salvaguarda de los recursos de informacion).

> **NO confundir** auditoria informatica con:
> - **Analisis de seguridad** (hacking etico, pentesting): eso es ofensivo/tecnico.
> - **Analisis de riesgos**: identificar amenazas y proponer salvaguardas → eso es analisis de riesgos, **NO** auditoria.
>
> **Importante:** No se debe confundir la auditoria con un **analisis de seguridad** (hacking etico, pruebas de penetracion). La auditoria evalua controles, recoge evidencias y verifica cumplimiento. El analisis de seguridad busca vulnerabilidades mediante tecnicas ofensivas. Son actividades complementarias pero distintas.

### 4.2 Objetivos de la Auditoria Informatica

- ✅ **Verificar disponibilidad** de los sistemas y servicios tecnologicos.
- ✅ **Verificar controles** de integridad, confidencialidad y autenticacion.
- ✅ **Verificar cumplimiento normativo** (LOPD/RGPD, ENS, ISO 27001, etc.).
- ✅ **Eliminar/minimizar** la probabilidad de perdida de informacion.
- ✅ **Verificar el control interno** de la funcion informatica (segregacion de funciones, gestion de accesos, etc.).
- ❌ **Identificar amenazas y proponer salvaguardas** → eso NO es auditoria, es analisis de riesgos.

> **Examen:** A la pregunta de cuales son los objetivos de la auditoria informatica, son correctas **AMBAS** opciones C y D (cuando aparecen combinadas verificaciones de disponibilidad/integridad y control interno/cumplimiento).

### 4.3 Tipos de Auditoria Informatica

| Tipo | Descripcion | Ejemplo real |
|---|---|---|
| **Auditoria de datos** | Revision de la calidad, integridad y proteccion de los datos. Clasificacion de la informacion segun criticidad. | Auditar la base de datos de RRHH para verificar que los datos de nomina solo sean accesibles por personal autorizado. |
| **Auditoria de comunicaciones** | Evaluacion de la seguridad y eficiencia de las redes y sistemas de comunicacion. | Verificar que las VPN de teletrabajo usan cifrado AES-256 y que los cortafuegos segmentan correctamente las subredes. |
| **Auditoria legal/LOPD/RGPD** | Verificar el cumplimiento de la normativa de proteccion de datos personales. | Revisar el registro de actividades de tratamiento, consentimientos de clientes, y contratos de encargados de tratamiento. |
| **Auditoria de seguridad** | Evaluacion de controles tecnicos y organizativos de seguridad de la informacion. | Revisar politicas de contrasenas, control de acceso fisico y logico, registros de auditoria (logs). |
| **Auditoria de sistemas** | Verificar la eficacia y eficiencia de los sistemas operativos y plataformas. | Auditar la configuracion de servidores Linux segun estandares CIS Benchmark. |
| **Auditoria de aplicaciones** | Evaluar el desarrollo, despliegue y mantenimiento del software. | Revisar la metodologia de desarrollo seguro (SDL), pruebas de seguridad en el pipeline CI/CD. |
| **Auditoria de ciberseguridad** | Evaluacion especifica de la postura de ciberseguridad: capacidad de prevenir, detectar y responder a ciberamenazas. | Analisis del nivel de madurez en ciberseguridad segun el modelo NIST CSF. |
| **Auditoria de sistemas SCADA** | Evaluacion de la seguridad en sistemas de control industrial y supervision. | Auditar la red OT de una planta de produccion, verificando segmentacion IT/OT. |
| **Auditoria de aseguramiento de la ciberresiliencia** | Verificar la capacidad de la organizacion para resistir, adaptarse y recuperarse de ciberincidentes. | Evaluar el cumplimiento de la Directiva NIS2 o del Marco de Ciberresiliencia. |

> **Examen:** A la pregunta "Que tipos de auditoria informatica existen?", la respuesta es **TODAS son correctas** cuando aparecen como opciones: de datos, de comunicaciones, legal de la LOPD/RGPD, de seguridad, de ciberseguridad, de sistemas SCADA, de aseguramiento de la ciberresiliencia, etc.

### 4.4 Formas de Desarrollar una Auditoria

| Enfoque | Descripcion | Tecnicas |
|---|---|---|
| **Alrededor del ordenador** | Revision del entorno que rodea al sistema sin acceder directamente a los programas ni datos. | Entrevistas, revision documental, inspeccion fisica, analisis de procedimientos y organigramas. |
| **A traves del ordenador** | Se analizan los procesos automatizados internos del sistema, los programas y los datos. | Trazas de ejecucion, revision de codigo, pruebas logicas de controles internos, analisis de logs. |
| **Con el ordenador** | Se utilizan herramientas informaticas auxiliares para realizar pruebas y simulaciones sobre el sistema auditado. | Software de auditoria generalizado (ACL, IDEA), herramientas CAAT (Computer-Assisted Audit Techniques), scripts de verificacion masiva. |

### 4.5 Referencia Tecnica: CCN-STIC 802

La guia **CCN-STIC 802** del Centro Criptologico Nacional es la guia de **Auditoria del Esquema Nacional de Seguridad (ENS)**. Establece:

- El procedimiento de auditoria para verificar el cumplimiento del ENS.
- Los criterios de evaluacion.
- Las evidencias que deben recogerse.
- Los requisitos del equipo auditor.

### 4.6 Dictamen Final de Auditoria

| Dictamen | Significado |
|---|---|
| **Conforme** | El sistema auditado cumple sustancialmente los requisitos y controles esperados. Sin deficiencias significativas. |
| **Conforme con deficiencias** | Se han encontrado deficiencias que no invalidan globalmente el sistema, pero requieren acciones correctivas. |
| **No conforme** | Se han detectado incumplimientos graves que comprometen significativamente los objetivos del sistema. |

**Ejemplo real:** Una auditoria del ENS sobre la plataforma de licitacion electronica del Estado arroja "Conforme con deficiencias" porque, aunque los controles de acceso son correctos, el registro de auditoria (logging) no retiene los logs durante el periodo minimo exigido de 1 ano.

### 4.7 Resultados de una Auditoria

El resultado principal de una auditoria es:

> **Evidencias de los riesgos** asociados a los sistemas que soportan la informacion, y en su caso, la identificacion de salvaguardas insuficientes o ausentes.

> **Trampa de examen:** No es "propuesta de salvaguardas" (eso es analisis de riesgos). Es "evidencias" de la situacion real, tanto de los riesgos detectados como de los controles existentes.

### 4.8 Alcance de la Auditoria

El alcance define los limites de la auditoria y se estructura en dos niveles:

#### Alcance General

| Elemento | Descripcion |
|---|---|
| **Descripcion de sedes** | Ubicaciones fisicas que seran auditadas (oficinas, datacenters, delegaciones). |
| **Estructura organica** | Departamentos, areas y unidades organizativas incluidas en el alcance. |
| **Actividades y procesos** | Que procesos de negocio y actividades operativas se auditan. |
| **Periodo de tiempo** | Marco temporal que cubre la auditoria (ej: ejercicio fiscal, ultimo trimestre). |

#### Alcance Especifico

| Elemento | Descripcion |
|---|---|
| **Sistemas afectados** | Sistemas de informacion, aplicaciones y plataformas concretas objeto de la auditoria. |
| **Activos de infraestructura tecnologica** | Servidores, redes, dispositivos de seguridad, equipos de comunicaciones. |
| **Personal vinculado** | Roles y personas responsables de los sistemas y procesos auditados. |

### 4.9 Planificacion de la Auditoria

La planificacion es la fase preparatoria fundamental que incluye:

| Elemento | Descripcion |
|---|---|
| **Plan de auditoria** | Documento rector que define objetivos, alcance, metodologia y recursos. |
| **Calendario de revisiones/reuniones/entrevistas** | Programacion temporal de todas las actividades de campo. |
| **Asignacion de tareas** | Distribucion de responsabilidades entre los miembros del equipo auditor. |
| **Concrecion de criterios** | Definicion precisa de los criterios de evaluacion y los umbrales de conformidad. |

---

## 5. Plan Director de Seguridad

### 5.1 Definicion

> Define la **estrategia en seguridad TIC** de la organizacion durante un periodo determinado (generalmente 2-4 anos), estableciendo objetivos, acciones, recursos y plazos.

- **NO** es solamente seguridad fisica y logica.
- **NO** es la estrategia de negocio general.
- **ES** el documento rector que marca el rumbo de la seguridad de la informacion en la organizacion a medio-largo plazo.

> **Problemas que evita el Plan Director:** Sin un Plan Director, las organizaciones sufren **iniciativas dispares** (cada departamento implementa su propia seguridad sin coordinacion), **sistemas heterogeneos** (soluciones incompatibles entre si) y **diferentes requisitos en una misma organizacion** (niveles de seguridad inconsistentes que generan brechas). El Plan Director unifica criterios y alinea todas las iniciativas bajo una estrategia comun.

### 5.2 Objetivos del Plan Director de Seguridad

| Objetivo | Descripcion |
|---|---|
| **Definir objetivos y criterios basicos** en seguridad de la informacion | Establecer el "norte" de la seguridad: que nivel se quiere alcanzar. |
| **Establecer el marco normativo y cumplimiento legal** | Asegurar que se cumplen RGPD, LSSI, ENS, LOPD, normativa sectorial (banca, sanidad, etc.). |
| **Conocer y planificar costes e inversiones** | Dimensionar el presupuesto necesario para alcanzar los niveles de seguridad deseados. |
| **Aportar confianza** sobre los servicios ofrecidos | Generar seguridad en clientes, proveedores y terceros sobre la fiabilidad de los servicios. |

- ❌ **NO** es objetivo especifico "realizar analisis de riesgos" (eso es un medio, no un fin).
- ❌ **NO** es objetivo "cumplir la LSSIE" (Ley de Servicios de la Sociedad de la Informacion -- la seguridad no solo se limita a esa ley).

### 5.3 Factores Clave de Exito

| # | Factor | Importancia |
|---|---|---|
| 1 | **Compromiso de la Direccion** | ⭐ **El mas importante.** Sin apoyo explicito y sostenido de la alta direccion, el Plan Director esta abocado al fracaso. |
| 2 | **Designar un responsable del Plan** | Una persona o comite con autoridad y responsabilidad clara para liderar el Plan. |
| 3 | **Marco metodologico definido** | Usar una metodologia reconocida (ISO 27001, MAGERIT, etc.) para estructurar el analisis y las acciones. |
| 4 | **Recursos y medios adecuados** | Presupuesto, personal, herramientas y tiempo suficientes. |
| 5 | **Seguimiento permanente** | Indicadores de cumplimiento (KPI), revisiones periodicas, cuadros de mando. |

### 5.4 Norma Basica de Referencia

La **ISO/IEC 27002** (Codigo de Buenas Practicas para los Controles de Seguridad de la Informacion) sirve como catalogo de controles de referencia sobre los que se estructura el Plan Director de Seguridad.

> Relacion clave: ISO 27001 define los requisitos del SGSI, ISO 27002 proporciona el catalogo de controles que se implementan en el Plan Director.

### 5.5 Resultados del Plan Director

| Resultado | Descripcion |
|---|---|
| **Nivel de seguridad actual** | Diagnostico de la situacion de partida (AS-IS). |
| **Nivel de seguridad deseado** | Objetivo a alcanzar (TO-BE). |
| **Necesidades identificadas** | Brechas entre la situacion actual y la deseada (GAP analysis). |
| **Hoja de ruta** | Secuencia temporal de proyectos y acciones priorizadas. |
| **Estudio economico** | Presupuesto estimado con coste de inversion y coste operativo recurrente. |

**Ejemplo real:** Una universidad publica espanola desarrolla su Plan Director de Seguridad 2024-2027:
- Situacion actual: 40 servicios web sin certificado SSL, 300 cuentas de usuario sin politica de contrasenas robusta.
- Situacion deseada: todos los servicios con HTTPS y autenticacion federada (eduGAIN/SIR), acceso multifactor para servicios criticos.
- Hoja de ruta: Ano 1 → implantar MFA y reforzar politicas de contrasenas. Ano 2 → migrar sistemas legacy. Ano 3 → certificacion ENS categoria media.
- Presupuesto: 1.2M€ distribuidos en 3 anos.

### 5.6 Dominios que Cubre el Plan Director

El Plan Director de Seguridad debe abarcar **TODOS los dominios** de la seguridad de la informacion en la organizacion:

| Dominio | Descripcion |
|---|---|
| **Redes** | Segmentacion, cortafuegos, VPN, monitorizacion de trafico, control de acceso a red (NAC). |
| **Equipos** | Endpoints (PCs, portatiles, moviles), servidores, configuracion segura, hardening. |
| **Seguridad fisica y logica** | Proteccion perimetral, control de accesos fisicos, cifrado, autenticacion, PKI. |
| **Controles de acceso** | Gestion de identidades (IAM), privilegios minimos, segregacion de funciones, MFA. |
| **Mantenimiento** | Gestion de parches, actualizaciones, fin de vida de sistemas, planes de renovacion tecnologica. |
| **Normativa** | Cumplimiento legal y regulatorio: ENS, RGPD, LOPD, LSSI, normativa sectorial. |
| **Politica de seguridad** | Documento de alto nivel con principios, roles y responsabilidades en materia de seguridad. |
| **Seguridad del personal** | Concienciacion, formacion, acuerdos de confidencialidad, verificacion de antecedentes. |
| **Continuidad del negocio** | Planes de continuidad, DRP, BIA, analisis de impacto, sitios alternativos. |
| **Control de inventario** | Registro y gestion de activos de informacion, hardware, software y licencias. |

> La norma basica de referencia para estos controles es la **ISO 27002**, que proporciona el catalogo estructurado de controles de seguridad.

---

## 6. Plan de Respuesta ante Incidentes

### 6.1 Definicion

> Documento que detalla una relacion de **tareas y actividades** para dar respuesta a cualquier incidente **generico** que afecte a la **seguridad de la informacion**.

- **NO** es un plan para "cualquier incidente de la organizacion" (demasiado amplio: solo cubre incidentes de seguridad de la informacion).
- **NO** es solo documentar la seguridad de la organizacion.
- **NO** es simplemente cumplir con un requisito legal (aunque tambien ayude a ello).

### 6.2 Elementos del Plan de Respuesta ante Incidentes

| Elemento | Descripcion | Ejemplo real |
|---|---|---|
| **CSIRT** (Computer Security Incident Response Team) | Equipo de respuesta, roles definidos (coordinador, analistas, responsables de comunicacion). Contactos 24x7. | El CSIRT del INCIBE en Espana coordina la respuesta a ciberincidentes en ciudadania y empresas. |
| **Procedimientos documentados** | Pasos detallados para cada tipo de incidente grave: ransomware, fuga de datos, DDoS, intrusion. | Playbook de respuesta a ransomware: aislar segmento de red afectado, identificar variante, evaluar backups, notificar a AEPD si hay datos personales. |
| **Deteccion y analisis** | Metodos y herramientas para detectar incidentes (SIEM, IDS/IPS, antivirus EDR, alertas de usuarios). | Un SIEM (Splunk, ELK, Elastic) correlaciona eventos: multiples intentos fallidos de login desde IP extranjera + escaneo de puertos → alerta de intrusion. |
| **Contencion** | Acciones para limitar el dano y evitar la propagacion. | Desconectar de la red un servidor comprometido, bloquear una IP atacante en el firewall perimetral. |
| **Erradicacion** | Eliminar la causa raiz del incidente. | Eliminar malware, cerrar puertas traseras, parchear la vulnerabilidad explotada. |
| **Recuperacion** | Restaurar los sistemas y servicios a su estado operativo normal. | Restaurar desde backup, validar integridad de datos, re-conectar servicios progresivamente. |
| **Comunicacion** | A quien informar, cuando y como: direccion, usuarios, afectados, autoridad de control (AEPD), fuerzas de seguridad si procede. | Protocolo de notificacion: < 72 h desde deteccion para incidentes con datos personales (RGPD), comunicado publico si hay impacto masivo. |
| **Valoracion y lecciones aprendidas** | Analisis post-mortem del incidente: que fallo, que funciono, como evitar que se repita. | Reunion post-incidente: el ataque fue por spear-phishing → mejorar formacion de empleados en concienciacion. |
| **Revision y mejora** | Actualizar el plan de respuesta tras cada incidente real o simulacro. | Incorporar nuevas IoCs (Indicators of Compromise) al SIEM, anadir reglas de deteccion. |

### 6.3 Ciclo de Respuesta a Incidentes (NIST SP 800-61)

```
Preparacion → Deteccion y Analisis → Contencion, Erradicacion y Recuperacion → Actividad Post-Incidente
     ↑                                                                                      |
     └──────────────────────────────────────────────────────────────────────────────────────┘
                                         (retroalimentacion continua)
```

**Ejemplo real (Ransomware en el SEPE, 2021):**
- El Servicio Publico de Empleo Estatal sufrio un ataque de ransomware.
- **Deteccion:** Se detecto la manana del 9 de marzo al no poder acceder a sistemas internos.
- **Contencion:** Se aislaron los equipos afectados y se corto el acceso desde Internet.
- **Erradicacion:** Colaboracion con el CCN-CERT para analizar el malware y eliminarlo.
- **Recuperacion:** Restauracion progresiva de servicios (la web del SEPE funcionaba, pero la intranet tardo varios dias en restaurarse).
- **Comunicacion:** Nota de prensa oficial del Ministerio. Notificacion al CCN-CERT.
- **Lecciones:** Se reforzo la segmentacion de red y se implanto EDR en todos los endpoints.

---

## 7. Plan de Continuidad del Negocio (PCN / SGCN)

### 7.1 Definicion

El Plan de Continuidad del Negocio (PCN) o Sistema de Gestion de la Continuidad del Negocio (SGCN) es el conjunto de estrategias, planes y procedimientos que permiten a una organizacion **seguir funcionando** en caso de una interrupcion grave, minimizando el impacto sobre sus actividades criticas.

### 7.2 Metricas Clave: RTO, MTD, RPO y ROL

| Metrica | Significado | Definicion | Ejemplo |
|---|---|---|---|
| **RPO** (Recovery Point Objective) | Objetivo de Punto de Recuperacion | Cantidad maxima de datos que la organizacion se puede permitir perder, medida en tiempo. Define la frecuencia de los backups. | RPO = 1 hora → Los backups deben realizarse cada hora. En caso de desastre, se pierden como maximo 60 minutos de datos. Un banco con RPO de 15 minutos usa replicacion sincrona de bases de datos. |
| **RTO** (Recovery Time Objective) | Objetivo de Tiempo de Recuperacion | Tiempo maximo tolerable para restaurar el servicio tras una interrupcion. Define cuanto puede estar caido un sistema. | RTO = 4 horas → Si el ERP corporativo cae a las 10:00, debe estar operativo antes de las 14:00. Un hospital con RTO de 5 minutos para el sistema de urgencias necesita un datacenter en caliente (hot site). |
| **MTD** (Maximum Tolerable Downtime) | Tiempo Maximo de Inactividad Tolerable | Limite absoluto de tiempo que un proceso/servicio puede estar inactivo antes de que las consecuencias sean catastroficas para la organizacion. | MTD = 24 horas para la pasarela de pagos de un e-commerce: tras 24 horas sin poder cobrar, las perdidas son irrecuperables y puede haber quiebra. |
| **ROL** (Recovery Objective Level) | Niveles Minimos de Recuperacion de Servicio | Define el nivel minimo de servicio que debe alcanzarse tras la recuperacion. No basta con restaurar el sistema: hay que garantizar que funciona a un nivel minimo aceptable. | ROL = 60% de la capacidad de atencion a clientes durante las primeras 4 horas post-recuperacion. Una vez estabilizado, escalar al 100% en 24 horas. El ROL asegura que no solo se recupera el sistema, sino que este ofrece un servicio minimo viable. |

> **Relacion entre metricas:** RTO <= MTD (el objetivo de recuperacion debe ser menor o igual que el tiempo maximo tolerable). RPO determina la estrategia de backup (a menor RPO, mas costosa la solucion). ROL define el nivel minimo operativo tras la recuperacion.

```
       RPO                          RTO                        MTD
←───|───|───────────────────────────|──────────────────────────|────→ tiempo
    ↑                               ↑                          ↑
 Ultimo backup                  Recuperacion                Colapso del negocio
 (perdida maxima               del servicio                 si no se recupera
  de datos aceptable)
```

### 7.3 Objetivos Generales del Plan de Continuidad

| Objetivo | Descripcion |
|---|---|
| **Evitar perdidas** | Prevenir o minimizar las perdidas economicas, de informacion y de activos derivadas de una interrupcion. |
| **Mantener la confianza** | Preservar la reputacion y la confianza de clientes, proveedores, accionistas y partes interesadas. |
| **Garantizar la comunicacion** | Asegurar canales de comunicacion efectivos durante y despues de la crisis (internos y externos). |
| **Proteger el medio ambiente** | Evitar o minimizar el impacto ambiental que pudiera derivarse de un incidente (fugas, vertidos, danos colaterales). |

### 7.4 Norma de Referencia: ISO 22301 y Documentos INCIBE

La **ISO 22301** es el estandar internacional que especifica los requisitos para un Sistema de Gestion de la Continuidad del Negocio (SGCN):

- Es certificable (una organizacion puede obtener certificacion ISO 22301).
- Alineada con ISO 27001 (SGSI), ISO 9001 (Calidad) e ISO 14001 (Medio Ambiente) mediante la estructura de alto nivel (HLS - High Level Structure).
- Fomenta el ciclo PDCA de mejora continua.

Ademas de la ISO 22301, en Espana se cuenta con los **documentos y guias del INCIBE** (Instituto Nacional de Ciberseguridad) como referencia complementaria para la elaboracion e implantacion de planes de continuidad del negocio, especialmente orientados a pymes y administraciones publicas.

**Ejemplo real:** Eurocontrol (gestion del trafico aereo europeo) esta certificado en ISO 22301: sus centros de control tienen redundancia completa (dos centros que pueden asumir el trafico del otro en minutos), con un RTO de menos de 5 minutos para sistemas de control aereo.

### 7.5 Fases del PCN

| Fase | Descripcion | Actividades Clave |
|---|---|---|
| **1. Alcance y Contexto** | Definir que partes de la organizacion cubre el PCN y en que contexto opera. | Identificar productos/servicios criticos, partes interesadas, requisitos legales y regulatorios. Analisis del contexto externo e interno. |
| **2. Analisis / BIA** (Business Impact Analysis) | Evaluar el impacto de una interrupcion en cada proceso de negocio y determinar los requisitos de continuidad. | Identificar procesos criticos, calcular RTO, MTD y RPO para cada proceso, priorizar la recuperacion segun impacto en el negocio. |
| **3. Estrategia** | Definir las estrategias de continuidad adecuadas para cada proceso critico. | Seleccionar alternativas de recuperacion: sitio alternativo (hot site, warm site, cold site), teletrabajo, proveedores alternativos, redundancia de sistemas. |
| **4. Respuesta / Planes** | Desarrollar los planes de continuidad detallados, incluyendo recursos, equipos y protocolos. | Elaborar plan de respuesta ante emergencias, plan de recuperacion de TI (DRP - Disaster Recovery Plan), plan de continuidad de procesos de negocio. |
| **5. Pruebas y Mantenimiento** | Verificar que los planes funcionan y mantenerlos actualizados. | Simulacros periodicos (al menos 1 al ano), pruebas de restauracion de backups, revision y actualizacion tras cambios organizativos o tecnologicos. |

### 7.6 Tipos de Sitios Alternativos (DRP)

| Tipo | Caracteristicas | Coste | RTO tipico |
|---|---|---|---|
| **Cold site** | Espacio fisico vacio con electricidad y climatizacion, sin equipamiento. Requiere instalar todo. | Bajo | Dias / Semanas |
| **Warm site** | Espacio con hardware y conectividad basica, pero sin datos sincronizados. Requiere restauracion de backups. | Medio | Horas / Dias |
| **Hot site** | Replica completa del entorno de produccion, con datos sincronizados en tiempo real. Funciona en minutos. | Alto | Minutos / Horas |

**Ejemplo real:** Un servicio cloud como AWS o Azure ofrece Disaster Recovery as a Service (DRaaS) con RTO de minutos y RPO cercano a cero mediante replicacion entre regiones.

---

## Resumen para el Examen

### Conceptos "Filtro" (preguntas trampa detectadas)

| Pregunta tipica | Respuesta correcta |
|---|---|
| ITIL es... | Una **biblioteca de buenas practicas** en gestion de servicios TI |
| ITIL es una norma europea de obligado cumplimiento | ❌ **NO** |
| ITIL es una norma ISO 27000 | ❌ **NO** |
| ITIL es una metodologia de trabajo | ❌ **NO** (es recopilacion de buenas practicas en gestion de SERVICIOS) |
| ITIL es el estandar "de facto" en provision de servicios TI | ✅ **SI** |
| Biblioteca original ITIL: 50 libros → 7 (V2) → 5 (V3) | ✅ **SI** |
| Objetivo ITIL V2 | **Alinear** la tecnologia con el Negocio |
| Objetivo ITIL V3 | **Integrar** la tecnologia en el Negocio |
| Ciclo de Vida del Servicio ITIL V3 | Estrategia → Diseno → Transicion → Operacion → Mejora Continua (5 etapas) |
| Cada fase ITIL V3 tiene Actividades y Procesos | ✅ **SI** |
| ITIL V4 sustituye "procesos" por "practicas" | ✅ **SI** |
| ITIL V4 se integra con Agile, DevOps, Lean, Gobierno TI | ✅ **SI** |
| Valor = funcionalidad + garantia | ✅ **SI** |
| Ciclo de Vida = PDCA (Plan, Do, Check, Act) | ❌ **NO** (eso es Deming) |
| Incluye "Publicacion" o "Difusion" en el ciclo? | ❌ **NO** |
| Que es un Activo? | Recurso software, hardware, personal, administrativo o funcional |
| Activo = solo hardware | ❌ **NO** |
| Vulnerabilidad es... | Una **debilidad** del sistema |
| Vulnerabilidad = amenaza | ❌ **NO** |
| Riesgo = Dano x Probabilidad | ✅ **SI**. Formula expandida: R = Σ (Li x Pi) |
| Ataque se caracteriza por... | **Intencionalidad** de terceros |
| Opciones para tratar riesgos (4) | **Mitigar, Asumir, Transferir, Eliminar** |
| Analisis de riesgos consiste en... | Identificar riesgos + identificar vulnerabilidades (**AMBAS**) |
| Fase I: Valor acumulado con dependencias | ✅ **SI** |
| Fase II: Vulnerabilidad = Degradacion + Frecuencia | ✅ **SI** |
| Fase III: Salvaguardas alineadas con amenazas (ISO 27002, MAGERIT, ENS) | ✅ **SI** |
| Gestion del riesgo = solo eliminar | ❌ **NO** (es evitar, minimizar o controlar) |
| Metodologias reconocidas de analisis de riesgos | **CRAMM, EBIOS y MAGERIT II** (todas) |
| CRAMM: 3 fases (Objetivos, Analisis de Riesgos, Salvaguardas). OTAN + Gob. Holandes | ✅ **SI** |
| EBIOS: 5 fases (Analisis del Contexto, Requisitos de Seguridad y Amenazas, Objetivos de Seguridad...) | ✅ **SI** |
| MAGERIT: primera version 1997, 3 libros | ✅ **SI** |
| UNE 71504: Metodologia de analisis y gestion de riesgos para SSII | ✅ **SI** |
| ITIL es metodologia de analisis de riesgos | ❌ **NO** |
| ISO 27001 es metodologia de analisis de riesgos | ❌ **NO** |
| MAGERIT III -- libros | 3 libros: Metodo, Catalogo, Guias Tecnicas |
| MAGERIT III -- origen | Espanola, CNI/CCN, enfocada a AA.PP. Primera version de 1997. |
| MAGERIT es metodologia de... | Analisis y **gestion** de riesgos |
| Auditoria = identificar amenazas y proponer salvaguardas | ❌ **NO** (eso es analisis de riesgos) |
| Auditoria NO es analisis de seguridad (hacking etico, pentesting) | ✅ **SI**. Son actividades complementarias pero distintas. |
| Tipos de auditoria | De datos, comunicaciones, legal LOPD/RGPD, seguridad, ciberseguridad, SCADA, ciberresiliencia → **TODAS** |
| Formas de auditoria | Alrededor, a traves, y con el ordenador |
| Alcance general: sedes, estructura organica, actividades, periodo | ✅ **SI** |
| Alcance especifico: sistemas, activos tecnologicos, personal | ✅ **SI** |
| Planificacion: plan de auditoria, calendario, asignar tareas, concretar criterios | ✅ **SI** |
| Guia de auditoria del ENS | **CCN-STIC 802** |
| Dictamenes de auditoria | Conforme, Conforme con deficiencias, No conforme |
| Plan Director de Seguridad define... | Estrategia en seguridad TIC de la organizacion |
| Problemas que evita el Plan Director: iniciativas dispares, sistemas heterogeneos, diferentes requisitos | ✅ **SI** |
| Dominios que cubre: redes, equipos, seguridad fisica/logica, controles de acceso, mantenimiento, normativa, politica de seguridad, seguridad del personal, continuidad del negocio, control de inventario | ✅ **SI** |
| Factor clave de exito principal del Plan Director | **Compromiso de la Direccion** |
| Norma basica del Plan Director | **ISO 27002** |
| Plan de Respuesta ante Incidentes cubre... | Incidentes genericos de **seguridad de la informacion** |
| PCN -- Objetivos generales: evitar perdidas, mantener confianza, garantizar comunicacion, proteger medio ambiente | ✅ **SI** |
| PCN -- ISO de referencia | **ISO 22301** |
| PCN -- Documentos complementarios en Espana | **INCIBE** |
| RPO → | Punto de Recuperacion (perdida maxima de datos) |
| RTO → | Tiempo de Recuperacion (tiempo maximo para restaurar) |
| MTD → | Tiempo Maximo de Inactividad Tolerable |
| ROL → | Niveles Minimos de Recuperacion de Servicio |

### Jerarquia de Normas y Marcos

```
ITIL → Buenas practicas de gestion de servicios TI (estandar "de facto")
ISO 27001 → Requisitos del SGSI (Sistema de Gestion de Seguridad de la Informacion)
ISO 27002 → Catalogo de controles (Plan Director de Seguridad)
ISO 27005 → Directrices de gestion de riesgos (modelo PDCA)
ISO 22301 → Sistema de Gestion de Continuidad del Negocio
MAGERIT III → Metodologia de analisis y gestion de riesgos (Espana, AA.PP., V1 en 1997)
CRAMM → Metodologia de analisis y gestion de riesgos (UK, OTAN, Gob. Holandes)
EBIOS → Metodologia de analisis y gestion de riesgos (Francia, ANSSI)
UNE 71504 → Metodologia de analisis y gestion de riesgos para SSII (Espana, AENOR)
ENS → Esquema Nacional de Seguridad (Espana, ambito legal-administrativo)
CCN-STIC 802 → Guia de Auditoria del ENS
INCIBE → Documentos y guias de continuidad del negocio (Espana)
```

### Truco Mnemotecnico para las 5 Etapas de ITIL V3

**"E D T O M"** → **E**strategia, **D**iseno, **T**ransicion, **O**peracion, **M**ejora Continua

**Frase:** *"El Director Tecnico Opera Mejoras"*

---

*Documento elaborado como material de referencia para la UA 5: Instrumentos para la Gestion de la Seguridad.*
