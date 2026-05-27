# Tema 1: Seguridad de la Informacion - Una Vision Integral

> **Navegacion:**
> - [← README](../README.md)
> - [GLOSARIO](../GLOSARIO.md)
> - [Chuleta numerica](08-cheat-sheet-numeros.md)
> - [Tema 2 →](02-criptografia-fundamentos.md)

---

## 1. Contextualización: Sociedad de la Información

### 1.1 Impulsores del cambio

La transformación hacia la Sociedad de la Información se sostiene sobre tres pilares impulsores:

| Categoría | Impulsores | Ejemplos reales |
|-----------|-----------|-----------------|
| **Tecnológicos** | Digitalización, ubicuidad de Internet, IoT, cloud computing, 5G, IA generativa | AWS (2006) democratiza la computación; ChatGPT alcanza 100M usuarios en 2 meses (2023) |
| **Humanos/Sociales** | Cambio de hábitos de consumo, teletrabajo, RRSS, nomadismo digital | Pandemia COVID-19 (2020): teletrabajo global masivo. TikTok supera 1.500M de usuarios |
| **Económicos/Políticos** | Globalización, economía del dato, regulación supranacional, ciber-soberanía | GDPR europeo (2018), Guerra comercial EEUU-China por el 5G (Huawei) |

### 1.2 Industria 4.0 y las cuatro revoluciones industriales (Klaus Schwab)

| Revolución | Periodo | Tecnología clave |
|------------|---------|------------------|
| **1ª Revolución** | 1760–1840 | Máquina de vapor, mecanización, ferrocarril |
| **2ª Revolución** | 1870–1914 | Electricidad, producción en cadena (Ford), teléfono |
| **3ª Revolución** | 1960–2000 | Electrónica, computación, Internet (revolución digital) |
| **4ª Revolución** | 2000–actualidad | IA, IoT, robótica avanzada, blockchain, biotecnología, computación cuántica |

> Klaus Schwab (fundador del Foro Económico Mundial, 2016): La 4ª Revolución Industrial difumina las fronteras entre lo físico, lo digital y lo biológico. Su velocidad, amplitud e impacto no tienen precedentes.

**Características distintivas de la Industria 4.0:**
- **Velocidad exponencial**, no lineal
- **Fusión de tecnologías** que borran los límites entre esferas
- **Impacto sistémico** en empresas, gobiernos y personas

### 1.2.1 Factores económicos y geopolíticos añadidos

- **Factor económico:** Globalización de la economía y precarización del empleo: estrechamiento de clases medias
- **Factor geopolítico:** Guerra fría tecnológica: EEUU y China, con la supremacía mundial en juego
- China censura Internet, Google lo acepta, 2M cámaras reconocimiento facial en China, Rusia planea Internet propia
- La desinformación como amenaza que socava la confianza de los ciudadanos en el sistema (guerra asimétrica)

**Tecnologías habilitadoras adicionales de la Industria 4.0:**
- Nanotecnología
- Computación cuántica
- Impresión 3D
- Vehículos autónomos

**Conceptos transversales de la red:**
- Internet: de sistema anti ataque nuclear a red global y ubicua
- Se habla de una "seguridad global", sin límites geográficos
- La neutralidad de Internet, también está en peligro
- La Red está creando una inteligencia colectiva

### 1.3 El ciberespacio como quinto dominio

> El **ciberespacio** es el espacio virtual que engloba todos los sistemas TIC, tanto sistemas de información como de control industrial. Es el dominio global y dinámico compuesto por las infraestructuras de TI (incluida Internet), redes de telecomunicaciones y sistemas informáticos.

Los cinco dominios de conflicto (reconocidos por la OTAN desde la Cumbre de Varsovia 2016):
1. Tierra
2. Mar
3. Aire
4. Espacio
5. **Ciberespacio**

**Ciberguerra y conflictos híbridos:**

| Concepto | Definición | Ejemplo real |
|----------|------------|--------------|
| **Ciberguerra** | Uso del ciberespacio para dañar la infraestructura crítica de un Estado | Stuxnet (2010): malware que destruyó centrifugadoras nucleares iraníes. Atribuido a EEUU-Israel |
| **Conflicto híbrido** | Combina medios convencionales, irregulares y cibernéticos | Guerra de Ucrania (2022–actualidad): ciberataques a infraestructura crítica (KYIVSTAR, DDoS a bancos) + guerra convencional |
| **Ciberataque a cadena de suministro** | Comprometer a un proveedor para llegar al objetivo final | SolarWinds (2020): hackers rusos comprometieron Orion, afectando a 18.000+ clientes incluyendo Pentagon, DHS, Microsoft |
| **Ransomware de Estado** | Gobiernos o sus proxies usan ransomware como arma geopolítica | NotPetya (2017): Rusia contra Ucrania. Daños globales estimados en 10.000M$. Maersk, Merck, FedEx paralizadas |

### 1.4 GAFAM y BATX

| Acrónimo | Empresas | Dominio principal | Característica de poder |
|----------|----------|-------------------|------------------------|
| **GAFAM** | Google (Alphabet), Apple, Facebook (Meta), Amazon, Microsoft | Occidente / Global | Control de datos, sistemas operativos, nube, RRSS, comercio electrónico |
| **BATX** | Baidu, Alibaba, Tencent, Xiaomi | China / Asia-Pacífico | Motor del ecosistema digital chino, pagos, IA, IoT |

**Implicaciones para la seguridad:**
- Concentración masiva de datos personales en pocas manos
- Capacidad de vigilancia y perfilado a escala planetaria
- Dependencia crítica de infraestructuras cloud (un fallo de AWS afecta a millones de servicios)

### 1.5 Factores económicos: la industria del cibercrimen

> La economía del cibercrimen mueve aproximadamente 8 billones de dólares anuales (estimación Cybersecurity Ventures 2023), **superando al tráfico global de drogas** y convirtiéndose en la tercera economía mundial tras EEUU y China.

**Modelos de negocio criminal:**
| Modelo | Descripción | Ejemplo |
|--------|-------------|---------|
| **Ransomware-as-a-Service (RaaS)** | Venta de kits de ransomware en la dark web con soporte técnico y reparto de beneficios | REvil, LockBit, Conti ofrecían servicio con SLA |
| **Cibercrimen como economía de plataforma** | Marketplaces especializados, brokers de acceso inicial, lavado de criptomonedas | AlphaBay, Hydra (mercados cerrados, ya desmantelados) |
| **Ataques a infraestructura crítica** | Extorsión con altísimo rescate por paralizar operaciones esenciales | Colonial Pipeline (2021): 4,4M$ de rescate pagado. Caos de suministro de combustible en la costa este EEUU |

---

## 2. Definiciones y conceptos básicos

### 2.1 Seguridad Informática

> Disciplina que diseña **normas, procedimientos, métodos y técnicas** para garantizar el procesamiento **seguro** de datos en **SISTEMAS INFORMÁTICOS** (hardware + software).

Se centra en proteger el sistema en sí (máquinas, programas, datos almacenados).

### 2.2 Seguridad en Tecnologías de la Información (TI)

Amplía el concepto anterior añadiendo la **transmisión** de información **entre sistemas**. Incorpora la protección durante el tránsito por redes.

### 2.3 Ciberseguridad

> Conjunto de herramientas, políticas, conceptos, salvaguardas, directrices, enfoques de gestión, acciones, formación, buenas prácticas y tecnologías para proteger los activos de las organizaciones y usuarios **en el ciberespacio**.

Enfoque más amplio que incluye la defensa del dominio cibernético, incluyendo infraestructuras nacionales críticas.

- Una organización puede hablar de seguridad en TIs, pero a nivel nacional o supranacional, el concepto adecuado será **ciberseguridad**
- La ciberseguridad contempla hogares, empresas, industrias, administraciones, infraestructuras críticas, defensa, etc.

### 2.4 Seguridad de la Información (definición MAGERIT V3)

> **Capacidad de resistir**, con un cierto nivel de confianza, accidentes o acciones ilícitas o malintencionadas que comprometan la **disponibilidad, integridad y confidencialidad** de los datos almacenados o transmitidos y de los servicios ofrecidos o accesibles.

**Características distintivas de la Seguridad de la Información:**
- **Visión INTEGRAL**: abarca seguridad informática + TI + ciberseguridad
- Incluye el **factor humano** como componente crítico
- **Independiente del medio físico**: protege la información esté en papel, en un disco duro, en tránsito o en la nube, o incluso en la mente de las personas
- Cubre todo el ciclo de vida de la información: creación → almacenamiento → transmisión → procesamiento → destrucción

### 2.5 ISO 27000: dimensiones ampliadas

La familia ISO 27000 añade dos dimensiones adicionales a la triada clásica D+I+C:

| Dimensión | Sigla | Definición |
|-----------|-------|------------|
| **Disponibilidad** | D | Información accesible y utilizable cuando se requiere |
| **Integridad** | I | Precisión y completitud. Sin alteraciones no autorizadas |
| **Confidencialidad** | C | No divulgación a individuos no autorizados |
| **Autenticación** | A | Verificación de la identidad del usuario/sistema |
| **No Repudio** | NR | Imposibilidad de negar participación en una acción |

Juntas forman los **5 pilares de la Seguridad de la Información**.

> **El activo más importante a proteger es la INFORMACIÓN**, por encima del hardware, software o cualquier otro recurso.

---

## 2.6 Evolución histórica de la seguridad en 3 fases

- **Fase 1:** Énfasis en respuesta ante ataques por explotación de vulnerabilidades
- **Fase 2:** Incorporación del análisis de riesgos con 3 ejes (activos, vulnerabilidades, amenazas)
- **Fase 3:** Seguridad de la información con visión integral (añade riesgos organizacionales, operacionales, físicos y de TIs). Integra el factor humano

---

## 3. Datos vs Información

| Concepto | Definición | Naturaleza |
|----------|------------|------------|
| **Dato** | Símbolo que representa un hecho, valor o medida sin contexto interpretativo | Materia prima, sin significado por sí solo |
| **Información** | Resultado de procesar, transformar o interpretar datos, dotándolos de significado y contexto | Elemento de **valor** para la toma de decisiones |

**Ejemplo ilustrativo:**

```
"37.5"                                    → DATO (número aislado)
"La temperatura corporal es 37.5°C"        → INFORMACIÓN (dato + contexto/magnitud)
"El paciente tiene 37.5°C de fiebre"       → INFORMACIÓN CON VALOR (diagnóstico, implica acción)
```

**¿Por qué es relevante para la seguridad?**
- Protegemos **información**, no solo datos
- Un dato fuera de contexto puede no tener valor; en su contexto puede ser crítico (un número puede ser desde una temperatura inocua hasta un PIN bancario)
- La agregación de múltiples datos aparentemente inocuos puede generar información sensible (problema de **metadatos**)

---

## 4. Terminología fundamental

| Término | Definición | Ejemplo real |
|---------|------------|--------------|
| **Activo** | Recurso HW, SW, personal, administrativo o funcional necesario para la prestación del servicio. Incluye contratos de mantenimiento, protocolos de actuación | Servidor de base de datos de clientes, código fuente de producto, administrador de sistemas |
| **Vulnerabilidad** | Debilidad del sistema susceptible de ser explotada (fortuita o intencionadamente) | CVE-2021-44228 (Log4Shell): vulnerabilidad crítica en Log4j que permitía ejecución remota de código. Afectó a millones de sistemas |
| **Amenaza** | Situación con potencial de causar daño con riesgo significativo | Grupo APT28 (Fancy Bear) lanzando campañas de spear-phishing contra gobiernos |
| **Daño** | Perjuicio material o inmaterial causado por un fallo fortuito o provocado | Fuga de datos de Equifax (2017): 147M de registros expuestos. Coste: +1.400M$ en multas y remediación |
| **Ataque** | Acción deliberada de provocar daño intencionadamente | Ataque DDoS de 2,54 Tbps a Azure (2021), el mayor registrado en ese momento |
| **Riesgo** | Magnitud del daño × probabilidad de que ocurra (R = D × P) | Riesgo de ransomware en hospital: daño CRÍTICO (vidas en juego) × probabilidad ALTA = riesgo INACEPTABLE |

> **Fórmula del riesgo:** `Riesgo = Impacto (magnitud del daño) × Probabilidad (de materialización)`

| Nivel de riesgo | Probabilidad baja | Probabilidad media | Probabilidad alta |
|-----------------|-------------------|-------------------|-------------------|
| **Impacto bajo** | Riesgo aceptable | Riesgo moderado | Riesgo moderado |
| **Impacto medio** | Riesgo moderado | Riesgo alto | Riesgo alto |
| **Impacto alto** | Riesgo alto | Riesgo muy alto | Riesgo inaceptable |

---

## 5. Principios básicos de la seguridad

### Principio 1: La seguridad NO es un producto, es un PROCESO

> La seguridad tiene un **ciclo de vida** continuo: Diseño → Transición (puesta en marcha) → Operación (día a día) → Actualización y optimización (procesos de mejora del servicio)

No se puede "comprar seguridad" embebida en un firewall. Requiere:
- Revisión periódica
- Actualización de medidas
- Concienciación del personal
- Adaptación a nuevas amenazas

### Principio 2: La seguridad plena es una utopía

> No existe el sistema 100% seguro. El objetivo es gestionar el riesgo a un nivel **aceptable** para la organización.

La seguridad absoluta implicaría un coste infinito y haría el sistema inutilizable.

- **Resulta imprescindible un equilibrio entre fortaleza y usabilidad, entre coste y complejidad.**

### Principio 3: La seguridad es una CADENA

> La seguridad de un sistema es tan fuerte como su **eslabón más débil**. El atacante buscará siempre el punto más frágil.

Ejemplo real: una empresa invierte millones en firewalls y cifrado, pero un empleado deja su contraseña en un post-it pegado al monitor → toda la inversión, comprometida.

### Principio 4: El factor humano representa el ~70% de incidentes internos

> Aproximadamente el **70% de los incidentes de seguridad** tienen origen interno, ya sea por negligencia, error humano o acción maliciosa deliberada.

Esto convierte al empleado en la principal vulnerabilidad pero también en la primera línea de defensa.

- **¿Debemos protegernos de nosotros mismos?** Pregunta retórica clave que pone de manifiesto que el factor humano es simultáneamente la mayor amenaza y la principal defensa.

### Principio 5: "Todo lo que no está explícitamente permitido, está prohibido"

> Principio de **denegación por defecto**: política de seguridad que cierra todo acceso y solo abre lo estrictamente necesario. También llamado principio de **mínimo privilegio**.

Opuesto al modelo permisivo donde "todo lo no prohibido, está permitido".

---

## 6. Las cuatro preguntas clave

Toda estrategia de seguridad debe responder estas cuatro preguntas:

| Pregunta | Responde a | Herramientas/Acciones |
|----------|------------|----------------------|
| **¿Qué proteger?** | Inventario de activos | Catálogo de HW, SW, comunicaciones, bases de datos, personal crítico, contratos, propiedad intelectual |
| **¿Contra quién?** | Perfiles de atacantes | Script kiddies, hacktivistas, cibercriminales, APTs estatales, insider malicioso, negligencia interna |
| **¿Cómo?** | Mecanismos de protección | Tecnologías (cortafuegos, cifrado, IDS/IPS), normas, procedimientos, buenas prácticas (ISO 27001), formación |
| **¿Hasta dónde?** | Compromiso valor vs coste | Lo que cuesta proteger no debe superar el valor de lo protegido. Buscar el nivel de riesgo aceptable |

---

## 7. Las cinco dimensiones/pilares (con ejemplos reales)

### 7.1 Disponibilidad

> Propiedad de que la información esté **accesible y utilizable** cuando la requiera una persona o sistema autorizado.

**Es la característica MÁS importante en la mayoría de sistemas de negocio** (sin disponibilidad, las demás dimensiones pierden sentido operativo).

**Ejemplos reales:**
| Incidente | Año | Impacto |
|-----------|-----|---------|
| **DDoS a Dyn DNS** | 2016 | Botnet Mirai saturó Dyn, tirando abajo Twitter, Netflix, Reddit, Airbnb y CNN durante horas en la costa este EEUU |
| **Caída global de WhatsApp** | 2021 | 6 horas de indisponibilidad afectaron a ~2.000M de usuarios. Causa: error en configuración BGP |
| **Ataque DDoS a GitHub** | 2018 | 1,35 Tbps de tráfico malicioso, el mayor registrado en ese momento. Mitigado en minutos gracias a Akamai |
| **Colonial Pipeline** | 2021 | Ransomware paró operaciones de suministro de combustible 5 días. Declaración de emergencia federal en EEUU |

**Mecanismos de protección de disponibilidad:**
- Sistemas redundantes (RAID, clustering, hot standby)
- Balanceadores de carga
- Sistemas anti-DDoS (Cloudflare, Akamai, AWS Shield)
- Planes de recuperación ante desastres (DRP)
- SAIs y generadores eléctricos

### 7.2 Integridad

> Propiedad de salvaguardar la **precisión y completitud** de los activos. Prevenir la alteración, modificación o eliminación no autorizada de la información.

Está íntimamente asociada a la **FIABILIDAD**: una información fiable es aquella que mantiene su integridad.

**Ejemplos reales:**
| Incidente | Descripción |
|-----------|-------------|
| **Modificación de transferencia bancaria** | Un atacante intercepta una transferencia de 100€ y modifica el IBAN de destino y la cuantía a 10.000€ (ataque Man-in-the-Middle + alteración). Caso real del troyano bancario Zeus |
| **Ataque SWIFT a Bangladesh Bank** | 2016: hackers norcoreanos (grupo Lazarus) manipularon mensajes SWIFT para intentar robar 951M$ del banco central de Bangladesh. Lograron transferir 81M$ |
| **Stuxnet** | 2010: alteró la velocidad de centrifugadoras nucleares iraníes modificando señales de control industrial mientras mostraba valores normales en los paneles de monitorización |
| **Wikipedia vandalism** | Ediciones maliciosas que alteran datos biográficos o históricos con información falsa. Sistemas de moderación y firmas criptográficas protegen la integridad |

**Mecanismos de protección de integridad:**
- Funciones hash (SHA-256, SHA-3)
- Firmas digitales
- Control de versiones (Git)
- Registros de auditoría (logs inmutables)
- Checksums y CRC para detectar corrupción de datos

### 7.3 Confidencialidad

> Propiedad de que la información **no esté disponible o revelada** a individuos, entidades o procesos no autorizados.

**No debe confundirse con privacidad** (aunque están relacionadas). Confidencialidad es una propiedad del sistema; privacidad es un derecho del individuo.

**Ejemplos reales:**
| Incidente | Año | Alcance |
|-----------|-----|---------|
| **Filtración de Snowden** | 2013 | Reveló programas de vigilancia masiva de la NSA (PRISM, XKeyscore). Puso la confidencialidad de las comunicaciones globales en debate |
| **Panama Papers** | 2016 | Filtración de 11,5M documentos del bufete Mossack Fonseca. La mayor filtración de la historia hasta entonces |
| **WikiLeaks / Chelsea Manning** | 2010 | Fuga de documentos clasificados militares y diplomáticos de EEUU. 750.000+ documentos expuestos |
| **Cifrado E2E en Signal y WhatsApp** | Actualidad | Implementaciones de Signal Protocol que garantizan que ni siquiera la plataforma puede leer los mensajes |

**Mecanismos de protección de confidencialidad:**
- Cifrado (simétrico AES, asimétrico RSA/ECC)
- Control de acceso (ACL, RBAC, MAC)
- DLP (Data Loss Prevention)
- Clasificación de la información (confidencial, restringida, pública)
- Acuerdos de confidencialidad (NDA) con empleados y terceros

### 7.4 Autenticación

> Proceso de **verificar la identidad** de un usuario, sistema o entidad antes de conceder acceso a los recursos.

**Los tres factores de autenticación** (explicados en detalle en §12):

| Factor | Tipo | Ejemplos |
|--------|------|----------|
| **Conocimiento** | Algo que se SABE | Contraseña, PIN, DNI, nombre de usuario |
| **Posesión** | Algo que se TIENE | DNI electrónico, móvil, token OTP, tarjeta criptográfica, llave hardware |
| **Existencia** | Algo que se ES | Huella dactilar, iris, retina, geometría de la mano, rasgos faciales, ADN |

**Ejemplo real:** Los bancos europeos implementan **PSD2** que exige **SCA (Strong Customer Authentication)** combinando al menos **2 de los 3 factores** para cualquier operación.

### 7.5 No Repudio

> Capacidad de probar de forma inequívoca la **participación** de una entidad en una acción o comunicación, de modo que no pueda negarla posteriormente.

**Dos vertientes:**

| Tipo | Significado | Mecanismo |
|------|-------------|-----------|
| **No repudio en origen** | El emisor no puede negar haber enviado el mensaje | Firma digital del emisor |
| **No repudio en destino** | El receptor no puede negar haber recibido el mensaje | Acuse de recibo firmado digitalmente |

**Ejemplos reales:**
| Caso | Descripción |
|------|-------------|
| **Firma digital en contratos** | Una empresa firma un contrato con su cliente mediante firma electrónica reconocida. Meses después no puede alegar que "no firmó" porque la firma es criptográficamente verificable |
| **Notificaciones electrónicas de Hacienda** | La AEAT envía notificaciones con acuse de recibo. El contribuyente no puede alegar "no me enteré" porque el sistema prueba la recepción |
| **Transacciones blockchain** | Bitcoin/Ethereum: cada transacción está firmada criptográficamente, garantizando que solo el poseedor de la clave privada pudo ordenarla |

---

## 8. Enfoques de la seguridad

La Seguridad de la Información debe abordarse desde tres vertientes complementarias:

### 8.1 Enfoque normativo/legal

Cumplir con el marco jurídico aplicable:
- **LOPDGDD** (Ley Orgánica 3/2018 de Protección de Datos y Garantía de Derechos Digitales)
- **LSSICE** (Ley 34/2002 de Servicios de la Sociedad de la Información y Comercio Electrónico)
- **Ley 59/2003 de Firma Electrónica**
- **Ley de Propiedad Intelectual** (RDL 1/1996)
- **Ley General de Telecomunicaciones** (Ley 11/2022)
- **RGPD** (Reglamento General de Protección de Datos europeo)

### 8.2 Enfoque de negocio

Alinear la seguridad con los objetivos empresariales:
- Determinar el **nivel adecuado** de seguridad (ni más ni menos del necesario)
- Gestionar el **valor** que la información representa para el negocio
- Garantizar la **recuperación** ante incidentes (continuidad de negocio)
- Relación **coste/beneficio** de las medidas de seguridad

### 8.3 Enfoque de amenazas tecnológicas

Identificar y mitigar las amenazas técnicas:
- **Hacking**: acceso no autorizado a sistemas
- **Malware**: virus, troyanos, ransomware, spyware, rootkits
- **Fuga de información**: pérdida o exposición de datos sensibles
- **Ingeniería social**: manipulación psicológica para obtener acceso o información

> Para una **visión integral**, deben considerarse **las 3 vertientes simultáneamente**: cumplir la ley (normativa), añadir valor al negocio (negocio) y defenderse de amenazas reales (tecnológica).

---

## 9. Política de Seguridad

### 9.1 Definición

> Conjunto de **normas y procedimientos** de obligado cumplimiento para toda persona o entidad con acceso a la información o a la tecnología de la organización.

Es el documento de más alto nivel que establece el marco de seguridad de la organización.

### 9.2 Características (las 6 son necesarias)

| Característica | Significado | Ejemplo de incumplimiento |
|----------------|-------------|---------------------------|
| **Abarcable** | Debe cubrir todos los aspectos relevantes de la seguridad (física, lógica, organizativa, legal) | Política que solo habla de contraseñas pero ignora el control de acceso físico |
| **Inteligible** | Redactada en lenguaje claro, comprensible para todos los destinatarios, no solo técnicos | Documento plagado de tecnicismos que el personal de RRHH no entiende |
| **Obligado cumplimiento** | Debe ser de cumplimiento obligatorio, con sanciones por incumplimiento | Política sin consecuencias: se convierte en papel mojado |
| **Concreción de responsabilidades** | Asignar claramente quién es responsable de qué | "Todos son responsables de la seguridad" → en la práctica, nadie lo es |
| **Asequible** | Realista y alcanzable con los recursos disponibles | Exigir autenticación biométrica a una PYME de 5 empleados sin presupuesto |
| **Mejorable** | Debe revisarse y actualizarse periódicamente | Política de seguridad de 2005 que no contempla cloud computing ni teletrabajo |

> **¡TODAS son características necesarias!** Una política que falle en una sola de ellas queda comprometida en su efectividad global.

---

## 10. Medidas con el personal y tipos de seguridad

### 10.1 Las 3 medidas principales con el personal

| Medida | Descripción | Acciones concretas |
|--------|-------------|-------------------|
| **Formación** | Capacitar al personal en materia de seguridad | Cursos periódicos, simulacros de phishing, concienciación sobre ingeniería social |
| **Fiabilidad** | Garantizar la confianza en el personal con acceso a información sensible | Verificación de antecedentes, referencias, acuerdos de confidencialidad, rotación de puestos críticos, principio de mínimo privilegio |
| **Seguimiento** | Monitorizar y auditar las acciones del personal | Registro de accesos, auditorías periódicas, revisión de logs, sistemas de detección de comportamientos anómalos |

> El factor humano es simultáneamente la **mayor vulnerabilidad** (~70% incidentes internos) y la **primera línea de defensa**.

### 10.2 Seguridad física

Protección de los activos materiales:

| Tipo | Medidas | Ejemplos reales |
|------|---------|-----------------|
| **Barreras físicas** | Control de acceso a instalaciones | Torniquetes con tarjeta, puertas blindadas, mamparas de seguridad, vallado perimetral |
| **Mecanismos de control** | Vigilancia y registro de accesos | CCTV, guardias de seguridad, registro de visitantes, sistemas biométricos de acceso |
| **Amenazas naturales** | Protección contra desastres naturales | Salas de servidores anti-incendios, sistemas anti-inundación, centros de datos en zona no sísmica |
| **Amenazas humanas** | Protección contra intrusión y sabotaje | Detectores de presencia, alarmas, jaulas de Faraday para evitar fugas electromagnéticas |

### 10.3 Seguridad lógica

Control del acceso a los datos y sistemas:

- **Identificación**: quién eres (usuario, email)
- **Autenticación**: demuéstralo (contraseña, token, biometría)
- **Autorización**: qué puedes hacer (permisos, roles)
- **Registro**: qué hiciste (logs, auditoría)

**Mecanismos:**
- Firewalls (cortafuegos de red y de aplicación)
- IDS/IPS (detección y prevención de intrusiones)
- Antimalware (antivirus, EDR — Endpoint Detection and Response)
- Cifrado de datos en reposo y en tránsito
- VPN (redes privadas virtuales)
- NAC (control de acceso a la red)

### 10.4 Seguridad organizativa

> Establece el **marco de trabajo formal** que define cómo la organización gestiona la seguridad.

**Componentes:**
- **Política de Seguridad** (documento de más alto nivel)
- **Normas y procedimientos** (desarrollan la política)
- **Roles de seguridad**: CISO (Chief Information Security Officer), delegado de protección de datos (DPO), comité de seguridad
- **Plan Director de Seguridad**: hoja de ruta estratégica
- **Planes operativos**: DRP (Disaster Recovery Plan), BCP (Business Continuity Plan)
- **Cumplimiento normativo**: ISO 27001, ENS (Esquema Nacional de Seguridad), RGPD

---

## 11. Seguridad por oscuridad vs conocimiento

### 11.1 Seguridad por oscuridad (Security through obscurity)

> Paradigma que basa la seguridad de un sistema en el **secreto del sistema mismo** (su diseño, implementación o funcionamiento). **ES INEFICAZ** como estrategia única.

Si la seguridad depende de que el atacante no conozca cómo funciona el sistema, en el momento en que lo descubre, **toda la seguridad se derrumba**.

**Ejemplo:** un fabricante oculta el puerto trasero de administración de sus routers sin protección criptográfica, pensando que nadie lo encontrará. Un atacante que haga ingeniería inversa lo descubre y compromete todos los dispositivos.

### 11.2 Principio de Kerckhoffs (1880)

> Un criptosistema debe ser seguro **incluso si todo lo relativo al sistema, excepto la clave, es de conocimiento público**.

Formulado por Auguste Kerckhoffs, criptógrafo holandés, en su ensayo "La Cryptographie Militaire" (1883).

**Implicaciones:**
- Los algoritmos deben ser públicos y escrutables por la comunidad científica
- La seguridad recae en la **clave**, no en el algoritmo
- Ejemplo: AES-256 es público y conocido por todos. Su seguridad depende de la clave de 256 bits, no de mantener secreto el algoritmo
- TODO sistema que viole este principio es sospechoso de contener puertas traseras

### 11.3 Esteganografía

> Técnica que consiste en **ocultar la existencia misma del mensaje** dentro de otro soporte inocuo (imagen, audio, vídeo, texto).

Se basa en **seguridad por oscuridad**: si no se detecta que hay un mensaje, no se intentará descifrarlo.

**Ejemplo real:**
- Inserción de texto cifrado en los bits menos significativos (LSB) de los píxeles de una imagen JPEG
- Caso FBI vs espías rusos (2010): agentes rusos usaban esteganografía en fotos públicas de Flickr para comunicarse

> **Diferencia clave:** la esteganografía OCULTA la existencia del mensaje; la criptografía OCULTA el contenido del mensaje. Son técnicas complementarias, no excluyentes.

### 11.4 Criptología

> **Ciencia** que garantiza la privacidad de la información en su almacenamiento y transmisión.

**Ramas:**
| Rama | Objetivo |
|------|----------|
| **Criptografía** | Diseñar sistemas para cifrar la información. Proteger |
| **Criptoanálisis** | Romper o burlar esos sistemas. Atacar |

La criptografía moderna aplica el **principio de Kerckhoffs** (seguridad a través del conocimiento): algoritmos públicos, claves privadas.

### 11.5 Biometría

> Sistema de reconocimiento basado en **rasgos fisiológicos o conductuales** únicos de cada individuo.

**La biometría NO aplica el principio de seguridad a través del conocimiento.** Aplica el principio de **"algo que se ES"** (factor de existencia).

| Tipo | Rasgos | Fiabilidad |
|------|--------|------------|
| Fisiológica | Huella dactilar, iris, retina, geometría de la mano, rasgos faciales, ADN, patrón de venas | Alta |
| Conductual | Voz, firma manuscrita, ritmo de tecleo, forma de andar | Media |

**Precaución sobre la biometría:**
- Una huella dactilar es un identificador **irrevocable**: si se compromete, no se puede "cambiar" como una contraseña
- Nunca debe ser el único factor de autenticación (idealmente combinarlo con PIN o token)
- Plantea problemas graves de privacidad y protección de datos (datos biométricos = categoría especial RGPD)

> **Respuesta a la pregunta trampa:** La biometría NO aplica seguridad a través del conocimiento. Aplica el factor de **existencia** ("algo que se ES").

---

## 12. Factores de Autenticación

### Los tres factores

| Factor | Principio | Ejemplos |
|--------|-----------|----------|
| **Conocimiento** | Algo que se **SABE** | Contraseña, PIN, patrón de desbloqueo, DNI (número), nombre de usuario, respuesta a pregunta secreta |
| **Posesión** | Algo que se **TIENE** | Tarjeta criptográfica, DNIe físico, token OTP, llave hardware (YubiKey), smartphone, tarjeta SIM |
| **Existencia** | Algo que se **ES** | Huella dactilar, iris, retina, rasgos faciales, geometría de la mano, ADN, firma manuscrita, voz |

### Autenticación multifactor (MFA) y 2FA

> **Autenticación de dos factores (2FA):** combina exactamente **DOS factores de distinta categoría**. Es el estándar mínimo de seguridad para servicios sensibles.

| Tipo de autenticación | Factores combinados | Ejemplo |
|----------------------|---------------------|---------|
| **Autenticación simple (SFA)** | Un solo factor | Solo contraseña (conocimiento) — Débil |
| **Autenticación de dos factores (2FA)** | Dos factores de distinta categoría | Contraseña + código SMS (conocimiento + posesión) |
| **Autenticación multifactor (MFA)** | Dos o más factores | Contraseña + YubiKey + huella dactilar (conocimiento + posesión + existencia) |

**Ejemplo real:**
> **PSD2 (Directiva de Servicios de Pago 2 europea)** exige SCA (Strong Customer Authentication) para operaciones bancarias electrónicas: al menos 2 de los 3 factores. Tu banco te pide contraseña + código SMS o contraseña + confirmación biométrica en la app.

**Falsos 2FA (error común):**
- Contraseña + "pregunta secreta" → ambas son conocimiento. NO es 2FA real.
- PIN + contraseña → ambas son conocimiento. NO es 2FA real.

### 12.1 Identificación vs Autenticación

> **Identificación:** proceso de declarar quién eres (un solo factor, como nombre de usuario o email).
> **Autenticación:** proceso de demostrar fehacientemente que eres quien dices ser (requiere más de un factor para ser robusta).

La identificación por sí sola no garantiza la identidad: cualquiera puede decir "soy Juan". La autenticación exige prueba.

---

## 13. Identidad Digital

### 13.1 Concepto de identidad digital

> **Rastro digital:** conjunto de huellas que dejamos en Internet al interactuar con servicios y plataformas.

**Componentes del rastro digital:**

| Categoría | Ejemplos |
|-----------|----------|
| Cuentas de correo | Gmail, Outlook, Yahoo, correo corporativo |
| Perfiles en RRSS | Instagram, Twitter/X, LinkedIn, TikTok, Facebook |
| Historial de búsquedas | Google, Bing, DuckDuckGo |
| Compras online | Amazon, eBay, tiendas online |
| Opiniones y foros | Comentarios, valoraciones, Reddit |
| Metadatos | Geolocalización de fotos, hora de conexión, dispositivos usados |

> **Identidad digital = agregación del rastro digital.** El conjunto de toda la información sobre nosotros en la red es nuestra identidad digital.

### 13.2 La red no olvida

> Principio de **perdurabilidad de los datos** en Internet: una vez que algo se publica, es extraordinariamente difícil eliminarlo por completo.

- Copias en cachés, mirrors, Wayback Machine
- Screenshots y republicaciones por terceros
- Indexación en buscadores
- Las políticas de "derecho al olvido" (RGPD) ayudan, pero no son infalibles

### 13.3 Metadatos como problema de seguridad

> Los **metadatos** son "datos sobre los datos". Describen contexto, contenido y estructura de la información. **Son a menudo más reveladores que el contenido mismo.**

| Archivo | Contenido visible | Metadatos ocultos |
|---------|-------------------|-------------------|
| Foto de tus llaves | Imagen de un llavero | Coordenadas GPS de tu casa, modelo de teléfono, fecha y hora exacta |
| PDF de CV | Datos profesionales | Nombre del autor original si era una plantilla, software usado, fechas de edición |
| Email | Asunto y cuerpo | IP de origen, servidores de tránsito, cliente de correo usado |

**Ejemplo real Edward Snowden (2013):**
> "Los metadatos pueden decir más sobre una persona que el contenido de sus comunicaciones. Saber a quién llamas, cuándo, por cuánto tiempo y desde dónde basta para reconstruir tu vida entera."

### 13.4 DNI electrónico (DNIe)

> Implantado en España en **2006**. Integra **identidad digital** con **firma electrónica avanzada**.

**Funcionalidades del DNIe:**
- Identificación electrónica (autenticación)
- Firma electrónica avanzada y reconocida
- Certificados digitales integrados (autenticación + firma)
- Claves criptográficas en chip seguro

---

## 14. Firma Electrónica (Ley 59/2003)

### 14.1 Definición legal

La Ley 59/2003 de Firma Electrónica establece dos categorías principales:

### 14.2 Firma electrónica avanzada

| Propiedad | Significado |
|-----------|-------------|
| **Identifica al firmante** | Vinculada al firmante de manera única |
| **Detecta cambios ulteriores** | Permite detectar cualquier modificación posterior de los datos firmados |
| **Creada por medios bajo control exclusivo** | El firmante mantiene el control exclusivo de sus datos de creación de firma |

**Soporte técnico:** certificados software (no requieren hardware específico).

### 14.3 Firma electrónica reconocida

> Es una **firma electrónica avanzada** que cumple dos requisitos adicionales:

| Requisito | Significado |
|-----------|-------------|
| **Certificado reconocido** | Basada en un certificado cualificado/reconocido emitido por un prestador autorizado |
| **Dispositivo seguro** | Creada con un **dispositivo seguro de creación de firma** (ej: chip del DNIe, smartcard criptográfica) |

### 14.4 Equivalencia legal

> **Ambas** (firma electrónica avanzada y firma electrónica reconocida) tienen el **mismo valor legal que la firma manuscrita**, según el artículo 3 de la Ley 59/2003.

**Prestadores cualificados en España:** FNMT (CERES, DNIe), Camerfirma, ANCERT, Firmaprofesional, etc.

---

## 15. Seguridad vs Privacidad

### 15.1 Marco legal del derecho a la privacidad

| Año | Hito |
|-----|------|
| **1948** | Declaración Universal de los Derechos Humanos (ONU), Art. 12: derecho a la privacidad |
| **1978** | Constitución Española, Art. 18.4: "La ley limitará el uso de la informática para garantizar el honor y la intimidad personal y familiar de los ciudadanos y el pleno ejercicio de sus derechos" |
| **1991** | Chip Clipper: EEUU propone chip de cifrado obligatorio con puerta trasera para agencias gubernamentales |
| **1992** | LORTAD (Ley Orgánica de Regulación del Tratamiento Automatizado de Datos) |
| **1993** | Europa: Iniciativa de Directiva Europea - Claves privadas bajo control gubernamental |
| **1996** | La criptografía deja de ser considerada material militar |
| **1998** | Ley General de Telecomunicaciones |
| **2018** | RGPD (Reglamento General de Protección de Datos europeo) y LOPDGDD española |

### 15.2 Criptografía como garante de la privacidad digital

> En sistemas digitales, la **CRIPTOGRAFÍA** es la herramienta fundamental que permite garantizar la privacidad de las comunicaciones.

Sin cifrado, toda comunicación digital es esencialmente una **postal** que puede ser leída por cualquiera en el tránsito: proveedores de Internet, gobiernos, cibercriminales.

### 15.3 La tensión seguridad nacional vs privacidad

Dos fuerzas opuestas definen el debate actual:

| Fuerza | Argumento | Consecuencia |
|--------|-----------|--------------|
| **Globalización del terrorismo** | Los Estados necesitan acceso a comunicaciones para prevenir atentados | Leyes que limitan el cifrado o exigen puertas traseras |
| **Ley de Moore** | La capacidad de descifrar y almacenar crece exponencialmente | La vigilancia masiva se vuelve técnicamente viable y barata |

### 15.4 Caso histórico: Chip Clipper, PGP y Phil Zimmermann

> Uno de los conflictos más emblemáticos entre seguridad nacional y privacidad individual.

| Hito | Año | Descripción |
|------|-----|-------------|
| **Chip Clipper** | 1993 | El gobierno de EEUU propuso un chip de cifrado obligatorio con "puerta trasera" para las agencias gubernamentales. La comunidad criptográfica y de derechos civiles lo rechazó y el proyecto fue abandonado en 1996 |
| **Phil Zimmermann y PGP** | 1991 | Zimmermann creó Pretty Good Privacy (PGP), el primer sistema de cifrado para el público general. El gobierno de EEUU lo investigó por "exportación ilegal de armamento" (la criptografía era considerada munición). El caso fue finalmente sobreseído en 1996 |
| **Crypto Wars** | 1990s- actualidad | Debate recurrente sobre si los gobiernos deben obligar a incluir puertas traseras en el cifrado. En 2023 resurge con propuestas como la "Ley de Seguridad Online" británica |

### 15.5 Necesidad de garantizar la privacidad incluso ante gobiernos

Argumentos a favor de un cifrado fuerte y sin puertas traseras:

1. **Las puertas traseras para "los buenos" son puertas para "los malos"**: no existe una puerta trasera que solo puedan usar gobiernos legítimos
2. **Debilitar el cifrado debilita toda la economía digital**: banca, comercio, telemedicina dependen de cifrado fuerte
3. **Los regímenes autoritarios abusan de las capacidades de vigilancia**: herramientas diseñadas contra el terrorismo se usan contra disidentes políticos
4. **Los metadatos ya proporcionan ingente inteligencia** sin necesidad de acceder al contenido

> **Principio fundamental:** Un sistema que pueda ser vigilado por un gobierno democrático hoy, podrá ser explotado por uno autoritario mañana.

- **Necesidad de garantizar la privacidad** de los ciudadanos en todo momento, incluso suponiendo que un gobierno democrático, deje de serlo.

---

## Resumen para el examen

### Tabla de puntos clave

| # | Concepto | Punto clave |
|---|----------|-------------|
| 1 | **4 revoluciones industriales** | Vapor → Electricidad → Digital → IA/IoT (Schwab) |
| 2 | **5 dominios de conflicto** | Tierra, Mar, Aire, Espacio, **Ciberespacio** |
| 3 | **GAFAM vs BATX** | Occidente: Google, Apple, Facebook, Amazon, Microsoft — China: Baidu, Alibaba, Tencent, Xiaomi |
| 4 | **Cibercrimen** | Tercera economía mundial (~8 billones $), supera tráfico de drogas |
| 5 | **Seguridad Informática vs TI vs Ciberseguridad vs SI** | Informática = procesamiento; TI = + transmisión; Ciberseguridad = ciberespacio; **SI = visión INTEGRAL** |
| 6 | **Definición SI (MAGERIT V3)** | Capacidad de resistir → proteger D+I+C. Visión integral, independiente del medio |
| 7 | **Las 5 dimensiones (ISO 27000)** | Disponibilidad, Integridad, Confidencialidad, **Autenticación, No Repudio** |
| 8 | **Activo más importante** | La **INFORMACIÓN** |
| 9 | **Dato vs Información** | Dato = materia prima, símbolo. Información = dato + contexto + valor |
| 10 | **Activo** | Recurso HW, SW, personal, administrativo o funcional |
| 11 | **Vulnerabilidad** | Debilidad del sistema explotable (fortuita o intencionada) |
| 12 | **Amenaza** | Situación de daño con riesgo significativo |
| 13 | **Daño** | Perjuicio por fallo fortuito o provocado |
| 14 | **Ataque** | Acción de provocar daño intencionadamente |
| 15 | **Riesgo** | Impacto × Probabilidad |
| 16 | **5 principios** | Proceso (no producto), No 100%, Eslabón más débil, 70% factor humano, Denegación por defecto |
| 17 | **4 preguntas clave** | Qué proteger, Contra quién, Cómo, Hasta dónde |
| 18 | **Dimensión MÁS importante** | **Disponibilidad** (generalmente en negocio) |
| 19 | **3 enfoques** | Normativo/legal, Negocio, Amenazas tecnológicas |
| 20 | **6 características Política de Seguridad** | Abarcable, Inteligible, Obligado cumplimiento, Concreción responsabilidades, Asequible, Mejorable. **TODAS necesarias** |
| 21 | **3 medidas con el personal** | Formación, Fiabilidad, Seguimiento |
| 22 | **Seguridad física, lógica, organizativa** | Barreras físicas + Controles acceso datos + Marco formal de trabajo |
| 23 | **Seguridad por oscuridad** | El secreto del sistema como base → **INEFICAZ** |
| 24 | **Principio de Kerckhoffs (1880)** | Seguro aunque todo excepto clave sea público |
| 25 | **Esteganografía** | Oculta existencia del mensaje → se basa en oscuridad |
| 26 | **Criptología** | Criptografía (proteger) + Criptoanálisis (atacar) |
| 27 | **Biometría** | NO aplica seguridad por conocimiento → aplica "algo que se ES" |
| 28 | **3 factores de autenticación** | Conocimiento (SABE), Posesión (TIENE), Existencia (ES) |
| 29 | **2FA** | Dos factores de distinta categoría. PSD2 obliga en banca |
| 30 | **Identidad Digital** | Agregación del rastro digital |
| 31 | **Metadatos** | Datos sobre datos. A menudo más reveladores que el contenido |
| 32 | **DNIe (2006)** | Identidad digital + firma electrónica avanzada |
| 33 | **Firma electrónica avanzada vs reconocida** | Avanzada = identifica + detecta cambios. Reconocida = avanzada + certificado reconocido + dispositivo seguro |
| 34 | **Valor legal** | Ambas equivalen a la firma manuscrita (Ley 59/2003) |
| 35 | **Seguridad vs Privacidad** | La criptografía garantiza la privacidad digital. Tensión con seguridad nacional |
| 36 | **Caso Chip Clipper + PGP + Zimmermann** | Conflicto histórico gobierno vs cifrado ciudadano |

### Preguntas frecuentes de examen

**Q1: ¿Cuál es la diferencia entre Seguridad Informática y Seguridad de la Información?**
> La Seguridad Informática protege SISTEMAS INFORMÁTICOS (HW+SW). La Seguridad de la Información es una visión INTEGRAL que protege la información independientemente del medio (papel, digital, oral) e incluye el factor humano.

**Q2: ¿Qué añade ISO 27000 a la triada clásica D+I+C?**
> Añade **Autenticación** (verificar identidad) y **No Repudio** (imposibilidad de negar participación).

**Q3: ¿Qué dimensión de la seguridad es la más importante?**
> La **Disponibilidad** es generalmente la más importante para los sistemas de negocio, porque sin acceso a la información, las demás dimensiones pierden su sentido operativo.

**Q4: ¿Por qué la biometría NO es seguridad a través del conocimiento?**
> Porque la biometría se basa en el factor de **existencia** ("algo que se ES"): huella, iris, etc. La seguridad por conocimiento se basa en secreto ("algo que se SABE").

**Q5: ¿Cuáles son las 6 características de una Política de Seguridad y cuántas son necesarias?**
> Abarcable, Inteligible, Obligado cumplimiento, Concreción de responsabilidades, Asequible, Mejorable. **TODAS son necesarias.** Si falla una, la política queda comprometida.

**Q6: ¿Qué es el principio de Kerckhoffs y por qué es relevante?**
> Un criptosistema debe ser seguro incluso si todo excepto la clave es público. Desmiente la seguridad por oscuridad y es el fundamento de la criptografía moderna.

**Q7: ¿Qué diferencia hay entre firma electrónica avanzada y reconocida?**
> La avanzada identifica al firmante y detecta cambios ulteriores. La reconocida añade **certificado reconocido + dispositivo seguro de creación de firma** (como el DNIe). Ambas tienen el mismo valor legal que la firma manuscrita.

**Q8: ¿Cuáles son las 4 preguntas clave de la seguridad?**
> 1) ¿Qué proteger? 2) ¿Contra quién? 3) ¿Cómo? 4) ¿Hasta dónde?

**Q9: Define riesgo y su fórmula.**
> Riesgo = Magnitud del daño (impacto) × Probabilidad de que ocurra.

**Q10: ¿Qué son los metadatos y por qué son un problema de seguridad?**
> Datos que describen otros datos. A menudo revelan más información que el contenido mismo (ubicaciones, relaciones, hábitos). Una foto puede contener coordenadas GPS; un email revela IP de origen y contactos frecuentes.

---

> **Referencia cruzada:** Los conceptos de criptografía se desarrollan en [Tema 2 - Criptografía: Fundamentos](02_criptografia-fundamentos.md). Las amenazas a sistemas en [Tema 3](03_amenazas-sistemas.md). Los mecanismos de defensa en [Tema 4](04_mecanismos-defensa.md). La gestión de seguridad en [Tema 5](05_gestion-seguridad.md). La legislación en [Tema 6](06_legislacion-normativa.md).

---

## Conceptos clave para el examen

- La Seguridad de la Informacion es una vision INTEGRAL que abarca seguridad informatica, TI y ciberseguridad
- Las 5 dimensiones ISO 27000: Disponibilidad, Integridad, Confidencialidad, Autenticacion, No Repudio
- El activo mas importante es la INFORMACION, no el hardware ni el software
- La seguridad NO es un producto, es un PROCESO con ciclo de vida: Diseno → Transicion → Operacion → Actualizacion y optimizacion
- La seguridad absoluta no existe; se busca un nivel de riesgo aceptable
- La seguridad es tan fuerte como su eslabon mas debil
- El factor humano representa ~70% de incidentes internos
- Principio de denegacion por defecto: todo lo no permitido explicitamente esta prohibido
- Identificacion (un solo factor) vs Autenticacion (requiere mas de uno)
- Los 3 factores de autenticacion: Conocimiento (algo que se SABE), Posesion (algo que se TIENE), Existencia (algo que se ES)
- 2FA requiere dos factores de distinta categoria
- La biometria NO aplica seguridad a traves del conocimiento, aplica factor de existencia
- Principio de Kerckhoffs: el sistema debe ser seguro aunque todo excepto la clave sea publico
- Seguridad por oscuridad es INEFICAZ como estrategia unica
- Riesgo = Impacto x Probabilidad
- Las 6 caracteristicas de la Politica de Seguridad (TODAS necesarias): Abarcable, Inteligible, Obligado cumplimiento, Concrecion de responsabilidades, Asequible, Mejorable
- Firma electronica avanzada y reconocida tienen el mismo valor legal que la firma manuscrita
- La criptografia garantiza la privacidad digital; tension permanente con seguridad nacional
- Internet: de sistema anti ataque nuclear a red global y ubicua
- La neutralidad de Internet esta en peligro
- Resulta imprescindible un equilibrio entre fortaleza y usabilidad, entre coste y complejidad
