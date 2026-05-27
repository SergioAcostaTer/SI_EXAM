# UA 6 - Legislacion y Normativa en Seguridad de la Informacion

> **Navegacion:**
> - [← README](../README.md)
> - [← Tema 5](05-gestion-seguridad.md)
> - [GLOSARIO](../GLOSARIO.md)
> - [Chuleta numerica](08-cheat-sheet-numeros.md)

---

## 1. Protección de Datos Personales

### 1.1 Evolución legislativa

| Norma | Año | Descripción clave |
|---|---|---|
| **LORTAD** | 1992 | Primera ley española de protección de datos. Sustituida por la LOPD. |
| **LOPD** (LO 15/1999) | 1999 | Asume las funciones de LORTAD. Regula el tratamiento de datos y ficheros, **en cualquier soporte** (digital y papel). |
| **RD 1720/2007** | 2007 | Reglamento de desarrollo de la LOPD. |
| **RGPD** (UE 2016/679) | 2016 | Reglamento europeo de aplicación directa. Novedades: Delegado de Protección de Datos (DPD), enfoque en tratamiento, comunicación de incidentes en **72 h**, sanciones de hasta **20 M€ o 4 % de facturación**. |
| **LOPDyGDD** (LO 3/2018) | 2018 | Adapta el RGPD a España. **Sustituye a la LOPD**. |

> **Pregunta típica de examen:** ¿Qué ley asumió las funciones de la LORTAD?
> **Respuesta: LOPD** (Ley Orgánica 15/1999).

> **Pregunta típica:** ¿La LOPD afecta solo a ficheros digitales?
> **Respuesta: NO.** Afecta a ficheros **automatizados (digitales) Y no automatizados (papel)**.

> **Pregunta típica:** ¿Cuál es la principal normativa de protección de datos?
> **Respuesta: LOPD** (no la Ley de Firma Electrónica, ni la LGT, ni la LSSI-CE).

### 1.2 Ejemplo real
Un hospital conserva historiales clínicos tanto en su sistema informático como en archivadores físicos. La LOPD (y hoy la LOPDyGDD) obliga a proteger **ambos** soportes: cifrado en base de datos y armario cerrado con llave para el papel.

---

## 2. Esquema Nacional de Seguridad (ENS)

### 2.1 Regulación

- **Real Decreto 3/2010**, de 8 de enero (modificado por RD 951/2015).
- **NO** está regulado por la Constitución, ni por la LGT, ni por la LOPD.

### 2.2 ¿Qué establece el ENS?

Establece las **condiciones de seguridad requeridas en el uso de medios electrónicos en el ámbito de la ADMINISTRACIÓN PÚBLICA**.

- **NO** es un reglamento de la LOPD.
- **NO** son normas para empresas públicas genéricas.
- **NO** aplica directamente a organizaciones privadas (salvo que presten servicios a la AGE).

### 2.3 Objetivos principales

1. Establecer la política de seguridad en el uso de medios electrónicos (derivada de la Ley 11/2007 — LAECSP).
2. Crear un marco común para las AAPP en materia de seguridad TIC.
3. Aportar confianza a los ciudadanos en sus derechos y deberes con las AAPP por medios telemáticos.

> **Pregunta típica:** ¿Cuáles son los objetivos del ENS?
> **Respuesta: TODAS LAS RESPUESTAS SON CORRECTAS** (las tres anteriores).

### 2.4 Ámbito de aplicación — Obligado cumplimiento

- Administración General del Estado (AGE)
- Administraciones de las Comunidades Autónomas
- Entidades de Derecho público vinculadas a las AAPP
- Entidades de Administración Local

> **Pregunta típica:** ¿A quién obliga el ENS?
> **Respuesta: TODAS LAS RESPUESTAS SON CORRECTAS** (todos los entes anteriores).

**Excluidos:** sistemas que traten **información clasificada**.

### 2.5 Categorización de sistemas

| Categoría | Criterio |
|---|---|
| **Básica** | Menor impacto |
| **Media** | Impacto moderado |
| **Alta** | Mayor impacto |

Se determina por cada **dimensión de seguridad** (confidencialidad, integridad, disponibilidad, autenticidad, trazabilidad).

### 2.6 Conformidad con el ENS

| Categoría | Método de verificación | Periodicidad |
|---|---|---|
| **Básica** | **Autoevaluación** | Cada 2 años |
| **Media** | **Auditoría externa** (entidad acreditada ENAC) | Cada 2 años |
| **Alta** | **Auditoría externa** (entidad acreditada ENAC) | Cada 2 años |

> **Pregunta típica:** ¿Cómo se verifica la conformidad de un sistema de categoría Básica?
> **Respuesta: Autoevaluación cada 2 años.**

> **Pregunta típica:** ¿Quién audita los sistemas de categoría Media y Alta?
> **Respuesta: Entidad acreditada por ENAC.**

### 2.7 Elementos principales del ENS

- Principios básicos
- Requisitos mínimos
- Medidas de seguridad proporcionadas
- Auditoría de seguridad
- Respuesta a incidentes
- Certificación

### 2.8 Ejemplo real
Un ayuntamiento que ofrece sede electrónica a sus ciudadanos (consulta de expedientes, pago de tasas) debe categorizar su plataforma (normalmente **Media**) y someterse a auditoría obligatoria cada 2 años mediante una entidad acreditada por ENAC.

---

## 3. Ciberseguridad

### 3.1 LSSI-CE (Ley 34/2002)

Ley de Servicios de la Sociedad de la Información y Comercio Electrónico. Regula servicios online, comercio electrónico, cookies, comunicaciones comerciales, etc.

> **Cuidado en el examen:** La LSSI-CE **NO** asumió las funciones de la LORTAD. Esa fue la LOPD.

### 3.2 Directiva NIS (UE 2016/1148)

Medidas para garantizar un **elevado nivel común de seguridad de redes y sistemas de información** en la UE. Primera directiva europea de ciberseguridad.

### 3.3 RD-Ley 12/2018 (7 de septiembre)

**Traspone la Directiva NIS** al ordenamiento español. Establece:

- Seguridad de redes y sistemas de información.
- Sistema de **notificación de incidentes obligatorio**.

### 3.4 CSIRT de referencia según el RD-Ley 12/2018

| CSIRT | Responsabilidad |
|---|---|
| **CCN-CERT** | Organismos públicos |
| **INCIBE-CERT** | Empresas, red académica y ciudadanos |
| **ESPDEF-CERT** | Defensa |

> **Pregunta típica:** ¿Cuál es el CSIRT para la red académica española?
> **Respuesta: IRIS-CERT** (de RedIRIS, gestionada por INCIBE-CERT para el ámbito académico).

### 3.5 Estrategia Nacional de Ciberseguridad

- **Orden PCI/487/2019** — Aprueba la Estrategia Nacional de Ciberseguridad 2019-2023.

### 3.6 Ejemplo real
Un hospital público sufre un ransomware. Debe notificar el incidente al **CCN-CERT** (por ser organismo público) en el marco establecido por el RD-Ley 12/2018 y, si hay datos personales comprometidos, a la **AEPD en 72 h** (según RGPD).

---

## 4. SGSI — Sistema de Gestión de Seguridad de la Información

### 4.1 Definición

Un SGSI es un **Sistema de GESTIÓN de SEGURIDAD de la INFORMACIÓN**.

> **Pregunta típica (trampa):** ¿Un SGSI es un sistema de monitorización de redes?
> **Respuesta: NO.** Es un sistema de gestión (políticas, procesos, controles, mejora continua).

- **NO** es un sistema de monitorización de redes.
- **NO** es un plan director (aunque puede incluir uno).
- **NO** es un "sistema general de seguridad interna".

### 4.2 Normas ISO/IEC 27000

| Norma | Descripción clave |
|---|---|
| **ISO/IEC 27000** | Vocabulario y definiciones. La serie **27.000 se asigna a SEGURIDAD DE LA INFORMACIÓN** (no a gestión TI, ni privacidad, ni metodologías de riesgos genéricas). |
| **ISO/IEC 27001** | **Certificable**. Cuerpo principal con 5 aspectos (contexto, liderazgo, planificación, soporte, operación, evaluación, mejora). |
| **ISO/IEC 27002** | **NO certificable**. Compendio de buenas prácticas. Soporte a 27001. Estructura: 11 capítulos, 39 categorías, **133 controles**. |

> **Pregunta típica:** ¿El rango 27.000 se asigna a qué?
> **Respuesta: SEGURIDAD DE LA INFORMACIÓN.**

> **Pregunta típica:** ¿Se puede certificar una organización en ISO 27002?
> **Respuesta: NO.** Solo se certifica en **ISO 27001**.

### 4.3 Requisitos fundamentales para implantar un SGSI

- **COMPROMISO DE LA DIRECCIÓN**
- **PLANTEAMIENTOS REALISTAS**

> **Pregunta típica (trampa):** ¿El requisito fundamental es disponer de recursos económicos y personal suficiente?
> **Respuesta: NO.** Sin compromiso de la dirección y sin planteamientos realistas, el SGSI fracasa aunque haya dinero.

### 4.4 ¿Es necesario el análisis de riesgos?

> **Pregunta típica:** ¿Es necesario hacer análisis de riesgos en un SGSI?
> **Respuesta: SÍ, SIEMPRE.** Es un pilar obligatorio.

### 4.5 Etapas para establecer un SGSI

| Fase | Contenido |
|---|---|
| **I** | Definir el **alcance** |
| **II** | Definir la **POLÍTICA DE SEGURIDAD** (elemento necesario a definir en esta fase) |
| **III** | Identificar **activos** |
| **IV** | Definir el **enfoque del análisis de riesgos** |
| **V** | Identificar **riesgos** |
| **VI** | Realizar el **análisis de riesgos** |
| **VII** | **Tratamiento** de riesgos |

> **Pregunta típica:** ¿En qué fase se define la política de seguridad?
> **Respuesta: Fase II.**

### 4.6 Ciclo PDCA (Ciclo de Deming)

| Fase | Significado |
|---|---|
| **P — Plan** | **Planificar** (establecer el SGSI) |
| **D — Do** | **Hacer** (implementar y operar) |
| **C — Check** | **Verificar / Revisar** (monitorear y revisar) |
| **A — Act** | **Actuar** (mantener y mejorar) |

> **Pregunta típica:** ¿Cuál es el orden correcto del ciclo PDCA?
> **Respuesta: Planificar → Hacer → Revisar (Verificar) → Actuar**

Variantes incorrectas que suelen aparecer en el examen:
- ~~Pensar, Hacer, Recordar, Analizar~~
- ~~Pensar, Hacer, Revisar, Actuar~~
- ~~Planificar, Hacer, Revisar, Analizar~~

### 4.7 Documentación del SGSI — 4 niveles

| Nivel | Contenido | Ejemplo |
|---|---|---|
| **1. Políticas** | Objetivos, alcance, compromiso dirección | Política de Seguridad de la Información |
| **2. Procedimientos** | Cómo se implementan las políticas | Procedimiento de gestión de incidentes |
| **3. Instrucciones** | Pasos detallados para tareas concretas | Instrucción para configuración de firewall |
| **4. Registros** | Evidencias de lo realizado | Logs, actas, informes de auditoría |

### 4.8 Ejemplo real
Una pyme tecnológica quiere certificarse en ISO 27001:
1. Define su alcance (Fase I).
2. Redacta la Política de Seguridad firmada por el CEO (Fase II) — **compromiso de la dirección**.
3. Identifica activos (servidores, código fuente, BD de clientes).
4. Realiza análisis de riesgos (obligatorio).
5. Aplica el ciclo PDCA de mejora continua.
6. Supera la auditoría de certificación (27001).

---

## 5. Ley de Firma Electrónica (Ley 59/2003)

### 5.1 Tipos de firma electrónica

| Tipo | Características |
|---|---|
| **Firma electrónica** | Cualquier dato que identifique al firmante y esté vinculado al documento. |
| **Firma electrónica avanzada** | Identifica al firmante **y detecta cambios ulteriores** en los datos firmados. |
| **Firma electrónica reconocida** | Avanzada + **certificado reconocido** + **dispositivo seguro de creación de firma**. Equivale a la **firma manuscrita**. |

> **Pregunta típica:** ¿Qué tipo de firma equivale a la firma manuscrita?
> **Respuesta: La firma electrónica reconocida.**

### 5.2 Ejemplo real
Un notario firma una escritura con su certificado de firma electrónica reconocida almacenado en una tarjeta criptográfica (dispositivo seguro). Esa firma tiene el **mismo valor legal que la firma manuscrita**.

---

## 6. Otras leyes relevantes

| Ley | Año | Propósito |
|---|---|---|
| **Ley 11/2007** (LAECSP) | 2007 | Acceso electrónico de los ciudadanos a los servicios públicos. Mandato que condujo a la creación del **ENS**. |
| **Ley 8/2011** | 2011 | Protección de **infraestructuras críticas** (PIC). |
| **Ley 9/2014** | 2014 | Ley General de **Telecomunicaciones** (LGT). |
| **Ley 39/2015** | 2015 | Procedimiento Administrativo Común de las Administraciones Públicas. |
| **Ley 40/2015** | 2015 | Régimen Jurídico del Sector Público. |

---

## Resumen para el examen

### Preguntas trampa frecuentes

| Pregunta | Respuesta correcta |
|---|---|
| ¿Qué ley asumió las funciones de LORTAD? | **LOPD** (no LSSI-CE ni Ley de Firma Electrónica) |
| ¿La principal normativa de protección de datos es...? | **LOPD** |
| ¿La LOPD afecta a ficheros en papel? | **SÍ** (automatizados y no automatizados) |
| ¿El ENS está regulado por la Constitución / LGT? | **NO** — RD 3/2010 (modif. RD 951/2015) |
| ¿El ENS es un reglamento de la LOPD? | **NO** |
| ¿El ENS aplica a todas las organizaciones privadas? | **NO** (solo a AAPP y entidades vinculadas) |
| ¿Conformidad Básica se audita externamente? | **NO** — autoevaluación cada 2 años |
| ¿Las categorías Media y Alta las audita...? | Entidad acreditada por **ENAC** |
| ¿CSIRT para red académica española? | **IRIS-CERT** |
| ¿El rango ISO 27.000 se asigna a...? | **Seguridad de la Información** |
| ¿Es necesario el análisis de riesgos en un SGSI? | **SÍ, SIEMPRE** |
| ¿Requisito fundamental para el SGSI? | **Compromiso de la dirección + planteamientos realistas** |
| ¿Cuál es la fase II del SGSI? | Definir la **política de seguridad** |
| ¿ISO 27001 es certificable? | **SÍ** |
| ¿ISO 27002 es certificable? | **NO** — es un compendio de buenas prácticas (133 controles) |
| ¿Ciclo PDCA correcto? | **Planificar → Hacer → Verificar/Revisar → Actuar** |
| ¿Qué firma equivale a la manuscrita? | **Firma electrónica reconocida** |
| ¿Qué ley dio origen al mandato del ENS? | **Ley 11/2007** (LAECSP) |
| ¿Plazo de notificación de brechas de datos personales? | **72 horas** (RGPD) |
| ¿Objetivos del ENS? | **TODAS LAS RESPUESTAS SON CORRECTAS** (en preguntas de test) |
| ¿A quién obliga el ENS? | **TODAS LAS RESPUESTAS SON CORRECTAS** (AGE, CCAA, entes públicos, entidades locales) |

### Jerarquía normativa rápida

```
Constitución Española
    └── UE: RGPD (Reglamento 2016/679) → aplicación directa
    └── España:
        ├── LOPDyGDD (LO 3/2018) — adapta RGPD, sustituye LOPD
        ├── LOPD (LO 15/1999) — sustituida, pero fue la principal
        │   └── RD 1720/2007 (reglamento desarrollo)
        ├── ENS (RD 3/2010) — seguridad AAPP
        ├── Ley 59/2003 — firma electrónica
        ├── LSSI-CE (Ley 34/2002) — sociedad de la información
        ├── Ley 8/2011 — infraestructuras críticas (PIC)
        ├── RD-Ley 12/2018 — transposición Directiva NIS
        └── ISO/IEC 27001/27002 — SGSI (certificación voluntaria salvo obligación contractual/ENS)
```
