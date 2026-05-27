# Banco de Preguntas — Seguridad de la Información

**4º Grado en Ingeniería Informática — Universidad de Las Palmas de Gran Canaria**

> 📚 **Referencias:** [T1 - Conceptos](01_conceptos-fundamentales.md) · [T2 - Criptografía](02_criptografia-fundamentos.md) · [T3 - Amenazas](03_amenazas-sistemas.md) · [T4 - Defensa](04_mecanismos-defensa.md) · [T5 - Gestión](05_gestion-seguridad.md) · [T6 - Legislación](06_legislacion-normativa.md) · [📖 GLOSARIO](GLOSARIO.md)

---

## UA 1. SEGURIDAD DE LA INFORMACIÓN: UNA VISIÓN INTEGRAL

📖 _Referencia completa:_ [01_conceptos-fundamentales.md](01_conceptos-fundamentales.md)

---

### 1. A la hora de analizar la seguridad de la información debemos plantearnos las siguientes preguntas básicas:

- A) qué proteger, contra quien, cómo y hasta donde
- B) qué proteger, de qué manera y hasta cuando
- C) qué proteger, contra quién y cómo
- D) cuando, cómo y donde

> **Respuesta: A**
>
> **Explicación:** Las 4 preguntas clave del análisis de seguridad son: (1) **qué proteger** — inventario de activos (hardware, software, datos, personal); (2) **contra quién** — perfiles de atacantes y amenazas; (3) **cómo** — tecnologías, normas y procedimientos; (4) **hasta dónde** — equilibrio entre el valor de lo protegido y el coste de la inversión.
>
> **Por qué no las otras:** La opción B cambia "contra quién" por "de qué manera" (redundante con "cómo") y "hasta dónde" por "hasta cuándo" (no es una pregunta del análisis). La C omite "hasta dónde", que es esencial para el análisis coste-beneficio. La D omite el "qué" y el "contra quién", que son el núcleo del análisis.

---

### 2. La Disponibilidad supone...

- A) que la información sólo debe ser accesible por las personas autorizadas
- B) evitar que la información sea alterada o modificada sin autorización
- C) que la información esté disponible cuando sea necesario y por quien esté autorizado a ello
- D) disponer de la información siempre que sea posible

> **Respuesta: C**
>
> **Explicación:** La **Disponibilidad** es la característica más importante de la seguridad. Significa que la información debe estar accesible cuando se necesita y por quien tiene autorización. Por ejemplo, si la web de tu banco no funciona cuando quieres hacer una transferencia, hay un fallo de disponibilidad.
>
> **Por qué no las otras:** A describe **Confidencialidad** (solo accesible por autorizados). B describe **Integridad** (evitar alteraciones no autorizadas). D es incorrecta porque "siempre que sea posible" no garantiza nada — la disponibilidad debe estar garantizada con un nivel de servicio (ej: 99.9% uptime), no "cuando se pueda".

---

### 3. La diferencia entre datos e información radica en...

- A) No hay diferencias
- B) Los datos son la materia prima de la información mientras que ésta es el resultado de procesar los datos
- C) Los datos son un tipo específico de información
- D) Los datos son la materia prima de la información mientras que ésta es un repositorio de datos global

> **Respuesta: B**
>
> **Explicación:** **Datos** = símbolos que representan hechos (materia prima). **Información** = resultado de procesar, transformar o interpretar datos (elemento con valor). Ejemplo: `37.5` es un dato; `"El paciente tiene 37.5°C de fiebre"` es información — el dato se ha contextualizado y aporta valor.
>
> **Por qué no las otras:** A es falsa, sí hay diferencias fundamentales. C invierte la relación (los datos no son un tipo de información, sino al revés: la información se compone de datos procesados). D es incorrecta: la información no es un "repositorio global", sino el resultado de procesar datos con un propósito.

---

### 4. ¿Qué aspectos trata de garantizar la Seguridad de la Información?

- A) La Disponibilidad, Integridad, Confidencialidad y No repudio de la información
- B) La disponibilidad, Integridad, confidencialidad, No repudio y Autenticación de la información almacenada en los ordenadores
- C) La disponibilidad, Integridad, confidencialidad, No repudio y Autenticación de la información con independencia del medio físico donde se almacene
- D) La disponibilidad, Integridad, confidencialidad, No repudio y Clasificación de la información con independencia del medio físico donde se almacene

> **Respuesta: C**
>
> **Explicación:** La Seguridad de la Información (según ISO 27000) garantiza **5 dimensiones**: Disponibilidad, Integridad, Confidencialidad, No Repudio y **Autenticación**. El aspecto clave es "con independencia del medio físico" (papel, digital, verbal), que distingue la Seguridad de la Información de la mera Seguridad Informática.
>
> **Por qué no las otras:** A omite la **Autenticación** (ISO 27000 la añadió a las 3 clásicas). B limita erróneamente a "información almacenada en ordenadores" — la Seguridad de la Información va más allá. D menciona "Clasificación" en lugar de "Autenticación" — la clasificación es una herramienta de gestión, no una dimensión/pilar de la seguridad.

---

### 5. La seguridad se considera un:

- A) Producto
- B) Proceso
- C) Activo
- D) Elemento prescindible de la organización

> **Respuesta: B**
>
> **Explicación:** La seguridad **NO es un producto** que se compra una vez y ya está. Es un **PROCESO** continuo con ciclo de vida: Diseño → Transición (puesta en marcha) → Operación (día a día) → Actualización y mejora continua. No puedes "instalar seguridad" como instalas un programa; requiere mantenimiento, revisión y adaptación constante.
>
> **Por qué no las otras:** A es justo el error conceptual que el curso enseña a evitar. C: aunque la información es un activo, la seguridad en sí misma no lo es — es una propiedad/característica que se gestiona mediante un proceso. D es totalmente falso: la seguridad es imprescindible.

---

### 6. La característica de la información asociada a la FIABILIDAD es la:

- A) Autenticación
- B) No Repudio
- C) Confidencialidad
- D) Integridad

> **Respuesta: D**
>
> **Explicación:** La **Integridad** es la característica relativa a la **fiabilidad** de la información. Si la información mantiene su integridad (no ha sido alterada sin autorización), podemos fiarnos de ella. Según las transparencias del tema 1: *"Integridad: es la característica de la información relativa a su fiabilidad. Se trata de evitar que la información sea alterada o modificada sin autorización."*
>
> **Por qué no las otras:** A (Autenticación) se asocia a la identidad — garantiza que alguien es quien dice ser. B (No Repudio) impide negar participación en una comunicación. C (Confidencialidad) se asocia al secreto y al acceso restringido.

---

### 7. La CONFIDENCIALIDAD es la característica de la información:

- A) Relacionada con la no revelación de secretos
- B) Relacionada con evitar que la información sea alterada o modificada sin autorización
- C) Vinculada a la necesidad de que quien corresponda tenga acceso a dicha información cuando lo necesite
- D) Relacionada con evitar que la información sea accesible por personas no autorizadas

> **Respuesta: D**
>
> **Explicación:** La **Confidencialidad** consiste en que la información solo sea accesible por las personas, programas o sistemas autorizados, evitando accesos no autorizados (casuales o intencionados). Según las transparencias: *"la información sólo debe ser accesible por las personas, programas o sistemas autorizados a ello, evitando accesos no autorizados."*
>
> **Por qué no las otras:** A es parcialmente correcta (la no revelación de secretos es un aspecto de la confidencialidad) pero D es la definición más precisa y completa. B describe la **Integridad** (evitar alteraciones). C describe la **Disponibilidad** (acceso cuando se necesita).

---

### 8. Algunas características que debe tener una Política de Seguridad son:

- A) Mejorable e Inteligible
- B) Todas las respuestas son correctas
- C) Abarcable y de obligado cumplimiento
- D) Asequible

> **Respuesta: B**
>
> **Explicación:** Una política de seguridad debe reunir **todas** estas características: **Abarcable** (implantable de forma efectiva), **Inteligible** (comprensible en conceptos e implicaciones), **de Obligado cumplimiento** (con procesos de auditoría), **Asequible** (no debe entorpecer el trabajo diario) y **Mejorable** (con mecanismos de autoevaluación y actualización). Como cada opción menciona características válidas pero ninguna las cubre todas, la respuesta correcta es que todas son correctas.

---

### 9. ¿Cuáles son las principales medidas a considerar con el personal de una organización en relación a la seguridad?

- A) Formación, Fiabilidad y Seguimiento
- B) Concienciación, Fiabilidad y Seguimiento
- C) Formación, Acuerdos de confidencialidad y Seguimiento
- D) Formación, Vigilancia y Aplicación de políticas de restricción de accesos

> **Respuesta: A**
>
> **Explicación:** Las tres medidas fundamentales con el personal son: **Formación** (capacitar en seguridad), **Fiabilidad** (verificar la confianza/antecedentes del personal que maneja información sensible) y **Seguimiento** (monitorizar la actividad del personal con acceso crítico). El factor humano es el eslabón más débil (causa del ~70% de incidentes internos).
>
> **Por qué no las otras:** B usa "Concienciación" en vez de "Formación" — la concienciación es parte de la formación pero no la sustituye completamente. C menciona "Acuerdos de confidencialidad" que son importantes pero no sustituyen la verificación de fiabilidad del personal. D menciona "Vigilancia" y "restricción de accesos" que son medidas de seguridad lógica, no específicamente de gestión de personal.

---

### 10. La SEGURIDAD INFORMÁTICA es:

- A) Una disciplina que se encarga de diseñar las normas, procedimientos, métodos y técnicas orientados a proveer condiciones seguras y confiables para el procesamiento de datos en sistemas informáticos
- B) Una disciplina que se encarga de diseñar las políticas de seguridad de las empresas
- C) Una metodología que se encarga de aplicar las normas, procedimientos, métodos y técnicas orientados a proveer condiciones seguras y confiables para el procesamiento de señales en sistemas informáticos
- D) Una disciplina que se encarga de diseñar las políticas de seguridad en las empresas y en la administración pública

> **Respuesta: A**
>
> **Explicación:** La seguridad informática es la **disciplina** (no metodología) que diseña normas, procedimientos, métodos y técnicas para el procesamiento seguro de **datos** (no señales) en **sistemas informáticos**. Es la definición más restrictiva: se centra en el procesamiento de datos dentro de los sistemas informáticos.
>
> **Por qué no las otras:** B y D son demasiado limitadas (solo políticas) y D añade erróneamente "administración pública" como parte de la definición. C es incorrecta porque dice "metodología" en vez de "disciplina" y "señales" en vez de "datos". La diferencia con Seguridad en TIs es que esta añade la transmisión entre sistemas; y con Ciberseguridad, que abarca todo el ciberespacio.

---

### 11. Los factores de autenticación son:

- A) Identidad, posesión y existencia
- B) Conocimiento, posesión y existencia
- C) Identidad, conocimiento y existencia
- D) Identidad, posesión y conocimiento

> **Respuesta: B**
>
> **Explicación:** Los 3 factores de autenticación (lo que permite verificar que alguien es quien dice ser) son: **Conocimiento** — algo que se SABE (contraseña, PIN); **Posesión** — algo que se TIENE (token, móvil, tarjeta criptográfica); **Existencia** — algo que se ES (huella dactilar, iris, rasgos faciales). La combinación de al menos 2 factores se denomina autenticación de dos factores (2FA), estándar actual en banca y servicios críticos.
>
> **Por qué no las otras:** A, C y D sustituyen erróneamente "Conocimiento" o "Existencia" por "Identidad" — la identidad no es un factor de autenticación, es lo que se pretende verificar. La autenticación fuerte usa al menos 2 de estos 3 factores.

---

### 12. ¿En cuál de estas ciencias o técnicas no se aplica el principio de seguridad a través del conocimiento?

- A) Esteganografía
- B) Criptología
- C) Biometría
- D) En ninguna de las indicadas

> **Respuesta: C**
>
> **Explicación:** El principio de **Kerckhoffs** (1880) establece que "un criptosistema debe ser seguro incluso si todo lo relacionado con su funcionamiento, excepto la clave, es de conocimiento público". Es lo opuesto a la "seguridad por oscuridad". La **Biometría** NO aplica este principio porque no se basa en conocimiento (claves secretas) sino en **rasgos fisiológicos o conductuales** (algo que se ES).
>
> **Por qué no las otras:** A (Esteganografía) tradicionalmente se basa en seguridad por oscuridad — ocultar la existencia misma del mensaje, no en claves públicas. B (Criptología moderna) SÍ aplica el principio de Kerckhoffs — algoritmos públicos, seguridad en la clave. D es falsa porque la biometría no aplica seguridad a través del conocimiento.

---

## UA 2. FUNDAMENTOS EN SEGURIDAD DIGITAL

📖 _Referencia completa:_ [02_criptografia-fundamentos.md](02_criptografia-fundamentos.md)

---

### Privacidad

### 13. ¿Cómo se define el concepto de PRIVACIDAD?

- A) Cómo el ámbito de la vida pública que se debe proteger de cualquier intromisión
- B) Cómo el ámbito de la vida privada que se debe proteger de la intromisión del estado
- C) Cómo el ámbito de la vida privada que se debe proteger de cualquier intromisión
- D) Cómo el ámbito de la vida pública que se debe proteger de la intromisión de los medios de comunicación

> **Respuesta: C**
>
> **Explicación:** La privacidad es el derecho fundamental (ONU 1948, Constitución Española Art. 18.4) que protege el **ámbito de la vida privada** frente a **cualquier intromisión**, no solo del Estado. Abarca protección frente a empresas, otros individuos, medios de comunicación, etc.
>
> **Por qué no las otras:** A habla de "vida pública" — la privacidad protege la vida privada, no la pública. B limita incorrectamente la protección solo frente al Estado. D mezcla dos errores: "vida pública" y limita a "medios de comunicación".

---

### 14. ¿Cuáles son las tres dimensiones más importantes de la seguridad que configuran la privacidad?

- A) Integridad, Confidencialidad y Autenticación
- B) Integridad, Confidencialidad y No repudio
- C) Autenticación, Trazabilidad y No repudio
- D) Confidencialidad, Temporalidad y No repudio

> **Respuesta: A**
>
> **Explicación:** Las tres dimensiones que configuran la privacidad son: **Integridad** (la información no se ha alterado), **Confidencialidad** (solo acceden los autorizados) y **Autenticación** (sabemos quién accede/envía). Según las transparencias: *"Objetivo de la Criptografía: Proporcionar las dimensiones de la seguridad que configuran la privacidad: Autenticación, Confidencialidad, Integridad, No Repudio, Trazabilidad, Temporalidad."* Las 3 primeras/más importantes son Integridad, Confidencialidad y Autenticación.
>
> **Por qué no las otras:** B incluye No Repudio en vez de Autenticación — el No Repudio es importante pero la Autenticación es más fundamental para la privacidad. C y D incluyen conceptos como Trazabilidad o Temporalidad, que son dimensiones adicionales pero no las 3 principales.

---

### 15. ¿Qué requisito básico de seguridad es necesario para garantizar la privacidad en los medios digitales?

- A) enviar los mensajes a través de correo electrónico
- B) el cifrado de la información
- C) la securización de las redes digitales
- D) no enviar mensajes a través de Internet

> **Respuesta: B**
>
> **Explicación:** Como se indica en las transparencias: *"La privacidad en sistemas digitales exige el empleo de criptografía."* El **cifrado** es el requisito básico: sin cifrado, cualquier intermediario (ISP, gobierno, atacante) puede leer las comunicaciones.
>
> **Por qué no las otras:** A no garantiza nada (el correo sin cifrar es como una postal). C es necesaria pero insuficiente sin cifrado (una red securizada no impide que el proveedor lea tus datos). D es una solución extrema e impracticable.

---

### Claves Simétricas

### 16. ¿Qué problema principal presentan los algoritmos de clave privada?

- A) Su excesiva lentitud
- B) La debilidad de la clave
- C) La complejidad para su uso
- D) La transmisión de la clave al destinatario del mensaje de forma segura

> **Respuesta: D**
>
> **Explicación:** El problema fundamental de la criptografía simétrica es el **intercambio de la clave**: ¿cómo haces llegar la clave secreta al destinatario sin que un atacante la intercepte? Si tienes un canal seguro para enviar la clave... ¿para qué necesitas cifrar? Esta es la paradoja que motivó el desarrollo de la criptografía asimétrica.
>
> **Por qué no las otras:** A es falso — el cifrado simétrico es muy RÁPIDO (órdenes de magnitud más rápido que el asimétrico). B no es inherente al sistema (depende del algoritmo y tamaño de clave). C es falso — el cifrado simétrico es conceptualmente simple (misma clave para cifrar y descifrar).

---

### 17. Los sistemas de clave simétrica

- A) Aseguran la integridad
- B) Aseguran la disponibilidad
- C) Aseguran la confidencialidad
- D) Aseguran el No repudio

> **Respuesta: C**
>
> **Explicación:** Los sistemas de clave simétrica aseguran **CONFIDENCIALIDAD** — el mensaje cifrado solo puede ser leído por quien posee la clave secreta. Por sí solos NO garantizan integridad (un atacante podría modificar el texto cifrado), ni autenticación, ni no repudio.
>
> **Por qué no las otras:** A requiere funciones hash o firma digital. B no depende del cifrado sino de la infraestructura. D requiere criptografía asimétrica (firma digital) — con clave simétrica, cualquiera que pueda descifrar también puede "firmar", no hay no repudio.

---

### 18. ¿Qué significa la SIMETRÍA en el concepto de clave simétrica?

- A) Que se utiliza una pareja de claves: una para cifrar y otra para descifrar
- B) Que se utiliza la misma clave tanto para cifrar como para descifrar
- C) Que se utiliza una clave para cifrar pero no es necesario ninguna para descifrar
- D) Que no se requieren claves para el cifrado

> **Respuesta: B**
>
> **Explicación:** La simetría significa que se usa **la misma clave** para ambas operaciones: cifrar y descifrar. De ahí el nombre "simétrica" — es simétrico porque la operación es la misma en ambos sentidos con la misma clave.
>
> **Por qué no las otras:** A describe la criptografía **asimétrica** (clave pública + clave privada). C y D son conceptos erróneos — siempre se necesita clave para descifrar.

---

### 19. ¿Qué aspectos determinan la potencia de los sistemas de cifrado simétrico?

- A) La calidad de la clave y la extensión del algoritmo
- B) La potencia o calidad del algoritmo y el tamaño de la clave
- C) La cantidad de veces que se puede utilizar el algoritmo y el tamaño de la clave
- D) El grado de desconocimiento que se tenga del algoritmo (secreto) y la longitud de la clave

> **Respuesta: B**
>
> **Explicación:** La potencia de un sistema de cifrado simétrico depende de dos factores: la **calidad/potencia del algoritmo** (diseño criptográfico, resistencia a criptoanálisis) y el **tamaño de la clave** (a mayor tamaño, más combinaciones posibles, más resistencia a fuerza bruta). Esto sigue el Principio de Kerckhoffs: la seguridad reside en la clave, no en el secreto del algoritmo.
>
> **Por qué no las otras:** A menciona "calidad de la clave" (la calidad la determina la aleatoriedad, no es un factor independiente del tamaño). C menciona "cantidad de veces", irrelevante para la potencia. D es justo lo contrario al principio de Kerckhoffs — la seguridad NO debe depender del secreto del algoritmo.

---

### 20. ¿Qué algoritmo de clave privada ha sustituido al algoritmo DES (Data Encryption Standard)?

- A) Doble DES (DDES)
- B) Triple DES (TDES)
- C) Cuádruple DES (QDES)
- D) Séxtuple DES (SDES)

> **Respuesta: B**
>
> **Explicación:** **Triple DES (TDES o 3DES)** fue el reemplazo directo de DES cuando este se volvió vulnerable (56 bits de clave, roto por fuerza bruta en 1998). TDES aplica el algoritmo DES tres veces con 2 o 3 claves distintas, logrando longitudes efectivas de 112 o 168 bits. Posteriormente, AES (2000) sustituyó a TDES como estándar.
>
> **Por qué no las otras:** A (Doble DES) es vulnerable a ataques "meet-in-the-middle". C y D no existen como estándares reales; son nombres inventados.

---

### Claves Asimétricas

### 21. ¿Qué posible problema se puede plantear en el uso de sistemas de clave pública?

- A) La dificultad para utilizar los algoritmos requeridos
- B) El coste computacional
- C) El intercambio de las claves públicas entre los agentes que establecen la comunicación
- D) La pérdida o sustracción de la clave privada

> **Respuesta: D**
>
> **Explicación:** La **pérdida o sustracción de la clave privada** es un problema crítico en sistemas asimétricos. Si alguien obtiene tu clave privada, puede: descifrar todos tus mensajes, suplantar tu identidad (firmar como tú) y descifrar sesiones pasadas si capturó el tráfico. Es la clave maestra de tu identidad digital. Por eso existen medidas como tarjetas criptográficas (DNIe) donde la clave privada nunca sale del chip.
>
> **Por qué no las otras:** A es falso — desde el punto de vista del usuario, usar criptografía asimétrica es transparente. B es un inconveniente real (los algoritmos asimétricos son ~1000× más lentos) pero es un problema de rendimiento, no de seguridad. C se resuelve con PKI y certificados.

---

### 22. ¿En qué se basa un algoritmo de clave asimétrica?

- A) En el uso de claves de distinta longitud para cifrar cada mensaje
- B) En el uso de dos claves apareadas: una para cifrar y otra para descifrar
- C) En la aplicación del algoritmo de Diffie-John
- D) En el uso de tres claves: dos para cifrar y otra para descifrar

> **Respuesta: B**
>
> **Explicación:** La criptografía asimétrica usa **dos claves matemáticamente relacionadas** (apareadas): una **clave pública** (para cifrar o verificar firmas) y una **clave privada** (para descifrar o firmar). Lo que una cifra, solo la otra puede descifrar — y viceversa. Es la base de RSA, Diffie-Hellman, ElGamal, etc.
>
> **Por qué no las otras:** A habla de "distinta longitud" — no es la longitud lo que varía. C dice "Diffie-John" — no existe tal algoritmo; el correcto es Diffie-Hellman. D menciona tres claves — los sistemas asimétricos usan dos claves.

---

### 23. ¿En qué se basa el funcionamiento del sistema RSA como algoritmo de cifrado de clave asimétrica?

- A) En la longitud de los números enteros
- B) En ocultar la clave pública para evitar el descifrado del mensaje
- C) En la imposibilidad computacional de factorizar números enteros muy grandes
- D) En la imposibilidad de dividir números irracionales

> **Respuesta: C**
>
> **Explicación:** RSA se basa en un problema matemático **"difícil"**: la **factorización de números enteros muy grandes** en sus factores primos. Multiplicar dos números primos grandes es fácil; dado el producto, encontrar los factores originales es computacionalmente inviable con tecnología actual. Ejemplo: multiplica 997 × 991 = 988,027 (fácil). Dado 988,027, encuentra sus factores primos (difícil sin fuerza bruta). RSA usa números de 1024-4096 bits.
>
> **Por qué no las otras:** A es vaga e imprecisa. B es incorrecta — la clave pública ES pública por definición, no se oculta. D es absurda — los números irracionales no se usan en RSA.

---

### 24. ¿Qué es RSA?

- A) Un estándar de codificación
- B) Un algoritmo de cifrado asimétrico
- C) Un algoritmo de cifrado en bloque
- D) Un algoritmo de cifrado en flujo

> **Respuesta: B**
>
> **Explicación:** RSA (Rivest-Shamir-Adleman, 1978) es un **algoritmo de cifrado asimétrico** — el más conocido y usado del mundo. Usa un par de claves (pública/privada) y se basa en la dificultad de factorizar números grandes.
>
> **Por qué no las otras:** A es incorrecta — RSA es un algoritmo, no un estándar de codificación. C y D son incorrectas — los algoritmos de bloque/flujo son propios de la criptografía simétrica; RSA es asimétrico y no opera por bloques.

---

### 25. ¿Qué familia de algoritmos criptográficos limita el tamaño de los datos de entrada?

- A) Los algoritmos de resumen
- B) Ninguna de las familias indicadas
- C) Los algoritmos de cifrado simétrico
- D) Los algoritmos de cifrado asimétrico

> **Respuesta: D**
>
> **Explicación:** Los **algoritmos asimétricos** tienen una limitación fundamental: los datos a cifrar deben ser de tamaño **menor o igual al tamaño de la clave**. Con RSA-2048, solo puedes cifrar ~256 bytes directamente. Por eso en la práctica se usan **sistemas mixtos**: se genera una clave simétrica aleatoria, se cifra el mensaje con AES (rápido, sin límite práctico), y luego se cifra ESA clave simétrica con RSA.
>
> **Por qué no las otras:** A (resumen) tiene tamaño de entrada ilimitado — puedes pasar un archivo de gigabytes a SHA-256. C (simétrico) procesa datos en bloques o flujo sin límite práctico de tamaño. B es incorrecta.

---

### 26. ¿Qué es ElGamal?

- A) Un algoritmo de cifrado asimétrico basado en la dificultad de calcular logaritmos discretos
- B) Un algoritmo de cifrado simétrico basado en la dificultad de factorizar grandes números
- C) Un algoritmo de cifrado simétrico basado en la dificultad de calcular logaritmos discretos
- D) Un algoritmo de cifrado asimétrico basado en la dificultad de factorizar grandes números

> **Respuesta: A**
>
> **Explicación:** **ElGamal** (1985, Taher ElGamal) es un algoritmo de cifrado **asimétrico** basado en el **Problema del Logaritmo Discreto (PLD)** — no en factorización. Es una alternativa a RSA con la ventaja de que no estaba patentado, lo que permitió su incorporación a PGP y otros sistemas libres. El PLD consiste en: dado g^a mod p, encontrar a es computacionalmente difícil.
>
> **Por qué no las otras:** B y C lo clasifican como simétrico (error — es asimétrico). D lo asocia a factorización (error — ElGamal se basa en logaritmos discretos; RSA es el que se basa en factorización).

---

### 27. ¿Qué dimensión de la seguridad hemos de reforzar si queremos evitar un ataque del tipo "Man in the Middle"?

- A) Autenticación
- B) Confidencialidad
- C) Disponibilidad
- D) Integridad

> **Respuesta: A**
>
> **Explicación:** Un ataque **Man in the Middle (MitM)** consiste en que un atacante se interpone entre dos partes, haciéndose pasar por cada una ante la otra. La víctima cree que habla con el banco, pero habla con el atacante; el atacante habla con el banco haciéndose pasar por la víctima. Para evitarlo, hay que reforzar la **AUTENTICACIÓN**: garantizar que cada parte es realmente quien dice ser. Esto se logra con firma de claves, certificados digitales y PKI.
>
> **Por qué no las otras:** B (confidencialidad) ya está comprometida en un MitM (el atacante lee todo). C y D no son el vector de ataque principal — el problema es de identidad/suplantación, no de disponibilidad o alteración de datos.

---

### 28. El mecanismo de firma digital

- A) Se realiza mediante el cifrado simétrico de resúmenes
- B) Se realiza mediante el cifrado asimétrico de resúmenes
- C) Se realiza mediante el cifrado de claves
- D) Ninguna de las anteriores

> **Respuesta: B**
>
> **Explicación:** La firma digital funciona así: (1) se calcula el **resumen (hash)** del documento; (2) ese resumen se cifra con la **clave PRIVADA** del firmante → eso es la firma. Para verificar: (1) se descifra la firma con la clave pública del firmante → se obtiene el resumen original; (2) se calcula el resumen del documento recibido; (3) se comparan. Si coinciden → autenticidad + integridad + no repudio.
>
> **Por qué no las otras:** A menciona "cifrado simétrico" — la firma digital requiere ASIMÉTRICO porque necesita que cualquiera pueda verificar (con clave pública) pero solo el titular pueda firmar (con clave privada). C es demasiado genérico.

---

### 29. El algoritmo de Diffie-Hellman es:

- A) Un algoritmo asimétrico para la negociación de claves simétricas
- B) Un algoritmo simétrico para la transmisión de claves asimétricas
- C) Un algoritmo simétrico para la negociación de claves asimétricas
- D) Un algoritmo asimétrico para la transmisión de claves simétricas

> **Respuesta: A**
>
> **Explicación:** Diffie-Hellman (1977) es un algoritmo **asimétrico** (usa claves pública/privada) cuyo propósito es la **NEGOCIACIÓN** de una clave secreta compartida — NO la transmisión de una clave. Dos partes generan cada una un par de claves DH, intercambian las públicas, y matemáticamente ambas obtienen el mismo secreto compartido que pueden usar como clave simétrica para AES. La magia: un atacante que vea todo el intercambio NO puede calcular el secreto compartido.
>
> **Por qué no las otras:** B y C lo clasifican erróneamente como "simétrico". D dice "transmisión" — DH no transmite la clave, la negocia/calcula en ambos extremos independientemente. La diferencia es sutil pero importante: en la transmisión envías la clave (inseguro), en la negociación cada parte la deriva sin enviarla.

---

### Sistemas criptográficos

### 30. ¿Qué caracteriza a los sistemas criptográficos HORIZONTALES?

- A) Usan una clave pública lineal
- B) Asumen que todos los agentes que intervienen en la comunicación poseen distintos niveles de confianza
- C) Asumen que todos los agentes que intervienen en la comunicación utilizan la misma clave pública
- D) Asumen que todos los agentes que intervienen en la comunicación poseen el mismo nivel de confianza

> **Respuesta: D**
>
> **Explicación:** En un sistema **horizontal** (Web of Trust / telaraña de confianza), todos los agentes están al **mismo nivel de confianza** y se firman las claves entre sí. No hay una autoridad central. Yo confío en ti porque alguien en quien confío ha firmado tu clave (confianza transitiva). Es el modelo de PGP/GPG.
>
> **Por qué no las otras:** B describe un sistema jerárquico/vertical (distintos niveles). A y C no son características definitorias de los sistemas horizontales.

---

### 31. El software PGP

- A) Se basa en un modelo horizontal
- B) Se basa en un modelo vertical
- C) Se basa en el empleo de certificados digitales
- D) Todas las anteriores

> **Respuesta: A**
>
> **Explicación:** **PGP (Pretty Good Privacy)**, creado por Phil Zimmermann en 1991, se basa en un modelo **HORIZONTAL** (Web of Trust). Los usuarios firman las claves de otros usuarios en quienes confían, creando una red de confianza descentralizada. No depende de Autoridades de Certificación centrales.
>
> **Por qué no las otras:** B es lo opuesto — el modelo vertical usa CAs. C: aunque PGP usa sus propios "certificados" (PGP keys), no son certificados X.509 en el sentido PKI tradicional. D es incorrecta porque B es falsa.

---

### 32. Los sistemas criptográficos VERTICALES:

- A) Utilizan Autoridades de Certificación para garantizar la validez y autenticidad de las claves públicas
- B) Se basan en el concepto de telaraña de confianza
- C) Necesitan que todos los certificados estén firmados por la misma autoridad
- D) Ninguna de las respuestas es correcta

> **Respuesta: A**
>
> **Explicación:** Los sistemas **verticales** (PKI — Public Key Infrastructure) utilizan **Autoridades de Certificación (CA)** que actúan como terceros de confianza. La CA firma los certificados de los agentes, garantizando la validez y autenticidad de sus claves públicas. Es el modelo usado en TLS/SSL (HTTPS), S/MIME, DNIe, etc.
>
> **Por qué no las otras:** B describe el modelo horizontal, no vertical. C es incorrecta — puede haber CAs intermedias/delegadas (cadena de confianza jerárquica), no todos los certificados son firmados por la misma CA raíz.

---

### Certificado digital

### 33. Un certificado digital

- A) Contiene la firma de la clave pública del usuario
- B) Contiene la firma de la clave privada del usuario
- C) Contiene la clave privada de la Autoridad Certificadora
- D) Ninguna de las anteriores es cierta

> **Respuesta: D**
>
> **Explicación:** Un certificado digital X.509 contiene: identidad del titular, su **clave pública** (no privada), periodo de validez, y la **firma de la CA** (realizada con la clave privada de la CA, pero el certificado no CONTIENE esa clave privada). La opción A es incorrecta porque el certificado contiene la clave pública y ES FIRMADO por la CA — no "contiene la firma de la clave pública", sino que la CA firma el certificado completo.
>
> **Por qué no las otras:** A es imprecisa — el certificado no contiene "la firma de la clave pública", contiene la clave pública y está firmado por la CA. B es falso — la clave privada NUNCA se incluye en el certificado (es secreta). C es falso — la clave privada de la CA es lo más secreto de una PKI, nunca se distribuye.

---

### 34. ¿Cuáles son las partes más importantes de un certificado digital?

- A) Clave privada, datos de identidad del titular, operaciones permitidas por el titular, firma digital realizada con la de la Autoridad de Certificación
- B) Clave pública, datos de identidad del titular, operaciones permitidas por el titular, firma digital realizada con la del titular
- C) Clave pública, datos de identidad del titular, operaciones permitidas por el titular, firma digital realizada con la de la Autoridad de Certificación
- D) Clave pública, datos de identidad del titular, operaciones permitidas por el titular, la firma digital realizada con la clave privada de la Autoridad de Certificación

> **Respuesta: D**
>
> **Explicación:** La diferencia está en el detalle. Las partes son: (1) **clave pública** del titular (nunca la privada), (2) datos de identidad, (3) operaciones permitidas, (4) firma digital de la CA realizada con la **clave PRIVADA** de la CA. La opción D es la más precisa porque especifica que la firma se realiza con la "clave privada" de la CA, mientras que C dice "con la de la Autoridad" sin especificar "clave privada".
>
> **Por qué no las otras:** A incluye erróneamente "clave privada" del titular. B dice que la firma la hace el titular, pero es la CA quien firma. C es casi correcta pero imprecisa al no especificar "clave privada" de la CA.

---

### 35. ¿Qué es una CRL?

- A) Una lista de cifradores aceptada en una transacción SSL
- B) Una lista de certificados revocados por una Autoridad
- C) Una lista de direcciones MAC cuyo acceso se permite o prohíbe explícitamente
- D) Una lista de direcciones de correo seguras

> **Respuesta: B**
>
> **Explicación:** **CRL (Certificate Revocation List)** es una lista de **certificados revocados** por una Autoridad de Certificación antes de su fecha de expiración. Un certificado puede ser revocado si: la clave privada fue comprometida, el titular ya no tiene derecho a usarlo, o los datos del certificado cambiaron. Los navegadores y sistemas consultan las CRLs (o usan OCSP) para verificar que un certificado no ha sido revocado.
>
> **Por qué no las otras:** A confunde CRL con cipher suites de TLS. C describe una ACL (Access Control List) por MAC. D no existe como concepto estándar.

---

### OpenSSL

### 36. ¿Cómo se deriva una clave de cifrado en OpenSSL a partir de la contraseña?

- A) Con un cifrador asimétrico
- B) Con un cifrador simétrico de flujo
- C) Con un cifrador simétrico de bloque
- D) Ninguna de las respuestas indicadas es correcta

> **Respuesta: D**
>
> **Explicación:** OpenSSL **NO deriva claves directamente con un cifrador**. La derivación de claves a partir de contraseñas se realiza mediante una **función de derivación de clave (KDF)** como PBKDF2, que itera una función de resumen (hash) sobre la contraseña + sal. Por tanto, ninguna de las opciones A-C es correcta. Esta pregunta es complementaria de la siguiente (37), donde sí se menciona la opción correcta: mediante función de resumen.
>
> **Por qué no las otras:** A, B y C son incorrectas porque no se usa un cifrador (ni asimétrico, ni de flujo, ni de bloque) para derivar la clave — se usa una función hash iterada.

---

### 37. ¿Cómo se deriva una clave de cifrado en OpenSSL a partir de la contraseña?

- A) Mediante una función de resumen
- B) Mediante un cifrador de bloque
- C) Mediante un cifrador de flujo
- D) Mediante una secuencia pseudo aleatoria

> **Respuesta: A**
>
> **Explicación:** La derivación se realiza mediante una **función de resumen (hash)** aplicada iterativamente: `hash(hash(hash(contraseña + sal)))`. OpenSSL típicamente usa SHA-256 dentro de PBKDF2. La sal asegura que dos usuarios con la misma contraseña obtengan claves diferentes, y la iteración (miles de rondas) ralentiza ataques de fuerza bruta.
>
> **Por qué no las otras:** B y C son incorrectas — no se usa un cifrador sino un hash. D no es el mecanismo principal (aunque el resultado final es una secuencia derivada, el método es mediante función de resumen).

---

### 38. Si ciframos un documento utilizando OpenSSL con clave y vector de inicialización con el algoritmo RC4, ¿cómo será el tamaño del documento cifrado en relación con el original?

- A) 16 bytes mayor, más el padding hasta múltiplo de 32 bytes
- B) 16 bytes mayor
- C) 16 bytes mayor, más el padding hasta múltiplo de 16 bytes
- D) Idéntico

> **Respuesta: D**
>
> **Explicación:** **RC4 es un cifrador de FLUJO**. Los cifradores de flujo cifran byte a byte (o bit a bit) mediante XOR con un flujo de clave pseudoaleatorio. Por tanto, el tamaño del texto cifrado es **IDÉNTICO** al tamaño del texto original — no necesitan padding ni añaden cabeceras.
>
> **Por qué no las otras:** A, B y C añaden bytes o padding, lo cual es característico de los cifradores de BLOQUE. RC4 no es un cifrador de bloque, es de flujo, y por tanto el tamaño no cambia.

---

### 39. Si ciframos un documento utilizando OpenSSL con el algoritmo AES-256 y contraseña, ¿cómo será el tamaño del documento en relación con el original?

- A) 16 bytes mayor, más el padding hasta múltiplo de 32 bytes
- B) Idéntico
- C) 16 bytes mayor
- D) 16 bytes mayor, más el padding hasta múltiplo de 16 bytes

> **Respuesta: D**
>
> **Explicación:** AES es un cifrador de **BLOQUE** (tamaño de bloque = 128 bits = **16 bytes**). Al cifrar con contraseña, OpenSSL añade: (1) cabecera "Salted__" de **16 bytes** (8 de texto mágico + 8 de salt aleatorio), (2) **padding** para que los datos alcancen un múltiplo del tamaño de bloque (16 bytes). Por tanto: tamaño_final = tamaño_original + 16 (cabecera) + padding hasta múltiplo de 16.
>
> **Por qué no las otras:** B es falso para cifradores de bloque. A menciona "múltiplo de 32" cuando el bloque de AES es 16 bytes. C ignora el padding necesario para completar el bloque.

---

### 40. ¿Cuál es el tamaño de bloque del cifrador AES?

- A) 256 bits
- B) 194 bits
- C) 64 bits
- D) 128 bits

> **Respuesta: D**
>
> **Explicación:** El tamaño de bloque de AES es **SIEMPRE 128 bits (16 bytes)**, independientemente del tamaño de clave. AES soporta claves de 128, 192 o 256 bits (de ahí AES-128, AES-192, AES-256), pero el bloque siempre es de 128 bits. Esta es una confusión frecuente: AES-256 NO significa bloques de 256 bits, sino clave de 256 bits con bloques de 128 bits.
>
> **Por qué no las otras:** A confunde tamaño de clave (256) con tamaño de bloque (128). B es incorrecto. C (64 bits) era el tamaño de bloque de DES, no de AES.

---

### Modos de operación

### 41. ¿Qué modo de operación transforma un cifrador de bloque en un cifrador de flujo?

- A) OFB
- B) CBC
- C) PCBC
- D) ECB

> **Respuesta: A**
>
> **Explicación:** **OFB (Output Feedback)** transforma un cifrador de bloque en un cifrador de flujo. Funciona generando un flujo continuo de clave (keystream) a partir de un IV y la clave, y luego aplica XOR con el texto claro. Similar a cómo funciona RC4 pero usando un cifrador de bloque como generador. También CTR (Counter) y CFB (Cipher Feedback) tienen esta propiedad, pero en esta pregunta OFB es la opción correcta.
>
> **Por qué no las otras:** B (CBC), C (PCBC) y D (ECB) son modos que operan bloque a bloque, no generan un flujo independiente del texto claro.

---

### 42. ¿Cuál de estos modos de operación transforma un cifrador de bloque en un cifrador de flujo?

- A) PCBC
- B) CBC
- C) CTR
- D) ECB

> **Respuesta: C**
>
> **Explicación:** **CTR (Counter)** transforma un cifrador de bloque en un cifrador de flujo. Funciona cifrando un contador que se incrementa para cada bloque, generando un keystream que se XOR-ea con el texto claro. A diferencia de OFB, CTR permite acceso aleatorio (puedes cifrar/descifrar cualquier bloque sin procesar los anteriores) y es paralelizable. Es el modo preferido en TLS 1.3 (como AES-GCM).
>
> **Por qué no las otras:** A, B y D no transforman el cifrador de bloque en flujo — siguen siendo modos de bloque.

---

### 43. ¿Cuáles de estos modos de operación necesitan Vector de Inicialización (IV)?

- A) CBC, PCBC y OFB
- B) CBC, OFB y ECB
- C) PCBC, OFB y ECB
- D) CBC, PCBC y ECB

> **Respuesta: A**
>
> **Explicación:** Necesitan IV: **CBC, PCBC, OFB, CFB y CTR**. **ECB NO** necesita IV (y precisamente por eso es peligroso — bloques idénticos de texto claro producen bloques idénticos de texto cifrado). El IV garantiza que dos mensajes idénticos cifrados con la misma clave produzcan textos cifrados diferentes.
>
> **Por qué no las otras:** B, C y D incluyen ECB que no necesita IV. La clave está en recordar que ECB es el único modo común que no usa IV.

---

### 44. ¿Qué modo de operación es especialmente peligroso en los sistemas de cifrado simétrico?

- A) PCBC (Propagating Cypher Block Chaining)
- B) OFB (Output Feedback)
- C) CBC (Cipher Block Chaining)
- D) ECB (Electronic Codebook)

> **Respuesta: D**
>
> **Explicación:** **ECB es PELIGROSO** porque bloques idénticos de texto claro producen bloques idénticos de texto cifrado. Esto revela patrones del documento original. El ejemplo clásico: una imagen bitmap cifrada con ECB sigue siendo reconocible porque los patrones de color se preservan. NUNCA usar ECB para datos con patrones repetitivos.
>
> **Por qué no las otras:** A, B y C son modos seguros (cuando se usan correctamente con IV adecuado). PCBC añade propagación de errores (un error afecta a todo el resto), OFB y CBC son seguros con IV aleatorio.

---

### 45. ¿Cuál de estos es un cifrador de flujo?

- A) IDEA
- B) AES
- C) RC2
- D) RC4

> **Respuesta: D**
>
> **Explicación:** **RC4 (Rivest Cipher 4)** es un cifrador de **FLUJO**. Genera un keystream pseudoaleatorio que se XOR-ea byte a byte con el texto claro. Fue ampliamente usado en WEP (WiFi antiguo) y SSL/TLS hasta que se descubrieron vulnerabilidades. Hoy está obsoleto y TLS 1.3 lo ha eliminado.
>
> **Por qué no las otras:** A (IDEA), B (AES) y C (RC2) son todos cifradores de **BLOQUE**.

---

### 46. ¿Qué aplicación principal tienen los algoritmos probabilísticos en criptografía?

- A) Pruebas de aleatoriedad criptográfica
- B) Pruebas de entropía condicionada
- C) Pruebas de conocimiento cero
- D) Pruebas de primalidad

> **Respuesta: D**
>
> **Explicación:** Los algoritmos probabilísticos en criptografía se usan principalmente para **pruebas de primalidad** — determinar si un número grande es primo. RSA, Diffie-Hellman y ElGamal necesitan números primos enormes. Tests como Miller-Rabin son probabilísticos: determinan si un número es "probablemente primo" con una certeza muy alta (error < 2^(-128)), mucho más rápidos que tests deterministas.
>
> **Por qué no las otras:** A (aleatoriedad) se evalúa con baterías de tests estadísticos (NIST SP 800-22), no son la aplicación principal de algoritmos probabilísticos. B y C son conceptos distintos.

---

### 47. ¿Cuál de estos no es un algoritmo de resumen?

- A) Whirlpool
- B) SHA-3
- C) MD5
- D) Camellia

> **Respuesta: D**
>
> **Explicación:** **Camellia** es un **cifrador de bloque** (como AES), NO un algoritmo de resumen. Fue desarrollado en Japón por NTT y Mitsubishi, y está aprobado por ISO/IEC. Es una alternativa a AES, pero no tiene nada que ver con funciones hash.
>
> **Por qué no las otras:** A (Whirlpool) es un algoritmo de resumen (hash) de 512 bits. B (SHA-3) es el estándar de hash más reciente del NIST, basado en Keccak. C (MD5) es una función hash antigua (ya rota, no recomendada).

---

### Otros

### 48. Las funciones HMAC aseguran:

- A) La autenticación y la confidencialidad
- B) La integridad y el no repudio
- C) La integridad y la autenticación
- D) La autenticación y el no repudio

> **Respuesta: C**
>
> **Explicación:** **HMAC (Hash-based Message Authentication Code)** garantiza dos cosas: **INTEGRIDAD** (el mensaje no ha sido alterado — si cambia un bit, el HMAC cambia completamente) y **AUTENTICACIÓN** (el mensaje proviene de quien dice — solo quien conoce la clave secreta puede generar el HMAC correcto). Se calcula como `hash((clave ⊕ pad1) || hash((clave ⊕ pad2) || mensaje))`. Se usa en TLS, JWT, APIs, etc.
>
> **Por qué no las otras:** A menciona confidencialidad — HMAC no cifra, no oculta el mensaje. B y D mencionan no repudio — HMAC usa clave simétrica compartida, ambas partes pueden generar el HMAC, por tanto no hay no repudio (cualquiera de los dos podría haber generado el mensaje). El no repudio requiere firma digital asimétrica.

---

### 49. En un criptosistema seguro de Shannon, si hablamos de tamaños:

- A) El espacio de mensajes ha de ser menor o igual que el espacio de claves
- B) El espacio de mensajes y el de claves no tienen relación alguna
- C) El espacio de mensajes ha de ser mayor o igual que el espacio de claves
- D) El espacio de mensajes ha de ser igual que el espacio de claves

> **Respuesta: A**
>
> **Explicación:** Shannon demostró que para tener **secreto perfecto** (perfect secrecy), el espacio de claves debe ser **≥** al espacio de mensajes. En otras palabras: |K| ≥ |M|. El ejemplo clásico es el One-Time Pad (libreta de un solo uso): la clave es tan larga como el mensaje y es perfectamente secreto. Si el espacio de claves es menor, hay información que se filtra (el cifrado no puede ser perfecto).
>
> **Por qué no las otras:** B contradice directamente a Shannon. C y D son condiciones incorrectas — el espacio de claves debe ser al menos tan grande como el de mensajes.

---

### 50. La sal criptográfica se utiliza:

- A) con algoritmos de resumen, para evitar ataques de cumpleaños
- B) con algoritmos de cifrado simétrico, para evitar ataques de cumpleaños
- C) con algoritmos de resumen, para evitar ataques de diccionario
- D) con algoritmos de cifrado simétrico, para evitar ataques de diccionario

> **Respuesta: C**
>
> **Explicación:** La **sal criptográfica** es un valor aleatorio que se añade a la contraseña antes de calcular su hash: `hash(contraseña + sal)`. Su propósito es evitar **ataques de diccionario/rainbow tables**: sin sal, dos usuarios con la misma contraseña tendrían el mismo hash. Con sal única por usuario, aunque tengan la misma contraseña, los hashes son diferentes. También fuerza a que un atacante tenga que generar una rainbow table por cada sal, haciendo el ataque computacionalmente inviable.
>
> **Por qué no las otras:** A: la sal NO evita ataques de cumpleaños (colisiones de hash) — para eso se aumenta el tamaño del hash. B y D: la sal se usa con funciones hash, no con cifrado simétrico.

---

### 51. El protocolo https de Web segura

- A) Emplea el sistema PGP
- B) Requiere el intercambio de contraseñas
- C) No precisa el empleo de certificados digitales
- D) Ninguna de las anteriores es cierta

> **Respuesta: D**
>
> **Explicación:** HTTPS = HTTP sobre **TLS/SSL**. NO emplea PGP (PGP es para correo/ficheros). NO requiere intercambio de contraseñas (la autenticación se hace con certificados y negociación TLS). SÍ precisa certificados digitales (al menos del servidor, X.509, en un sistema PKI vertical). Por tanto, todas las afirmaciones A, B y C son falsas.
>
> **Por qué no las otras:** A: PGP y TLS son sistemas distintos. B: TLS puede funcionar con certificados del cliente sin contraseñas. C: HTTPS requiere certificados (gratuitos como Let's Encrypt o de pago).

---

### 52. El protocolo S-HTTP de Web segura se basa:

- A) En un sistema horizontal, ya que utiliza certificados digitales
- B) En un sistema vertical, ya que no utiliza certificados digitales
- C) En un sistema horizontal, ya que no utiliza certificados digitales
- D) En un sistema vertical, ya que utiliza certificados digitales

> **Respuesta: D**
>
> **Explicación:** **S-HTTP (Secure HTTP)** es un protocolo alternativo a HTTPS que también proporciona seguridad web. Se basa en un sistema **VERTICAL** porque utiliza **certificados digitales** (PKI con Autoridades de Certificación). La clave es: certificados digitales → sistema vertical.
>
> **Por qué no las otras:** A y C son incorrectas porque lo clasifican como horizontal — el uso de certificados implica sistema vertical. B contradice que los certificados se usen en sistema vertical.

---

## UA 3. AMENAZAS A LOS SISTEMAS DE INFORMACIÓN

📖 _Referencia completa:_ [03_amenazas-sistemas.md](03_amenazas-sistemas.md)

---

### 53. Algunos de los efectos más habituales de un ataque son:

- A) Destrucción de la información
- B) Pérdida de disponibilidad de los servicios
- C) Daños de la propiedad
- D) Todas las respuestas son correctas

> **Respuesta: D**
>
> **Explicación:** Los ataques pueden tener múltiples efectos: destrucción de información (ransomware que cifra/borra datos), pérdida de disponibilidad (ataque DDoS que tumba un servicio), daños a la propiedad (Stuxnet destruyó centrifugadoras físicas en Irán). **Todos** son efectos reales de ciberataques.
>
> **Por qué no las otras:** Ninguna opción por sí sola cubre todos los efectos posibles — los ataques modernos pueden causar todos estos daños simultáneamente.

---

### 54. ¿Qué es una COOKIE?

- A) Un fragmento de código publicitario que se descarga de algunas páginas web
- B) Un fragmento de código malicioso que se descarga de algunas páginas web
- C) Una página web almacenada en la caché del navegador
- D) Un fragmento de información que se almacena en el disco duro del visitante de una página web, a petición del servidor que aloja la página web

> **Respuesta: D**
>
> **Explicación:** Una cookie es un pequeño fragmento de información (texto) que un servidor web pide al navegador que almacene en el equipo del usuario. Se usa para mantener sesiones (login), preferencias (idioma), carritos de compra, etc. No es código ejecutable — es solo texto. Las cookies en sí no son maliciosas, aunque pueden usarse para tracking (cookies de terceros).
>
> **Por qué no las otras:** A y B la describen como "código" — las cookies no son código ejecutable, son datos. C confunde cookie con caché — la caché almacena páginas completas (HTML, imágenes).

---

### 55. ¿Qué se considera el activo más importante de las organizaciones?

- A) Sus beneficios
- B) Su seguridad
- C) Sus empleados
- D) La información

> **Respuesta: D**
>
> **Explicación:** La **INFORMACIÓN** es el activo más importante. Sin información, no se pueden tomar decisiones, no hay negocio. Los beneficios son consecuencia de usar bien la información. La seguridad es un medio para protegerla. Los empleados son importantes pero la información trasciende a personas individuales. Por eso la Seguridad de la Información como disciplina pone el foco en proteger este activo.

---

### 56. La persona que compromete la seguridad de un sistema informático haciendo uso de sus conocimientos técnicos, pero sin la intención de cometer daños, se llama:

- A) hacker
- B) cracker
- C) lacker
- D) tracker

> **Respuesta: A**
>
> **Explicación:** La distinción clásica: **Hacker** = persona con altos conocimientos técnicos que explora sistemas por curiosidad/desafío intelectual, **SIN intención maliciosa**. **Cracker** = mismo nivel técnico pero **CON intención de dañar** u obtener beneficio ilegal. Esta distinción es importante en el temario.
>
> **Por qué no las otras:** B (cracker) tiene intención de dañar, lo contrario a lo que dice el enunciado. C (lacker) y D (tracker) no son términos estándar de la clasificación de atacantes.

---

### 57. Un ataque de denegación de servicio distribuido se caracteriza porque:

- A) el intruso deniega el servicio distribuyendo contraseñas por la Red
- B) se emplea a un conjunto de máquinas para saturar al sistema víctima
- C) se distribuye el trabajo entre varios hackers
- D) todas las anteriores son ciertas

> **Respuesta: B**
>
> **Explicación:** Un **DDoS (Distributed Denial of Service)** se caracteriza por usar **múltiples máquinas** (típicamente una botnet — miles de dispositivos infectados) para **saturar** al sistema víctima con tráfico masivo, impidiendo que usuarios legítimos accedan al servicio. Ejemplo: el ataque a Dyn DNS en 2016 usando la botnet Mirai tiró Twitter, Netflix, Reddit, etc.
>
> **Por qué no las otras:** A no es DDoS — distribuir contraseñas no causa denegación de servicio. C no es la característica definitoria — lo relevante es la saturación desde múltiples fuentes. D es incorrecta.

---

### 58. Una diferencia entre un gusano y un virus es que

- A) el virus es un software malicioso y el gusano no lo es
- B) son términos sinónimos, se refieren al mismo tipo de software
- C) el gusano se propaga automáticamente, mientras que el virus necesita intervención humana
- D) el gusano puede ser un troyano y el virus no

> **Respuesta: C**
>
> **Explicación:** La diferencia fundamental es el mecanismo de propagación: el **gusano (worm)** se propaga **automáticamente** a través de la red sin intervención del usuario (ej: Stuxnet, Conficker, Blaster). El **virus** necesita **intervención humana** para propagarse (abrir un adjunto, ejecutar un programa, insertar un USB). Ambos son malware.
>
> **Por qué no las otras:** A es falsa — ambos son software malicioso. B es falsa — no son sinónimos. D no es una diferencia definitoria — un troyano es otro tipo de malware, y tanto virus como gusanos pueden combinarse con troyanos.

---

### 59. La intoxicación del DNS a fin de dirigir un equipo a una web maliciosa se denomina

- A) spoofing
- B) phising
- C) pharming
- D) rootkit

> **Respuesta: C**
>
> **Explicación:** **Pharming** es el envenenamiento/intoxicación del DNS para redirigir a los usuarios a sitios web falsos sin que lo sepan. Puede realizarse modificando la caché DNS del servidor (DNS cache poisoning) o el archivo HOSTS del equipo local. A diferencia del phishing (que usa correos señuelo), el pharming no requiere que el usuario pique un enlace — simplemente escribe la URL correcta y es redirigido.
>
> **Por qué no las otras:** A (spoofing) es suplantación genérica, no específicamente DNS. B (phishing) usa ingeniería social, no envenenamiento DNS. D (rootkit) es software que oculta su presencia en el sistema operativo.

---

### 60. ¿Cómo se evita la inyección de SQL?

- A) Filtrando las URLs de salida de una aplicación web
- B) Filtrando todas las entradas a una aplicación web
- C) Filtrando los correos electrónicos para evitar URLs maliciosas
- D) Utilizando una buena suite antivirus

> **Respuesta: B**
>
> **Explicación:** La inyección SQL se evita **filtrando y validando todas las entradas** del usuario en la aplicación web (sanitización de inputs). La técnica correcta es usar **consultas parametrizadas/prepared statements**: en lugar de concatenar strings del usuario en la query SQL, se usan placeholders que el motor de BD trata como datos, no como código. Ejemplo en Java: `PreparedStatement ps = conn.prepareStatement("SELECT * FROM users WHERE name = ?"); ps.setString(1, userInput);`
>
> **Por qué no las otras:** A filtra salidas, no entradas (la inyección entra, no sale). C y D son completamente ineficaces contra inyección SQL — no es un problema de correo ni de virus, es un fallo de programación.

---

### 61. ¿A qué se conoce como ROOTKIT?

- A) A un software malicioso capaz de sustituir determinados componentes de un Sistema Operativo
- B) A un tipo de virus
- C) A un gusano
- D) A un troyano

> **Respuesta: A**
>
> **Explicación:** Un **rootkit** es un software malicioso diseñado para **sustituir componentes del SO** (librerías, binarios, módulos del kernel) y así ocultar su presencia (y la de otro malware). El nombre viene de "root" (superusuario) + "kit" (conjunto de herramientas). Una vez instalado, el rootkit puede ocultar procesos, archivos, conexiones de red... es extremadamente difícil de detectar.
>
> **Por qué no las otras:** B, C y D son clasificaciones por mecanismo de propagación o entrada. Un rootkit no es un mecanismo de propagación sino un método de ocultación. Un rootkit puede ser instalado POR un virus, gusano o troyano, pero no ES ninguno de ellos.

---

### 62. ¿De qué manera puede llegar un TROYANO hasta un sistema informático?

- A) Descargado automáticamente por otro programa malicioso
- B) Como adjunto en un mensaje de correo electrónico
- C) Descargado al visitar una página web maliciosa
- D) Todas las respuestas son correctas

> **Respuesta: D**
>
> **Explicación:** Un troyano (caballo de Troya) es malware que se camufla como software legítimo. Puede llegar por **múltiples vías**: descargado por otro malware (dropper/downloader), como adjunto en un correo electrónico (factura falsa, currículum), al visitar una web maliciosa (drive-by download), a través de descargas P2P, en apps falsas, etc. **Todas las opciones son vectores reales de entrada.**
>
> **Por qué no las otras:** Cada opción individual es correcta pero incompleta — los troyanos usan todos estos métodos.

---

## UA 4. MECANISMOS DE DEFENSA

📖 _Referencia completa:_ [04_mecanismos-defensa.md](04_mecanismos-defensa.md)

---

### 63. ¿Cómo se denomina a los centros con la capacidad técnica y la estructura más adecuada para la lucha contra las ciberamenazas?

- A) Centro de Respuesta al Usuario (CRU)
- B) Centro de Atención a Usuarios (CAU)
- C) Centro de Atención a la Seguridad (CAS)
- D) Centro de Respuesta ante Incidentes (CERT)

> **Respuesta: D**
>
> **Explicación:** Los **CERT (Computer Emergency Response Team)** o **CSIRT (Computer Security Incident Response Team)** son los centros especializados en responder a incidentes de ciberseguridad. Coordinan la respuesta, analizan amenazas, emiten alertas tempranas y ayudan en la recuperación. En España: CCN-CERT, INCIBE-CERT, ESPDEF-CERT, IRIS-CERT.
>
> **Por qué no las otras:** CRU, CAU y CAS no son términos estándar en ciberseguridad. CAU es típicamente un centro de atención a usuarios para soporte TI general, no especializado en ciberamenazas.

---

### 64. ¿Qué política de la organización se ve especialmente afectada por la creciente amenaza de los criptovirus?

- A) Política de copias de seguridad
- B) Política de uso de la nube
- C) Política de actualizaciones
- D) Política de cuentas de usuario y contraseñas

> **Respuesta: A**
>
> **Explicación:** Los **criptovirus (ransomware)** cifran los datos de la víctima y piden un rescate. La principal defensa es tener **copias de seguridad** (backups) offline/offsite que el ransomware no pueda alcanzar. Si las copias están en línea (conectadas al sistema), también serán cifradas. Una buena política de copias de seguridad (3-2-1: 3 copias, 2 medios, 1 offsite) es la mejor defensa contra ransomware.
>
> **Por qué no las otras:** B, C y D son políticas importantes pero no tan directamente afectadas. Las actualizaciones (C) previenen la infección inicial, pero una vez infectado, la copia de seguridad es lo que permite recuperarse sin pagar.

---

### 65. ¿Cómo se evita la inyección de SQL?

- A) En el firewall de la organización, filtrando las URL maliciosas en los datos de entrada
- B) En el código de la aplicación web, filtrando todo el tráfico de entrada
- C) En el firewall de la organización, filtrando todo el tráfico de entrada
- D) En el código de la aplicación web, filtrando las URL maliciosas en los datos de entrada

> **Respuesta: B**
>
> **Explicación:** La inyección SQL se evita en el **código de la aplicación web**, filtrando/sanitizando **todo el tráfico de entrada**. La defensa debe estar en la capa de aplicación, no en la de red. Las técnicas correctas: consultas parametrizadas (prepared statements), stored procedures, validación de entrada (whitelist), escapado de caracteres especiales, y ORMs que abstraen las queries.
>
> **Por qué no las otras:** A y C sitúan la defensa en el firewall (capa de red) — un firewall tradicional no puede detectar inyección SQL porque opera a nivel de paquetes, no entiende consultas SQL. D limita a "filtrar URLs maliciosas" — pero la inyección SQL puede venir por cualquier campo (formularios, cabeceras HTTP, cookies...), no solo URLs.

---

### 66. Una medida básica de seguridad en el uso de redes WIFI es:

- A) Activar la lista de control de acceso (ACL) por MAC
- B) Desactivar el protocolo WPS
- C) Ocultar el SSID
- D) Utilizar protocolos de cifrado seguros, como el WEP

> **Respuesta: B**
>
> **Explicación:** **Desactivar WPS (WiFi Protected Setup)** es una medida básica y crítica. WPS fue diseñado para facilitar la conexión (botón o PIN de 8 dígitos), pero tiene una vulnerabilidad grave: el PIN puede ser forzado por fuerza bruta en horas. Las transparencias lo destacan: *"¡¡¡Protocolo WPS peligrosísimo!!!"*.
>
> **Por qué no las otras:** A (ACL por MAC) proporciona seguridad muy débil — las MACs se pueden suplantar (spoofing). C (ocultar SSID) es seguridad por oscuridad — el SSID se transmite en cada paquete y es trivial de descubrir. D es INCORRECTO porque WEP está roto y NO es seguro — usar WPA2 o WPA3.

---

### 67. La letra A en las siglas ADSL representa en castellano la palabra

- A) Automática
- B) Avanzada
- C) Autónoma
- D) Asíncrona

> **Respuesta: D**
>
> **Explicación:** ADSL = **Asymmetric Digital Subscriber Line** = Línea de Abonado Digital **Asimétrica**. "Asíncrona" porque la velocidad de bajada y subida no son iguales (asimétrica).
>
> **Por qué no las otras:** A, B, C no corresponden a las siglas en inglés ni al concepto técnico.

---

### 68. Para cifrar las comunicaciones en una red Wifi, se puede usar el protocolo

- A) WPE
- B) WAP
- C) WPA
- D) ninguno de los anteriores

> **Respuesta: C**
>
> **Explicación:** **WPA (WiFi Protected Access)** y sus versiones WPA2/WPA3 son los protocolos de cifrado para WiFi. WPA2 usa AES-CCMP y es el mínimo recomendable. WPA3 (2018) añade mejoras como SAE (Simultaneous Authentication of Equals) que protege contra ataques de diccionario offline.
>
> **Por qué no las otras:** A (WPE) no existe. B (WAP) es Wireless Application Protocol — un protocolo para contenido móvil antiguo, no para cifrado WiFi.

---

### 69. Una buena práctica en la configuración de un router ADSL doméstico es:

- A) permitir el acceso remoto a la pantalla de configuración
- B) desactivar la utilización de comunicaciones cifradas
- C) entregar todas las conexiones entrantes a una "default workstation" o DMZ
- D) ninguna de las anteriores

> **Respuesta: D**
>
> **Explicación:** **Todas las opciones A, B y C son MALAS prácticas.** Permitir acceso remoto a la configuración (A) abre el router a ataques externos. Desactivar cifrado (B) expone todas las comunicaciones. Poner una "default workstation" o DMZ (C) expone un equipo a todo Internet sin protección. Ninguna es una buena práctica.
>
> **Por qué no las otras:** Las buenas prácticas reales son: cambiar contraseña del router, desactivar acceso remoto, activar firewall, usar WPA2/WPA3, desactivar WPS, cambiar contraseña WiFi por defecto, mantener firmware actualizado.

---

### 70. Para garantizar la integridad de un mensaje de correo electrónico necesitaremos

- A) cifrarlo
- B) firmarlo
- C) cifrarlo y firmarlo
- D) ninguna de las anteriores

> **Respuesta: B**
>
> **Explicación:** La **integridad** (asegurar que el mensaje no ha sido modificado) se garantiza con la **firma digital**. La firma incluye el hash del mensaje cifrado con la clave privada del remitente. El destinatario puede verificar que el mensaje no ha cambiado. Cifrar (A) proporciona confidencialidad pero NO integridad — un atacante podría modificar el texto cifrado (aunque no sepa qué dice). Cifrar Y firmar (C) da ambas propiedades pero la pregunta pide específicamente integridad.
>
> **Por qué no las otras:** A proporciona confidencialidad, no integridad. C es correcto pero va más allá de lo que pide la pregunta (integridad). D es incorrecta.

---

### 71. Una red privada virtual (VPN)

- A) es un mecanismo de virtualización de redes
- B) es un sistema de comunicaciones virtuales
- C) es un sistema de interconexión o de acceso a redes privadas
- D) ninguna de las anteriores

> **Respuesta: C**
>
> **Explicación:** Una VPN es un **sistema de interconexión o acceso a redes privadas** a través de redes públicas (Internet) mediante túneles cifrados. Permite que un usuario acceda a la red corporativa como si estuviera físicamente conectado, o interconectar dos sedes. Usa protocolos como IPSec, OpenVPN, WireGuard.
>
> **Por qué no las otras:** A y B son definiciones vagas e imprecisas. "Virtualización de redes" es otra cosa (VLANs, SDN). "Sistema de comunicaciones virtuales" no captura el propósito de acceso a redes privadas.

---

### 72. ¿Qué protocolo se considera más seguro en redes WIFI?

- A) WEP
- B) WEP2
- C) WPA2
- D) WPA

> **Respuesta: C**
>
> **Explicación:** El orden de seguridad: WEP (roto, 1999) < WPA (TKIP/RC4, 2003, vulnerable) < **WPA2** (AES-CCMP, 2004, seguro) < WPA3 (SAE, 2018, el más seguro pero no es opción aquí). Entre las opciones dadas, **WPA2 es la más segura**.
>
> **Por qué no las otras:** A (WEP) es extremadamente inseguro — se puede romper en minutos. B (WEP2) no existe como estándar real. D (WPA) es mejor que WEP pero vulnerable a ciertos ataques (TKIP). WPA2 usa AES que es mucho más robusto.

---

### 73. ¿Cuál de estas direcciones IP es pública?

- A) 11.1.1.1
- B) 10.1.1.1
- C) 172.26.0.1
- D) 192.168.1.1

> **Respuesta: A**
>
> **Explicación:** Los rangos de IPs **privadas** (RFC 1918) son:
> - **10.0.0.0/8** → 10.x.x.x
> - **172.16.0.0/12** → 172.16.x.x a 172.31.x.x
> - **192.168.0.0/16** → 192.168.x.x
>
> **11.1.1.1** no está en ningún rango privado → es **pública**.
>
> **Por qué no las otras:** B (10.1.1.1) está en 10.0.0.0/8. C (172.26.0.1) está en 172.16.0.0/12. D (192.168.1.1) está en 192.168.0.0/16.

---

### 74. ¿A qué se denomina DMZ?

- A) A la intranet de una organización
- B) A la parte de la red interna de una organización donde habitualmente se conectan los PCs de usuario
- C) A la parte de Internet donde se colocan los servidores web
- D) A la parte de la red interna de una organización en la que se colocan los servidores que ofrecen servicios al exterior de la empresa

> **Respuesta: D**
>
> **Explicación:** La **DMZ (Zona Desmilitarizada)** es una subred dentro de la red de la organización donde se colocan los **servidores que ofrecen servicios al exterior** (servidor web, correo, DNS). Está separada de la intranet por firewalls: si un servidor en la DMZ es comprometido, el atacante no tiene acceso directo a la red interna.
>
> **Por qué no las otras:** A es la intranet (red interna segura). B son los puestos de usuario (LAN interna). C sitúa erróneamente la DMZ en Internet. La DMZ está en la red de la organización, no en Internet.

---

## UA 5. INSTRUMENTOS PARA LA GESTIÓN DE LA SEGURIDAD

📖 _Referencia completa:_ [05_gestion-seguridad.md](05_gestion-seguridad.md)

---

### 75. ¿Qué es ITIL?

- A) Una norma europea de obligado cumplimiento en Tecnologías de la Información
- B) Un conjunto de estándares en Tecnologías de la Información
- C) Una biblioteca de buenas prácticas en la gestión de las Tecnologías de la Información
- D) Ninguna de las respuestas es correcta

> **Respuesta: C**
>
> **Explicación:** **ITIL (Information Technology Infrastructure Library)** es una **biblioteca (library) de buenas prácticas** — un compendio de recomendaciones basadas en la experiencia de miles de organizaciones. NO es una norma de obligado cumplimiento, ni un estándar ISO. Su origen está en el gobierno del Reino Unido en los años 80.
>
> **Por qué no las otras:** A: ITIL no es de obligado cumplimiento — es voluntario. B: ITIL no es un estándar (los estándares son ISO, IEEE...). D es incorrecta porque C es correcta.

---

### 76. ITIL es...

- A) una metodología de trabajo
- B) una recopilación de buenas prácticas en la gestión de servicios
- C) un manual de acciones a realizar para hacer un análisis de riesgos
- D) una norma ISO de la familia ISO 27.000

> **Respuesta: B**
>
> **Explicación:** ITIL es específicamente una **recopilación de buenas prácticas en la gestión de SERVICIOS** de TI. La diferencia sutil con la pregunta 75 es que aquí se especifica "gestión de servicios" en vez de "gestión de TI" genérica.
>
> **Por qué no las otras:** A: ITIL no es una metodología (aunque incluye procesos, es más amplio). C: ITIL cubre mucho más que análisis de riesgos. D: ITIL no es una norma ISO (aunque existe ISO 20000 que se alinea con ITIL).

---

### 77. El objetivo de ITIL v3 es:

- A) Mejorar las comunicaciones de la organización
- B) Alinear las Tecnologías de la Información con el negocio
- C) Separar las funciones de las Tecnologías de la Información
- D) Integrar las Tecnologías de la Información en el negocio

> **Respuesta: B**
>
> **Explicación:** El objetivo principal de ITIL v3 es **alinear las TI con el negocio**. Según las transparencias: *"ITIL V2: ALINEAR la tecnología con el Negocio; ITIL V3: INTEGRAR la tecnología en el Negocio."* Sin embargo, en este examen la respuesta correcta es B (alinear). Nota: aunque ITIL v3 habla de INTEGRAR, en el contexto del examen "alinear" es la respuesta correcta.
>
> **Por qué no las otras:** C es lo opuesto al objetivo de ITIL. A es un beneficio secundario, no el objetivo principal. D sería más propio de ITIL v3 avanzado/v4 pero no es la opción marcada en el examen.

---

### 78. ¿Qué etapas conforman el Ciclo de Vida del Servicio?

- A) Transición del servicio, Publicación, Difusión y Mejora continua
- B) Estrategia del Servicio, Diseño del Servicio, Transición del Servicio, Operación del Servicio y Mejora Continua
- C) Plan, Do, Check, Act
- D) Estrategia del Servicio, Implantación del Servicio y Mantenimiento del Servicio

> **Respuesta: B**
>
> **Explicación:** El Ciclo de Vida del Servicio de ITIL v3 tiene **5 etapas**: (1) Estrategia del Servicio, (2) Diseño del Servicio, (3) Transición del Servicio, (4) Operación del Servicio, (5) Mejora Continua del Servicio. Es un ciclo iterativo.
>
> **Por qué no las otras:** A incluye términos incorrectos (Publicación, Difusión). C es el ciclo PDCA de Deming (ISO 27001), no el ciclo de vida de ITIL. D solo menciona 3 etapas y no son las correctas.

---

### 79. ¿Qué opciones existen para tratar los riesgos?

- A) Mitigar, asumir, transferir o eliminar el riesgo
- B) Ninguna de las respuestas es correcta
- C) Mitigar, asumir y eliminar el riesgo
- D) Transferir a un tercero y eliminar el riesgo

> **Respuesta: A**
>
> **Explicación:** Las **4 estrategias** para tratar riesgos son: (1) **Mitigar** — reducir probabilidad o impacto con controles; (2) **Asumir** — aceptar el riesgo (cuando el coste de mitigación > pérdida potencial); (3) **Transferir** — pasar el riesgo a un tercero (ej: seguro, outsourcing); (4) **Eliminar** — dejar de hacer la actividad que genera el riesgo.
>
> **Por qué no las otras:** C omite la opción de transferir. D solo contempla dos opciones. La gestión de riesgos siempre incluye las 4 posibilidades.

---

### 80. ¿En qué consiste un ANÁLISIS DE RIESGOS?

- A) En identificar los riesgos a los que están expuestos los activos de la organización
- B) En identificar los problemas de seguridad que evidencian vulnerabilidades
- C) Las dos respuestas indicadas son correctas
- D) Ninguna de las dos respuestas indicadas es correcta

> **Respuesta: C**
>
> **Explicación:** El análisis de riesgos consiste en **AMBAS** cosas: identificar los riesgos que afectan a los activos (qué puede pasar y a qué activos) e identificar los problemas de seguridad que evidencian vulnerabilidades (dónde están los puntos débiles). Las dos definiciones son complementarias y ambas forman parte del análisis de riesgos.

---

### 81. En el ámbito del análisis de riesgos, se denomina incidente a:

- A) Los hechos que deben evitarse en la organización pues causan un impacto en el negocio
- B) Las averías de los sistemas de Información
- C) Un fallo en el sistema eléctrico
- D) Los hechos que no deben evitarse en la organización pues aportan beneficio al negocio

> **Respuesta: A**
>
> **Explicación:** Un **incidente** es un hecho que **debe evitarse** porque causa un **impacto negativo** en el negocio. Puede ser una brecha de seguridad, una caída del sistema, un robo de datos... La definición clave: hechos con impacto negativo que se quieren prevenir.
>
> **Por qué no las otras:** B y C son ejemplos concretos de incidentes, no la definición general. D es lo contrario: describe un hecho positivo, no un incidente.

---

### 82. Un activo es...

- A) el hardware asociado a los servicios que estamos considerando
- B) una debilidad del sistema que puede ser utilizada de forma accidental o intencionada
- C) un recurso software, hardware, de personal, administrativo, o funcional que es necesario para el funcionamiento del servicio
- D) ninguna de las anteriores

> **Respuesta: C**
>
> **Explicación:** Un **activo** es mucho más que hardware. Incluye: software, hardware, **personal**, recursos administrativos, funcionales... **cualquier recurso necesario para el funcionamiento del servicio** y que posee valor para la organización. Esta definición amplia es clave: el personal y los procesos también son activos.
>
> **Por qué no las otras:** A es demasiado limitada (solo hardware). B define una **vulnerabilidad**, no un activo.

---

### 83. ¿Qué se considera el activo más importante de las organizaciones?

- A) Sus beneficios
- B) Su seguridad
- C) Sus empleados
- D) La información

> **Respuesta: D**
>
> **Explicación:** (Misma que la pregunta 55) La **información** es el activo más importante. Es lo que permite tomar decisiones y operar el negocio.

---

### 84. El IMPACTO es:

- A) Un medible del grado de daño que se ha producido sobre un activo
- B) Ninguna de las respuestas es correcta
- C) Un medible de la importancia de una vulnerabilidad
- D) Un medible sobre el número de activos de una organización

> **Respuesta: A**
>
> **Explicación:** El **impacto** mide el **grado de daño** producido sobre un activo cuando una amenaza se materializa. Se mide en términos de pérdida económica, daño reputacional, tiempo de inactividad, etc. Es un componente del cálculo de riesgo: Riesgo = Impacto × Probabilidad.
>
> **Por qué no las otras:** C confunde impacto con severidad de vulnerabilidad. D no es relevante (el número de activos no es una medida de impacto).

---

### 85. Denominamos RIESGO a:

- A) La probabilidad de que ocurra un fallo de hardware
- B) La probabilidad de que ocurra un evento adverso
- C) Un medible de las posibles amenazas detectadas en una organización
- D) La probabilidad de que ocurra un fallo en el sistema

> **Respuesta: B**
>
> **Explicación:** El **riesgo** es la **probabilidad de que ocurra un evento adverso**, y está compuesto por: probabilidad × impacto. No es solo la probabilidad (también importa el impacto), pero entre las opciones, B es la definición más correcta.
>
> **Por qué no las otras:** A y D limitan el riesgo a fallos de hardware/sistema, cuando el riesgo abarca mucho más (fallos humanos, desastres naturales, ataques). C define parte del análisis pero no el concepto de riesgo en sí.

---

### 86. Definimos el riesgo como:

- A) la probabilidad de que ocurra un evento que puede tener un impacto positivo o negativo en la organización
- B) la probabilidad de que ocurra un evento adverso que supone un impacto negativo en caso de ocurrir
- C) la probabilidad de que una amenaza nunca ocurra
- D) la posibilidad de que un evento adverso no se produzca

> **Respuesta: B**
>
> **Explicación:** El riesgo se define como la probabilidad de que ocurra un **evento adverso** que conlleva un **impacto negativo**. Esta definición es más precisa que la de la pregunta 85 porque incluye explícitamente "impacto negativo en caso de ocurrir". Riesgo = Probabilidad × Impacto negativo.
>
> **Por qué no las otras:** A habla de impacto "positivo o negativo" — en gestión de riesgos de seguridad, solo se consideran impactos negativos (las oportunidades positivas se gestionan aparte). C y D son definiciones absurdas.

---

### 87. Un ATAQUE es:

- A) Una amenaza que proviene de terceros que intencionadamente buscan comprometer la seguridad del sistema
- B) Un error intencionado en los sistemas de información
- C) Una vulnerabilidad que proviene de terceros con la intención de robar la información de la organización
- D) Una negligencia de terceros que compromete la seguridad de los sistemas

> **Respuesta: A**
>
> **Explicación:** Un **ataque** se caracteriza por: (1) proviene de **terceros** (externos o internos), (2) es **intencionado** (no accidental), (3) busca **comprometer la seguridad**. La intencionalidad es la clave que distingue un ataque de un accidente o negligencia.
>
> **Por qué no las otras:** B limita a "error" — un ataque no es un error, es deliberado. C confunde ataque con vulnerabilidad. D habla de negligencia (no intencionada) — un ataque es intencionado.

---

### 88. Una vulnerabilidad es un tipo de

- A) amenaza
- B) incidente
- C) riesgo
- D) debilidad

> **Respuesta: D**
>
> **Explicación:** Una **vulnerabilidad** es un tipo de **debilidad** — una deficiencia del sistema que puede ser explotada (fortuita o intencionadamente) para causar un fallo. La vulnerabilidad es el "agujero"; la amenaza es "lo que puede pasar si se explota"; el riesgo es "probabilidad × impacto de que ocurra".
>
> **Por qué no las otras:** La vulnerabilidad NO es una amenaza (la amenaza es lo que explota la vulnerabilidad). NO es un incidente (el incidente ocurre cuando la amenaza explota la vulnerabilidad). NO es un riesgo (el riesgo es la combinación de amenaza + vulnerabilidad + impacto).

---

### 89. ¿Qué tipos de riesgo existen?

- A) Conocidos y desconocidos
- B) Ninguna de las respuestas es correcta
- C) Mitigables y gestionables
- D) Previstos, imprevistos y mitigables

> **Respuesta: A**
>
> **Explicación:** Según las transparencias, los riesgos se clasifican en: **conocidos** (pueden identificarse y gestionarse con medidas oportunas) y **desconocidos** (situaciones imprevistas que no permiten tomar medidas a priori). Esta clasificación viene de la teoría de riesgos de Donald Rumsfeld ("known unknowns" y "unknown unknowns").
>
> **Por qué no las otras:** C y D no son clasificaciones estándar. "Mitigable" es una acción sobre el riesgo, no un tipo. "Previstos/imprevistos" es similar pero la terminología del curso es "conocidos/desconocidos".

---

### 90. ¿Cuál de los siguientes eventos se puede considerar un "incidente de seguridad"?

- A) la pérdida de suministro eléctrico
- B) el robo de información confidencial
- C) el fallo en un disco de datos
- D) todos los anteriores

> **Respuesta: D**
>
> **Explicación:** **Todos son incidentes de seguridad** porque afectan a la disponibilidad, confidencialidad o integridad. La pérdida de suministro eléctrico afecta a la disponibilidad. El robo de información afecta a la confidencialidad. El fallo de un disco afecta a la disponibilidad e integridad. Un incidente de seguridad es cualquier evento que comprometa alguna dimensión de la seguridad.
>
> **Por qué no las otras:** Ninguna opción individual cubre todos los tipos de incidentes.

---

### 91. ¿En qué consiste la Gestión del Riesgo?

- A) En identificar y desplegar las medidas técnicas y organizativas requeridas para eliminar los riesgos identificados, de forma que se evite totalmente el daño que pueden ocasionar
- B) En subcontratar a una empresa externa la seguridad de la organización
- C) En aplicar determinadas medidas destinadas a mitigar los riesgos detectados
- D) En identificar y desplegar las medidas técnicas y organizativas requeridas para evitar, minimizar o controlar los riesgos identificados, de forma que se elimine o reduzca el daño que pueden ocasionar

> **Respuesta: D**
>
> **Explicación:** La gestión del riesgo es más amplia que simplemente eliminar o mitigar. Incluye **evitar, minimizar o controlar** los riesgos, buscando **eliminar o reducir** el daño. Las 4 estrategias son: mitigar, asumir, transferir, eliminar. La opción D captura esta visión integral.
>
> **Por qué no las otras:** A promete "eliminar los riesgos" y "evitar totalmente el daño" — eso es imposible (la seguridad plena es una utopía). B es solo una opción (transferir), no toda la gestión. C solo habla de mitigar, ignorando las otras estrategias.

---

### 92. ¿Cuáles de las siguientes respuestas son metodologías reconocidas de análisis de riesgos?

- A) Magerit II
- B) Ebios
- C) CRAMM
- D) todas las anteriores

> **Respuesta: D**
>
> **Explicación:** **MAGERIT** (española, CCN/CNI), **EBIOS** (francesa, ANSSI) y **CRAMM** (británica, gobierno UK) son **todas metodologías reconocidas de análisis de riesgos**. Ninguna es falsa.
>
> **Por qué no las otras:** Cada opción individual es correcta pero incompleta.

---

### 93. ¿Cuál de los siguientes eventos se puede considerar un "incidente de seguridad"?

- A) la pérdida de suministro eléctrico
- B) el robo de información confidencial
- C) el fallo en un disco de datos
- D) todos los anteriores

> **Respuesta: D**
>
> **Explicación:** (Repetida de la 90) Todos son incidentes de seguridad.

---

### 94. Entre las posibles metodologías que se pueden utilizar para realizar un análisis de riesgos están:

- A) ITIL, ISO 27.001 y MAGERIT II
- B) CRAMM, EBIOS y MAGERIT II
- C) ITIL v3, CRAMM y MAGERIT II
- D) Ninguna de las respuestas es correcta

> **Respuesta: B**
>
> **Explicación:** **OJO con esta pregunta trampa.** Las metodologías de análisis de riesgos son **CRAMM, EBIOS y MAGERIT**. ITIL NO es una metodología de análisis de riesgos (es de gestión de servicios TI). ISO 27001 NO es una metodología de análisis de riesgos (es un estándar para SGSI, aunque incluye análisis de riesgos como parte del proceso).
>
> **Por qué no las otras:** A y C incluyen ITIL/ISO 27001, que no son metodologías de análisis de riesgos. D es incorrecta porque B es correcta.

---

### 95. ¿Qué es MAGERIT?

- A) Una metodología de análisis de la seguridad propuesta por el CNI
- B) Una metodología de análisis forense desarrollada por las administraciones públicas
- C) Una metodología de análisis y gestión de riesgos enfocada a las Administraciones Públicas
- D) Una metodología de análisis de intrusiones

> **Respuesta: C**
>
> **Explicación:** **MAGERIT** (Metodología de Análisis y Gestión de Riesgos de los Sistemas de Información) es una metodología de **análisis y gestión de riesgos** desarrollada por el Consejo Superior de Administración Electrónica (CSAE) y adoptada por el CCN, **enfocada a las Administraciones Públicas** españolas. Es la metodología de referencia para cumplir con el ENS. Versión actual: MAGERIT III (3 libros: Método, Catálogo de Elementos, Guías Técnicas).
>
> **Por qué no las otras:** A es incorrecta porque MAGERIT no fue "propuesta por el CNI" sino por el CSAE (aunque el CCN la adopta y mantiene). B y D confunden MAGERIT con metodologías forenses o de intrusión.

---

### 96. La auditoría informática consiste en:

- A) Recoger, agrupar y evaluar las evidencias para determinar si un sistema de información realiza de forma eficaz los fines de la organización y utiliza eficientemente los recursos
- B) Recoger, agrupar y evaluar las evidencias para determinar si un sistema de información mantiene la integridad de los datos
- C) Recoger, agrupar y evaluar las evidencias para determinar si un sistema de información protege el activo empresarial
- D) Todas las respuestas son correctas

> **Respuesta: A**
>
> **Explicación:** La definición más completa y precisa de auditoría informática es la opción A: verificar eficacia (cumple los fines) y eficiencia (usa bien los recursos). Según las transparencias, la auditoría es: *"Proceso de recogida, agrupación y evaluación de evidencias que determinan si el sistema de información protege el activo empresarial, mantiene la integridad de los datos, ayuda a realizar los fines de la organización y utiliza adecuadamente los recursos."* La opción A es la más completa.
>
> **Por qué no las otras:** B y C son aspectos parciales. Aunque D podría parecer correcta, la respuesta aceptada en el examen es A como la definición principal.

---

### 97. ¿Cuál de las siguientes tareas NO corresponde a la realización de una auditoría informática?

- A) recoger, agrupar y evaluar evidencias para determinar si un sistema de información protege el activo empresarial
- B) verificar que se mantiene la integridad de los datos
- C) verificar que un sistema realiza de forma eficaz los fines de la organización y utiliza eficientemente los recursos
- D) identificar las amenazas y proponer salvaguardas para proteger a la organización

> **Respuesta: D**
>
> **Explicación:** La auditoría **verifica y evalúa**, pero **NO identifica amenazas ni propone salvaguardas**. Esa tarea (identificar amenazas y proponer salvaguardas) corresponde al **análisis de riesgos**, no a la auditoría. La auditoría comprueba el estado actual; el análisis de riesgos mira hacia adelante y propone mejoras.
>
> **Por qué no las otras:** A, B y C son tareas propias de la auditoría informática.

---

### 98. Algunos de los objetivos de la auditoría informática son:

- A) Las dos respuestas indicadas son correctas
- B) Ninguna de las dos respuestas indicadas es correcta
- C) Eliminar o minimizar la probabilidad de pérdida de información
- D) Verificar el control interno de la función informática

> **Respuesta: A**
>
> **Explicación:** Tanto C (eliminar/minimizar pérdida de información) como D (verificar control interno de la función informática) son objetivos válidos de la auditoría informática. Por tanto, **ambas respuestas son correctas**.

---

### 99. Se consideran tipos de auditoría desde el punto de vista informático:

- A) La auditoría de datos
- B) Todas las respuestas son correctas
- C) La auditoría de las comunicaciones
- D) La auditoría legal de la LOPD

> **Respuesta: B**
>
> **Explicación:** Los tipos de auditoría informática incluyen: auditoría de **datos**, auditoría de **comunicaciones**, auditoría **legal** (LOPD/LOPDyGDD), auditoría de seguridad, auditoría de sistemas, etc. **Todas** las opciones mencionadas son tipos válidos.

---

### 100. ¿De qué forma podemos desarrollar una auditoría?

- A) Auditoría alrededor del ordenador, a través del ordenador y con el ordenador
- B) Auditoría a través de la informática, a través de la seguridad y con el ordenador
- C) Auditoría a través de la seguridad
- D) Ninguna de las anteriores es correcta

> **Respuesta: A**
>
> **Explicación:** Las 3 formas clásicas de auditoría informática son: **alrededor del ordenador** (revisar documentación, procedimientos, controles externos sin examinar el sistema), **a través del ordenador** (analizar el funcionamiento interno del sistema, programas, procesos), y **con el ordenador** (usar herramientas informáticas para realizar la auditoría).
>
> **Por qué no las otras:** B y C usan terminología no estándar. D es incorrecta porque A es correcta.

---

### 101. ¿Qué resultados obtenemos tras la realización de una auditoría informática?

- A) Identificación de las salvaguardas que minimizan los riesgos detectados
- B) Evidencias de los riesgos asociados a los sistemas que dan soporte a la información de la organización
- C) Posibles adquisiciones a realizar para mejorar la infraestructura informática
- D) Ninguna de las respuestas es correcta

> **Respuesta: B**
>
> **Explicación:** El resultado principal de una auditoría es obtener **evidencias de los riesgos** asociados a los sistemas de información. Según las transparencias: *"Resultados: Evidencias de los riesgos asociados a los SSII; Posibles acciones de mejora."* **Nota:** depende de la interpretación — si D se considera excluyente, entonces B; en general se acepta B.
>
> **Por qué no las otras:** A es más propio del análisis de riesgos que de la auditoría (la auditoría identifica problemas, no propone salvaguardas). C es un posible resultado indirecto pero no el principal.

---

### 102. ¿Qué define un Plan Director de Seguridad?

- A) La seguridad de la organización
- B) La estrategia en seguridad física y lógica de la organización
- C) La estrategia de negocio de la organización
- D) La estrategia en seguridad TIC de la organización

> **Respuesta: D**
>
> **Explicación:** Un Plan Director de Seguridad define la **estrategia en seguridad TIC** durante un período de tiempo, alineando todas las áreas de la organización con esta estrategia. Cubre TODOS los dominios: redes, equipos, seguridad física y lógica, controles de acceso, mantenimiento, normativa, etc.
>
> **Por qué no las otras:** A es demasiado genérico. B limita a "física y lógica" — el plan director cubre mucho más (organizativa, normativa, continuidad...). C habla de estrategia de negocio — el plan director cubre seguridad TIC.

---

### 103. Uno de los factores clave para el éxito de un Plan Director de Seguridad es:

- A) Compromiso con los empleados
- B) Ninguna de las respuestas es correcta
- C) Compromiso con los proveedores
- D) Compromiso de la dirección

> **Respuesta: D**
>
> **Explicación:** El factor clave número 1 para el éxito de un Plan Director de Seguridad es el **compromiso de la dirección**. Sin el apoyo de la alta dirección, no habrá recursos, no se asignarán responsabilidades, y el plan fracasará. Es el mismo principio que en la ISO 27001: el compromiso de la dirección es fundamental.
>
> **Por qué no las otras:** A y C son importantes pero secundarios. Sin la dirección, empleados y proveedores no seguirán el plan.

---

### 104. Uno de los objetivos de un Plan Director de Seguridad es:

- A) Aportar confianza sobre los servicios ofrecidos
- B) Ninguna de las respuestas es correcta
- C) Realizar un análisis de riesgos en la organización
- D) Cumplir los requisitos de la LSSIE

> **Respuesta: A**
>
> **Explicación:** Entre los objetivos del Plan Director está **aportar confianza sobre los servicios ofrecidos**, tanto a clientes internos como externos. También incluye: definir objetivos y criterios de seguridad, establecer marco normativo, conocer y planificar costes e inversiones.
>
> **Por qué no las otras:** C: el análisis de riesgos es una herramienta para elaborar el plan, no un objetivo del plan en sí. D: la LSSI-CE es solo una de las normativas a considerar, no el objetivo principal.

---

### 105. Un Plan de Respuesta ante Incidentes implica:

- A) Documentar una relación de actividades y tareas destinadas a dar respuesta a cualquier incidente genérico que afecte a la seguridad de la información
- B) Documentar la seguridad de la organización
- C) Cumplir un requisito legal
- D) Documentar una relación de actividades y tareas destinadas a dar respuesta a cualquier incidente de la organización

> **Respuesta: A**
>
> **Explicación:** El Plan de Respuesta ante Incidentes documenta actividades para responder a incidentes que afecten **específicamente a la seguridad de la información**. La diferencia con D es sutil pero importante: el plan cubre incidentes de seguridad de la información, no "cualquier incidente de la organización" (un incendio en la cocina de la oficina no es un incidente de seguridad de la información).
>
> **Por qué no las otras:** B es demasiado genérico. C: aunque puede ser un requisito legal (ENS, NIS), la definición es A. D es demasiado amplia.

---

## UA 6. LEGISLACIÓN Y NORMATIVA EN SEGURIDAD DE LA INFORMACIÓN

📖 _Referencia completa:_ [06_legislacion-normativa.md](06_legislacion-normativa.md)

---

### 106. ¿Qué Ley ha asumido la mayoría de las funciones de la antigua LORTAD?

- A) Ley de Firma Electrónica
- B) LOPD
- C) Ninguna de las respuestas es correcta
- D) LSSI-CE

> **Respuesta: B**
>
> **Explicación:** La **LORTAD** (Ley Orgánica de Regulación del Tratamiento Automatizado de los Datos, 1992) fue la primera ley española de protección de datos. Fue sustituida por la **LOPD** (Ley Orgánica de Protección de Datos, 1999), que asumió la mayoría de sus funciones ampliándolas.
>
> **Por qué no las otras:** A (Ley de Firma Electrónica, 59/2003) regula la firma electrónica, no la protección de datos. D (LSSI-CE, 34/2002) regula servicios de la sociedad de la información y comercio electrónico.

---

### 107. La LOPD afecta a los siguientes tipos de ficheros:

- A) Ficheros digitales y en papel
- B) Sólo ficheros en papel
- C) Sólo ficheros digitales
- D) Ninguna de las respuestas es correcta

> **Respuesta: A**
>
> **Explicación:** La LOPD se aplica a ficheros **tanto digitales como en papel** (automatizados y no automatizados). Este es un punto importante: la protección de datos no se limita al ámbito digital. Un archivador con fichas de clientes en papel también está sujeto a la LOPD.
>
> **Por qué no las otras:** B y C son incorrectas porque limitan a un solo soporte. D es incorrecta.

---

### 108. La principal normativa que regula el acceso y tratamiento de datos de carácter personal es:

- A) La Ley de Firma Electrónica
- B) La Ley General de Telecomunicación
- C) La Ley de Servicio de la Sociedad de la Información y Comercio Electrónico
- D) La LOPD

> **Respuesta: D**
>
> **Explicación:** La **LOPD** (y actualmente LOPDyGDD) es la principal normativa española sobre protección de datos personales, regulando el acceso, tratamiento, derechos de los ciudadanos y obligaciones de quienes tratan datos.
>
> **Por qué no las otras:** A regula firma electrónica, B telecomunicaciones, C comercio electrónico. Ninguna es la normativa principal de protección de datos.

---

### 109. El Esquema Nacional de Seguridad es de obligado cumplimiento para:

- A) Las Administraciones de las Comunidades Autónomas
- B) Las entidades de Derecho público con personalidad jurídica propia vinculadas o dependientes de las Administraciones Públicas
- C) Todas las respuestas son correctas
- D) Las Entidades que integran la Administración Local

> **Respuesta: C**
>
> **Explicación:** El ENS (RD 3/2010) es de obligado cumplimiento para **TODAS las Administraciones Públicas**: Administración General del Estado, CCAA, Administración Local, entidades de derecho público vinculadas o dependientes, universidades públicas, organismos públicos... **Todas las opciones son correctas.**
>
> **Por qué no las otras:** Cada opción individual es correcta pero incompleta. Además, las empresas privadas que presten servicios a la AGE también deben cumplir el ENS.

---

### 110. ¿Qué establece el Esquema Nacional de Seguridad?

- A) Las condiciones de seguridad requeridas en el uso de los medios electrónicos en el ámbito de la Administración Pública
- B) Las condiciones de seguridad requeridas en el uso de los medios electrónicos en el ámbito de las organizaciones privadas
- C) El reglamento de requisitos técnicos de la LOPD
- D) Una relación de normas para la gestión de la seguridad en las empresas públicas

> **Respuesta: A**
>
> **Explicación:** El ENS establece las condiciones de seguridad en el uso de medios electrónicos en el ámbito de la **Administración Pública**. Define la política de seguridad, principios básicos y requisitos mínimos para proteger la información en las AAPP. Se regula por el RD 3/2010.
>
> **Por qué no las otras:** B: el ENS no se aplica directamente a organizaciones privadas (salvo que presten servicios a la AGE). C: el reglamento de la LOPD es el RD 1720/2007, distinto al ENS. D es una descripción imprecisa.

---

### 111. Uno de los objetivos principales del Esquema Nacional de Seguridad es:

- A) Establecer la política de seguridad en la utilización de medios electrónicos en el ámbito de la Ley 11/2007
- B) Crear un marco común para la actuación de las Administraciones Públicas en materia de seguridad de las tecnologías
- C) Todas las respuestas son correctas
- D) Aportar confianza a los ciudadanos en el ejercicio de sus derechos y deberes con la Administración Pública por medios telemáticos

> **Respuesta: C**
>
> **Explicación:** El ENS tiene múltiples objetivos, y **todos los mencionados son correctos**: (1) establecer política de seguridad según Ley 11/2007 (LAECSP), (2) crear un marco común para las AAPP en seguridad TIC, (3) aportar confianza a los ciudadanos en sus relaciones telemáticas con la AGE. La respuesta es **todas**.
>
> **Por qué no las otras:** Cada opción individual es correcta pero incompleta.

---

### 112. El Esquema Nacional de Seguridad está regulado por ...

- A) La Constitución Española
- B) La Ley General de Telecomunicación
- C) La Ley Orgánica de Protección de Datos
- D) El Real Decreto 3/2010 de 8 de enero

> **Respuesta: D**
>
> **Explicación:** El ENS se regula por el **Real Decreto 3/2010, de 8 de enero** (modificado posteriormente por RD 951/2015). Es un Real Decreto, no una Ley Orgánica ni está en la Constitución.
>
> **Por qué no las otras:** A: la Constitución (Art. 18.4) establece el derecho pero no regula el ENS. B y C son leyes diferentes. El ENS es un desarrollo reglamentario, no una ley.

---

### 113. ¿Qué es un SGSI?

- A) Un sistema de monitorización de redes
- B) Un plan Director de Seguridad
- C) Un sistema de gestión de seguridad de la información
- D) Un sistema general de seguridad interna

> **Respuesta: C**
>
> **Explicación:** **SGSI** = **Sistema de Gestión de Seguridad de la Información** (en inglés ISMS — Information Security Management System). Según ISO 27001: *"parte del sistema de gestión general, basada en un enfoque de riesgo empresarial, que se establece para crear, implementar, operar, supervisar, revisar, mantener y mejorar la seguridad de la información."*
>
> **Por qué no las otras:** A describe un SOC/NOC. B es un documento/plan, no un sistema de gestión completo. D no es un término estándar.

---

### 114. ¿Qué dos requisitos son fundamentales para establecer un SGSI?

- A) Disponer de recursos económicos y de personal
- B) Disponer de recursos tecnológicos y financieros
- C) Compromiso por la dirección y planteamientos realistas
- D) Acotar el trabajo y definir bien las funciones

> **Respuesta: C**
>
> **Explicación:** Los dos requisitos fundamentales son: **compromiso de la dirección** (sin apoyo directivo, el SGSI fracasa) y **planteamientos realistas** (no intentar abarcar demasiado, ser práctico). Las transparencias lo confirman: *"Factores críticos: Compromiso de la dirección y planteamientos realistas."*
>
> **Por qué no las otras:** A y B mencionan recursos materiales — necesarios pero no son los fundamentales. D es una buena práctica pero no los dos requisitos principales.

---

### 115. ¿Es necesario realizar un análisis de riesgos para implementar un SGSI?

- A) No, nunca
- B) Sí, siempre
- C) No, salvo que la organización lo decida así
- D) Sí, pero sólo en la Administración Pública

> **Respuesta: B**
>
> **Explicación:** **SÍ, siempre.** El análisis de riesgos es un paso OBLIGATORIO e INELUDIBLE para implementar un SGSI según ISO 27001. El SGSI se basa en un enfoque de riesgos: primero identificas los riesgos, luego decides cómo tratarlos. Sin análisis de riesgos no hay SGSI.
>
> **Por qué no las otras:** A, C y D son incorrectas. El análisis de riesgos no es opcional ni depende del tipo de organización.

---

### 116. Dentro de las etapas para el establecimiento de un SGSI, ¿Qué elementos de los siguientes es necesario definir?

- A) La Política de negocio de la organización
- B) La Política de Seguridad
- C) La Estrategia de negocio
- D) La Política de buen gobierno

> **Respuesta: B**
>
> **Explicación:** Según las etapas de implantación del SGSI, la **Fase II** es explícitamente: *"Definir la política de Seguridad de la Organización."* La política de seguridad es el documento fundacional del SGSI que establece el compromiso de la dirección y los principios rectores.
>
> **Por qué no las otras:** A, C y D son documentos de negocio, no elementos específicos del SGSI. La política de seguridad es el elemento del SGSI, no la política de negocio.

---

### 117. ¿Qué cuatro etapas de trabajo plantea el Ciclo PDCA o Ciclo de Deming?

- A) Pensar, Hacer, Recordar y Analizar
- B) Pensar, Hacer, Revisar y Actuar
- C) Planificar, Hacer, Revisar y Actuar
- D) Planificar, Hacer, Revisar y Analizar

> **Respuesta: C**
>
> **Explicación:** El ciclo PDCA (Plan-Do-Check-Act) de Deming, usado en ISO 27001 para la mejora continua del SGSI, se traduce como: **Planificar** (Plan), **Hacer** (Do), **Revisar/Verificar** (Check), **Actuar** (Act).
>
> **Por qué no las otras:** A y B empiezan con "Pensar" en vez de "Planificar". D termina con "Analizar" en vez de "Actuar". Los verbos exactos importan.

---

### 118. Dentro de los estándares ISO/IEC, ¿A qué ámbito se ha asignado el rango 27.000?

- A) A la gestión de las tecnologías de la información
- B) A la privacidad de la información
- C) A la seguridad de la información
- D) A las metodologías de gestión de riesgos

> **Respuesta: C**
>
> **Explicación:** La familia ISO/IEC **27000** está dedicada a la **Seguridad de la Información**. Incluye: 27000 (vocabulario), 27001 (requisitos SGSI, certificable), 27002 (buenas prácticas/controles), 27005 (gestión de riesgos), etc.
>
> **Por qué no las otras:** A (gestión TI) corresponde a ISO 20000. B (privacidad) corresponde a ISO 27701. D (gestión de riesgos) es ISO 31000; aunque 27005 cubre riesgos de seguridad, la familia completa es de seguridad de la información.

---

### 119. Los estándares ISO/IEC 27.001 y 27.002 ¿A qué ámbito pertenecen?

- A) A la privacidad de la información
- B) A las metodologías de gestión de riesgos
- C) A la seguridad de la información
- D) A ninguno de los anteriores

> **Respuesta: C**
>
> **Explicación:** ISO 27001 (requisitos para SGSI) e ISO 27002 (código de buenas prácticas/controles) pertenecen al ámbito de la **Seguridad de la Información**. Son los dos estándares más importantes de la familia 27000.
>
> **Por qué no las otras:** Misma lógica que la pregunta 118.

---

### 120. El RD-Ley 12/2018 asigna como CSIRT de notificación de incidentes para la red académica española a:

- A) INCIBE-CERT
- B) IRIS-CERT
- C) CCN-CERT
- D) ESP DEF

> **Respuesta: B**
>
> **Explicación:** Según el RD-Ley 12/2018 (trasposición de la Directiva NIS), los CSIRT de referencia son: **CCN-CERT** (organismos públicos), **INCIBE-CERT** (empresas y ciudadanos), **ESPDEF-CERT** (defensa), e **IRIS-CERT** (red académica española RedIRIS). IRIS-CERT es el CSIRT específico para universidades y centros de investigación.
>
> **Por qué no las otras:** A (INCIBE-CERT) cubre empresas y ciudadanos, no específicamente la red académica. C (CCN-CERT) cubre administración pública. D (ESPDEF-CERT) cubre defensa.

---

## 📌 Temas con más peso en el examen (según el profesor)

| Tema | Peso | Enfoque |
|------|------|---------|
| **UA 1** — Conceptos fundamentales | ⭐⭐⭐ | Definiciones, dimensiones, principios, políticas |
| **UA 2** — Criptografía | ⭐⭐⭐⭐⭐ | Hash, simétrico, asimétrico, modos, certificados, OpenSSL |
| **UA 3** — Amenazas | ⭐⭐ | Malware, tipos de ataques, perfiles |
| **UA 4** — Mecanismos de defensa | ⭐⭐ | WiFi, VPN, DMZ, CERT, direcciones IP |
| **UA 5** — Gestión de seguridad | ⭐⭐⭐ | ITIL, análisis de riesgos, auditoría, Plan Director |
| **UA 6** — Legislación y normativa | ⭐⭐⭐⭐ | LOPD, ENS, SGSI, ISO 27000, Esquema Nacional |

---

> 📚 **Referencias completas:**
> [T1 - Conceptos Fundamentales](01_conceptos-fundamentales.md) ·
> [T2 - Criptografía](02_criptografia-fundamentos.md) ·
> [T3 - Amenazas](03_amenazas-sistemas.md) ·
> [T4 - Mecanismos de Defensa](04_mecanismos-defensa.md) ·
> [T5 - Gestión de Seguridad](05_gestion-seguridad.md) ·
> [T6 - Legislación y Normativa](06_legislacion-normativa.md) ·
> [📖 GLOSARIO](GLOSARIO.md)

---

*Banco de preguntas completo de Seguridad de la Información — 4º Grado en Ingeniería Informática, ULPGC.*
