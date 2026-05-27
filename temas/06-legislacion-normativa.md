# UA 6 - Legislacion y Normativa en Seguridad de la Informacion

> **Navegacion:**
> - [← README](../README.md)
> - [← Tema 5](05-gestion-seguridad.md)
> - [GLOSARIO](../GLOSARIO.md)
> - [Chuleta numerica](08-cheat-sheet-numeros.md)

---

## 1. Proteccion de Datos Personales

### 1.1 Evolucion legislativa

| Norma | Anio | Descripcion clave |
|---|---|---|
| **LORTAD** | 1992 | Supuso la primera ley espaniola (y en el ambito MUNDIAL) que regulaba especificamente los datos de caracter personal. Sustituida por la LOPD. |
| **LOPD** (LO 15/1999) | 1999 | Asume las funciones de LORTAD. Regula el tratamiento de datos y ficheros, **en cualquier soporte** (digital y papel). |
| **RD 1720/2007** | 2007 | Reglamento de desarrollo de la LOPD. |
| **RGPD** (UE 2016/679) | 2016 | Reglamento europeo de aplicacion directa. Novedades: (1) Delegado de Proteccion de Datos (DPD), (2) enfoque en tratamiento, (3) comunicacion de incidentes en **72 h**, (4) sanciones de hasta **20 M€ o 4 % de facturacion**, (5) incorpora la obligacion a TODAS las organizaciones de analizar las vulnerabilidades informaticas y posibles brechas de seguridad logica para seleccionar e implementar soluciones tecnologicas optimas. |
| **LOPDyGDD** (LO 3/2018) | 2018 | Adapta el RGPD a Espana. **Sustituye a la LOPD**. |

> **Pregunta tipica de examen:** ¿Que ley asumio las funciones de la LORTAD?
> **Respuesta: LOPD** (Ley Organica 15/1999).

> **Pregunta tipica:** ¿La LOPD afecta solo a ficheros digitales?
> **Respuesta: NO.** Afecta a ficheros **automatizados (digitales) Y no automatizados (papel)**.

> **Pregunta tipica:** ¿Cual es la principal normativa de proteccion de datos?
> **Respuesta: LOPD** (no la Ley de Firma Electronica, ni la LGT, ni la LSSI-CE).

### 1.2 Ejemplo real
Un hospital conserva historiales clinicos tanto en su sistema informatico como en archivadores fisicos. La LOPD (y hoy la LOPDyGDD) obliga a proteger **ambos** soportes: cifrado en base de datos y armario cerrado con llave para el papel.

### 1.3 Evaluacion de Impacto (EIPD / DPIA)

El RGPD establece la obligacion de efectuar una **Evaluacion de Impacto relativa a la Proteccion de Datos (EIPD/DPIA)** cuando el tratamiento de datos personales, por su naturaleza, alcance, contexto o fines, entrañe un alto riesgo para los derechos y libertades de las personas fisicas. Esta evaluacion debe realizarse de forma **previa** al inicio del tratamiento y debe incluir:

- Una descripcion sistematica del tratamiento previsto
- Evaluacion de la necesidad y proporcionalidad del tratamiento
- Evaluacion de los riesgos para los derechos y libertades
- Medidas previstas para mitigar dichos riesgos

---

## 2. Esquema Nacional de Seguridad (ENS)

### 2.1 Regulacion

- **Real Decreto 3/2010**, de 8 de enero (modificado por RD 951/2015).
- **NO** esta regulado por la Constitucion, ni por la LGT, ni por la LOPD.

### 2.2 ¿Que establece el ENS?

Establece las **condiciones de seguridad requeridas en el uso de medios electronicos en el ambito de la ADMINISTRACION PUBLICA**.

- **NO** es un reglamento de la LOPD.
- **NO** son normas para empresas publicas genericas.
- **NO** aplica directamente a organizaciones privadas (salvo que presten servicios a la AGE).

### 2.3 Objetivos principales

1. Establecer la politica de seguridad en el uso de medios electronicos (derivada de la Ley 11/2007 -- LAECSP).
2. Crear un marco comun para las AAPP en materia de seguridad TIC.
3. Aportar confianza a los ciudadanos en sus derechos y deberes con las AAPP por medios telematicos.
4. Establecer un lenguaje homogeneo que facilite la interaccion entre administraciones y su comunicacion a la industria y empresas.

> **Pregunta tipica:** ¿Cuales son los objetivos del ENS?
> **Respuesta: TODAS LAS RESPUESTAS SON CORRECTAS** (las cuatro anteriores).

### 2.4 Ambito de aplicacion -- Obligado cumplimiento

- Administracion General del Estado (AGE)
- Administraciones de las Comunidades Autonomas
- Entidades de Derecho publico vinculadas a las AAPP
- Entidades de Administracion Local

> **Pregunta tipica:** ¿A quien obliga el ENS?
> **Respuesta: TODAS LAS RESPUESTAS SON CORRECTAS** (todos los entes anteriores).

**Excluidos:** sistemas que traten **informacion clasificada**.

### 2.5 Categorizacion de sistemas

| Categoria | Criterio |
|---|---|
| **Basica** | Menor impacto |
| **Media** | Impacto moderado |
| **Alta** | Mayor impacto |

Se determina por cada **dimension de seguridad** (confidencialidad, integridad, disponibilidad, autenticidad, trazabilidad).

### 2.6 Conformidad con el ENS

| Categoria | Nivel de verificacion | Metodo de verificacion | Periodicidad | Acreditacion |
|---|---|---|---|---|
| **Basica** | Informal | **Autoevaluacion** | Cada 2 anios | Voluntaria |
| **Media** | Semiformal | **Auditoria externa** (entidad acreditada ENAC) | Cada 2 anios | Obligatoria |
| **Alta** | Formal | **Auditoria externa** (entidad acreditada ENAC) | Cada 2 anios | Obligatoria |

> **Pregunta tipica:** ¿Como se verifica la conformidad de un sistema de categoria Basica?
> **Respuesta: Autoevaluacion cada 2 anios. Nivel informal, acreditacion voluntaria.**

> **Pregunta tipica:** ¿Quien audita los sistemas de categoria Media y Alta?
> **Respuesta: Entidad acreditada por ENAC.**

### 2.7 Elementos principales del ENS

- Principios basicos
- Requisitos minimos
- Medidas de seguridad proporcionadas
- Auditoria de seguridad
- Respuesta a incidentes
- Certificacion

### 2.8 Ejemplo real
Un ayuntamiento que ofrece sede electronica a sus ciudadanos (consulta de expedientes, pago de tasas) debe categorizar su plataforma (normalmente **Media**) y someterse a auditoria obligatoria cada 2 anios mediante una entidad acreditada por ENAC.

---

## Comparativa ISO 27000 vs ENS

| Aspecto | Gestion ISO/IEC 27000 | Gestion en base al ENS |
|---------|----------------------|------------------------|
| Objetivo | Establecimiento de un SGSI | Regular principios basicos y definir requisitos minimos. Solo obliga a SGSI en Cat. Alta |
| Alcance | Definido por la propia organizacion | Medios electronicos de la Administracion para relacionarse con ciudadanos |
| Enfoque | Recursos de forma general, sin limitarse a SSII | Sistema de informacion como conjunto organizado de recursos |
| Medidas | No obliga a medidas concretas, sino a satisfacer controles | Obliga a implantar medidas determinadas segun categoria del sistema |
| Auditoria | Obliga a auditorias periodicas | Auditoria cada 2 anios en Cat. Media y Alta (autoevaluacion en Basica) |

---

## 3. Ciberseguridad

### 3.1 LSSI-CE (Ley 34/2002)

Ley de Servicios de la Sociedad de la Informacion y Comercio Electronico. Regula servicios online, comercio electronico, cookies, comunicaciones comerciales, etc.

Aspectos destacables:
- Obligaciones de prestadores de servicios con beneficio economico
- Regula comunicaciones comerciales por medios electronicos
- Regimen sancionador
- Accesibilidad en webs de AAPP
- Asignacion de nombres de dominio bajo .es

> **Cuidado en el examen:** La LSSI-CE **NO** asumio las funciones de la LORTAD. Esa fue la LOPD.

### 3.2 Directiva NIS (UE 2016/1148)

Medidas para garantizar un **elevado nivel comun de seguridad de redes y sistemas de informacion** en la UE. Primera directiva europea de ciberseguridad.

**4 objetivos principales:**
- Gestionar el riesgo
- Proteger contra ciberataques
- Detectar eventos
- Minimizar impacto

**5 medidas:**
1. Estrategia Nacional de Ciberseguridad
2. Grupo de cooperacion
3. Red CSIRT
4. Condiciones de seguridad para operadores de servicios esenciales
5. Obligaciones para autoridades nacionales

### 3.3 RD-Ley 12/2018 (7 de septiembre)

**Traspone la Directiva NIS** al ordenamiento espaniol. Establece:

- Seguridad de redes y sistemas de informacion.
- Sistema de **notificacion de incidentes obligatorio**.

### 3.4 CSIRT de referencia segun el RD-Ley 12/2018

| CSIRT | Responsabilidad |
|---|---|
| **CCN-CERT** | Organismos publicos |
| **INCIBE-CERT** | Empresas, red academica y ciudadanos |
| **ESPDEF-CERT** | Defensa |

> **Pregunta tipica:** ¿Cual es el CSIRT para la red academica espaniola?
> **Respuesta: IRIS-CERT** (de RedIRIS, gestionada por INCIBE-CERT para el ambito academico).

### 3.5 Estrategia Nacional de Ciberseguridad

- **Orden PCI/487/2019** -- Aprueba la Estrategia Nacional de Ciberseguridad 2019-2023.

### 3.6 Ejemplo real
Un hospital publico sufre un ransomware. Debe notificar el incidente al **CCN-CERT** (por ser organismo publico) en el marco establecido por el RD-Ley 12/2018 y, si hay datos personales comprometidos, a la **AEPD en 72 h** (segun RGPD).

---

## 4. SGSI -- Sistema de Gestion de Seguridad de la Informacion

### 4.1 Definicion

Un SGSI es un **Sistema de GESTION de SEGURIDAD de la INFORMACION**.

> **Pregunta tipica (trampa):** ¿Un SGSI es un sistema de monitorizacion de redes?
> **Respuesta: NO.** Es un sistema de gestion (politicas, procesos, controles, mejora continua).

- **NO** es un sistema de monitorizacion de redes.
- **NO** es un plan director (aunque puede incluir uno).
- **NO** es un "sistema general de seguridad interna".

### 4.2 Normas ISO/IEC 27000

| Norma | Descripcion clave |
|---|---|
| **ISO/IEC 27000** | Vocabulario y definiciones. La serie **27.000 se asigna a SEGURIDAD DE LA INFORMACION** (no a gestion TI, ni privacidad, ni metodologias de riesgos genericas). |
| **ISO/IEC 27001** | **Certificable**. Cuerpo principal con 5 aspectos: Establecimiento del SGSI, Responsabilidad de la Direccion, Auditorias internas del SGSI, Revision continua, Mejora del SGSI. |
| **ISO/IEC 27002** | **NO certificable**. Compendio de buenas practicas. Soporte a 27001. Estructura: 11 capitulos, 39 categorias de seguridad (objetivos), **133 controles**. Incluye metodologia de Analisis y Gestion de Riesgos. |

> **Pregunta tipica:** ¿El rango 27.000 se asigna a que?
> **Respuesta: SEGURIDAD DE LA INFORMACION.**

> **Pregunta tipica:** ¿Se puede certificar una organizacion en ISO 27002?
> **Respuesta: NO.** Solo se certifica en **ISO 27001**.

### 4.3 Declaracion de aplicabilidad (ISO 27001)

Documento fundamental del SGSI que recoge:
- Controles seleccionados e implementados
- Controles excluidos (con justificacion)
- Relacion entre los riesgos identificados y los controles aplicados

### 4.4 Implementacion del SGSI (ISO 27001)

- **Dos roles clave:** Responsable del SGSI y Comite de Seguridad
- **Plan de Tratamiento de Riesgos (PTR)**
- **Marco Normativo** (politicas, procedimientos, instrucciones, registros)
- **Formacion y Concienciacion** del personal

### 4.5 Requisitos fundamentales para implantar un SGSI

- **COMPROMISO DE LA DIRECCION**
- **PLANTEAMIENTOS REALISTAS**

> **Pregunta tipica (trampa):** ¿El requisito fundamental es disponer de recursos economicos y personal suficiente?
> **Respuesta: NO.** Sin compromiso de la direccion y sin planteamientos realistas, el SGSI fracasa aunque haya dinero.

### 4.6 ¿Es necesario el analisis de riesgos?

> **Pregunta tipica:** ¿Es necesario hacer analisis de riesgos en un SGSI?
> **Respuesta: SI, SIEMPRE.** Es un pilar obligatorio.

### 4.7 Etapas para establecer un SGSI

| Fase | Contenido |
|---|---|
| **I** | Definir el **alcance** |
| **II** | Definir la **POLITICA DE SEGURIDAD** (elemento necesario a definir en esta fase) |
| **III** | Identificar **activos** |
| **IV** | Definir el **enfoque del analisis de riesgos** |
| **V** | Identificar **riesgos** |
| **VI** | Realizar el **analisis de riesgos** |
| **VII** | **Tratamiento** de riesgos |

> **Pregunta tipica:** ¿En que fase se define la politica de seguridad?
> **Respuesta: Fase II.**

### 4.8 Ciclo PDCA (Ciclo de Deming)

| Fase | Significado |
|---|---|
| **P -- Plan** | **Planificar** (establecer el SGSI) |
| **D -- Do** | **Hacer** (implementar y operar) |
| **C -- Check** | **Verificar / Revisar** (monitorear y revisar) |
| **A -- Act** | **Actuar** (mantener y mejorar) |

> **Pregunta tipica:** ¿Cual es el orden correcto del ciclo PDCA?
> **Respuesta: Planificar -> Hacer -> Revisar (Verificar) -> Actuar**

Variantes incorrectas que suelen aparecer en el examen:
- ~~Pensar, Hacer, Recordar, Analizar~~
- ~~Pensar, Hacer, Revisar, Actuar~~
- ~~Planificar, Hacer, Revisar, Analizar~~

### 4.9 Documentacion del SGSI -- 4 niveles

| Nivel | Contenido | Ejemplo |
|---|---|---|
| **1. Politicas** | Objetivos, alcance, compromiso direccion | Politica de Seguridad de la Informacion |
| **2. Procedimientos** | Como se implementan las politicas | Procedimiento de gestion de incidentes |
| **3. Instrucciones** | Pasos detallados para tareas concretas | Instruccion para configuracion de firewall |
| **4. Registros** | Evidencias de lo realizado | Logs, actas, informes de auditoria |

### 4.10 Ejemplo real
Una pyme tecnologica quiere certificarse en ISO 27001:
1. Define su alcance (Fase I).
2. Redacta la Politica de Seguridad firmada por el CEO (Fase II) -- **compromiso de la direccion**.
3. Identifica activos (servidores, codigo fuente, BD de clientes).
4. Realiza analisis de riesgos (obligatorio).
5. Aplica el ciclo PDCA de mejora continua.
6. Supera la auditoria de certificacion (27001).

---

## 5. Ley de Firma Electronica (Ley 59/2003)

### 5.1 Tipos de firma electronica

| Tipo | Caracteristicas |
|---|---|
| **Firma electronica** | Cualquier dato que identifique al firmante y este vinculado al documento. |
| **Firma electronica avanzada** | Identifica al firmante **y detecta cambios ulteriores** en los datos firmados. |
| **Firma electronica reconocida** | Avanzada + **certificado reconocido** + **dispositivo seguro de creacion de firma**. Equivale a la **firma manuscrita**. |

> **Pregunta tipica:** ¿Que tipo de firma equivale a la firma manuscrita?
> **Respuesta: La firma electronica reconocida.**

### 5.2 Ejemplo real
Un notario firma una escritura con su certificado de firma electronica reconocida almacenado en una tarjeta criptografica (dispositivo seguro). Esa firma tiene el **mismo valor legal que la firma manuscrita**.

---

## 6. Otras leyes relevantes

| Ley | Anio | Proposito |
|---|---|---|
| **Ley 11/2007** (LAECSP) | 2007 | Acceso electronico de los ciudadanos a los servicios publicos. Mandato que condujo a la creacion del **ENS**. |
| **Ley 8/2011** | 2011 | Proteccion de **infraestructuras criticas** (PIC). |
| **Ley 9/2014** | 2014 | Ley General de **Telecomunicaciones** (LGT). |
| **Ley 39/2015** | 2015 | Procedimiento Administrativo Comun de las Administraciones Publicas. |
| **Ley 40/2015** | 2015 | Regimen Juridico del Sector Publico. |

---

## 7. Legislacion complementaria

Normativa adicional relevante en el ambito de la administracion electronica y seguridad:

- **RD 704/2011** (20 mayo): Reglamento de proteccion de infraestructuras criticas.
- **Ley 30/1992**: Regimen Juridico de las AAPP. Ya incluye la obligacion de aplicacion de medios electronicos. Validez de documentos electronicos si se asegura autenticidad, integridad y conservacion.
- **RD 263/1996** (16 febrero): Uso de tecnicas electronicas por la AGE. Desarrolla el art. 45 de la Ley 30/1992.
- **Directiva 1999/93/CE** (13 diciembre): Marco comunitario para la firma electronica. Establece criterios para el reconocimiento juridico de la firma digital.
- **Directiva 2000/31/CE** (8 junio): Comercio electronico. Contratacion en linea y spam.
- **RD 209/2003** (21 febrero): Registros y notificaciones telematicas.
- **Directiva 2004/18/CE** (31 marzo): Igualdad entre medios electronicos y tradicionales. Introduce la subasta electronica.
- **Ley 56/2007** (28 diciembre): Medidas de impulso de la sociedad de la informacion. Introduce la factura electronica.
- **Ley 25/2007** (18 octubre): Conservacion de datos de comunicaciones electronicas.
- **RD 1671/2009** (6 noviembre): Desarrolla parcialmente la Ley 11/2007 (LAECSP).
- **Directiva UE 2018/1972** (11 diciembre): Codigo Europeo de Comunicaciones Electronicas.

---

## Resumen para el examen

### Preguntas trampa frecuentes

| Pregunta | Respuesta correcta |
|---|---|
| ¿Que ley asumio las funciones de LORTAD? | **LOPD** (no LSSI-CE ni Ley de Firma Electronica) |
| ¿La principal normativa de proteccion de datos es...? | **LOPD** |
| ¿La LOPD afecta a ficheros en papel? | **SI** (automatizados y no automatizados) |
| ¿El ENS esta regulado por la Constitucion / LGT? | **NO** -- RD 3/2010 (modif. RD 951/2015) |
| ¿El ENS es un reglamento de la LOPD? | **NO** |
| ¿El ENS aplica a todas las organizaciones privadas? | **NO** (solo a AAPP y entidades vinculadas) |
| ¿Conformidad Basica se audita externamente? | **NO** -- autoevaluacion cada 2 anios. Nivel informal, acreditacion voluntaria |
| ¿Las categorias Media y Alta las audita...? | Entidad acreditada por **ENAC** |
| ¿CSIRT para red academica espaniola? | **IRIS-CERT** |
| ¿El rango ISO 27.000 se asigna a...? | **Seguridad de la Informacion** |
| ¿Es necesario el analisis de riesgos en un SGSI? | **SI, SIEMPRE** |
| ¿Requisito fundamental para el SGSI? | **Compromiso de la direccion + planteamientos realistas** |
| ¿Cual es la fase II del SGSI? | Definir la **politica de seguridad** |
| ¿ISO 27001 es certificable? | **SI** |
| ¿ISO 27002 es certificable? | **NO** -- compendio de buenas practicas (133 controles). Incluye metodologia de Analisis y Gestion de Riesgos |
| ¿Ciclo PDCA correcto? | **Planificar -> Hacer -> Verificar/Revisar -> Actuar** |
| ¿Que firma equivale a la manuscrita? | **Firma electronica reconocida** |
| ¿Que ley dio origen al mandato del ENS? | **Ley 11/2007** (LAECSP) |
| ¿Plazo de notificacion de brechas de datos personales? | **72 horas** (RGPD) |
| ¿Objetivos del ENS? | **TODAS LAS RESPUESTAS SON CORRECTAS** (en preguntas de test) |
| ¿A quien obliga el ENS? | **TODAS LAS RESPUESTAS SON CORRECTAS** (AGE, CCAA, entes publicos, entidades locales) |
| ¿Cuales son los 4 objetivos de la Directiva NIS? | **Gestionar el riesgo, Proteger contra ciberataques, Detectar eventos, Minimizar impacto** |
| ¿Cual es la primera ley MUNDIAL que regulo datos de caracter personal? | **LORTAD** (1992) |
| ¿Que es una EIPD/DPIA? | Evaluacion de Impacto relativa a la Proteccion de Datos, obligatoria segun RGPD para tratamientos de alto riesgo |

### Jerarquia normativa rapida

```
Constitucion Espanola
    └── UE: RGPD (Reglamento 2016/679) -> aplicacion directa
    └── Espana:
        ├── LOPDyGDD (LO 3/2018) -- adapta RGPD, sustituye LOPD
        ├── LOPD (LO 15/1999) -- sustituida, pero fue la principal
        │   └── RD 1720/2007 (reglamento desarrollo)
        ├── ENS (RD 3/2010) -- seguridad AAPP
        ├── Ley 59/2003 -- firma electronica
        ├── LSSI-CE (Ley 34/2002) -- sociedad de la informacion
        ├── Ley 8/2011 -- infraestructuras criticas (PIC)
        ├── RD-Ley 12/2018 -- transposicion Directiva NIS
        └── ISO/IEC 27001/27002 -- SGSI (certificacion voluntaria salvo obligacion contractual/ENS)
```
