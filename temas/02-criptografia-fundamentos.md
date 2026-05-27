# UA 2 - Fundamentos en Seguridad Digital: Criptografia

> **Navegacion:**
> - [← README](../README.md)
> - [← Tema 1](01-conceptos-fundamentales.md)
> - [GLOSARIO](../GLOSARIO.md)
> - [Chuleta numerica](08-cheat-sheet-numeros.md)
> - [Tema 3 →](03-amenazas-sistemas.md)

---

## 1. Conceptos básicos de criptografía

### 1.1 Definiciones fundamentales

| Término | Definición |
|---------|------------|
| **Criptografía** | Ciencia que estudia las técnicas para cifrar/descifrar información, transformándola en un formato ininteligible para quien no posee la clave. |
| **Criptología** | Disciplina que engloba tanto la criptografía (cifrar) como el criptoanálisis (romper cifrados). Es la ciencia global del secreto. |
| **Criptoanálisis** | Estudio de métodos para romper sistemas criptográficos, obtener el texto claro o la clave sin estar autorizado. |

### 1.2 Proceso básico de cifrado

```
TEXTO CLARO (plaintext) + CLAVE (key) → ALGORITMO → TEXTO CIFRADO (ciphertext)
```

**Ejemplo real:** Cuando envías un mensaje por WhatsApp, tu texto "Hola, ¿cómo estás?" se combina con una clave de sesión generada por el protocolo Signal, y el algoritmo (AES-256) produce un galimatías ilegible que solo el destinatario puede revertir.

### 1.3 Dimensiones de seguridad que proporciona la criptografía

| Dimensión | Descripción | ¿Quién la garantiza? |
|-----------|-------------|----------------------|
| **Confidencialidad** | Solo el destinatario legítimo accede al contenido. | Cifrado simétrico y asimétrico |
| **Integridad** | El mensaje no ha sido alterado en tránsito. | Hash, HMAC, firma digital |
| **Autenticación** | Se verifica la identidad del emisor/destinatario. | HMAC, firma digital, certificados |
| **No Repudio** | El emisor no puede negar haber enviado el mensaje. | Firma digital (clave privada) |
| **Trazabilidad** | Se puede rastrear el origen y las acciones realizadas. | Registros firmados, logs criptográficos |
| **Temporalidad** | Se garantiza la vigencia o caducidad del mensaje. | Timestamps firmados, certificados con período de validez |

### 1.4 Principios de Shannon: Confusión y Difusión

Claude Shannon, padre de la teoría de la información, estableció dos propiedades esenciales para un cifrado seguro:

> **Confusión (sustitución):** La relación entre el texto claro y el texto cifrado debe ser lo más compleja posible. Se logra mediante sustituciones. Cada bit del texto cifrado debe depender de varias partes de la clave. *Ejemplo: la caja S (S-Box) de AES sustituye bytes por otros según una tabla predefinida.*

> **Difusión (transposición):** Cada bit del texto claro debe influir en muchos bits del texto cifrado. Se logra mediante permutaciones y transposiciones. *Ejemplo: la operación ShiftRows y MixColumns en AES dispersa los bits por todo el bloque.*

Ambos principios se aplican juntos para evitar el criptoanálisis estadístico. AES combina confusión (SubBytes) y difusión (ShiftRows + MixColumns) en cada ronda.

### 1.5 Criptosistema seguro de Shannon

Un sistema criptográfico es **incondicionalmente seguro** si:

| Condición | Significado |
|-----------|-------------|
| **Espacio de claves ≥ Espacio de mensajes** | Debe haber al menos tantas claves posibles como mensajes posibles. |
| **Clave tan larga como el mensaje** | La clave no puede reutilizarse sin comprometer la seguridad. |
| **Clave verdaderamente aleatoria** | Sin patrones predecibles. |

> **One-Time Pad (OTP)** es el único criptosistema demostrado matemáticamente seguro, pero es impráctico para uso masivo: la clave debe ser del mismo tamaño que el mensaje, no puede reutilizarse y debe compartirse previamente.

### 1.6 XOR como base del cifrado binario

La operación XOR (⊕) es la columna vertebral del cifrado moderno:

```
Propiedad fundamental: A ⊕ B ⊕ B = A
```

| Propiedad | Explicación |
|-----------|-------------|
| **Cifrado** | TextoCifrado = TextoClaro ⊕ Clave |
| **Descifrado** | TextoClaro = TextoCifrado ⊕ Clave |
| **Reversibilidad** | Aplicar XOR dos veces con la misma clave devuelve el original |
| **Perfecto si clave aleatoria** | Con OTP, el adversario no obtiene información del texto claro |

**Ejemplo real:** En AES-CBC, cada bloque de texto claro se XOR-ea con el bloque cifrado anterior antes de entrar al cifrador. En CTR, un contador genera un flujo pseudoaleatorio que se XOR-ea con el texto claro.

### 1.7 Historia de la criptografia

La criptografia tiene una larga historia que abarca milenios:

| Hito | Epoca | Descripcion |
|------|-------|-------------|
| **Escitalo babilonico** | Antiguedad | Primer dispositivo criptografico conocido. Un baston alrededor del cual se enrollaba una tira de cuero; el mensaje solo era legible al enrollarlo en un baston del mismo diametro. |
| **"La clave" del Imperio Espanol** | Siglos XVI-XVII | Sistema de cifrado basado en sustituir silabas, terminaciones y letras por simbolos o numeros. Felipe II lo perfecciono para las comunicaciones con sus territorios. |
| **Maquinas de rotores** | Siglo XIX | Primeros dispositivos mecanicos de cifrado basados en discos giratorios (rotores) que realizaban sustituciones polialfabeticas complejas. |
| **IIGM -- Sigaba** | 1940s | Maquina de rotores estadounidense usada por la US Navy. Nunca fue rota por las potencias del Eje. |
| **IIGM -- Purple** | 1940s | Maquina de cifrado diplomatica japonesa. Descifrada por William Friedman y el equipo del SIS estadounidense antes de Pearl Harbor. |
| **IIGM -- Enigma** | 1940s | Maquina de rotores alemana. Su criptoanalisis por **Alan Turing** y el equipo de Bletchley Park fue decisivo para el curso de la guerra. |
| **SZ40 (Lorenz)** | 1940s | Cifrador de teletipo aleman de alto nivel (usado por el alto mando). Su criptoanalisis lo dirigio **Max Newman** y se construyo **Colossus**, el **PRIMER COMPUTADOR ELECTRONICO** de la historia, con 1500 valvulas de vacio. |

> La historia de la criptografia demuestra una constante carrera entre cifradores y criptoanalistas. Cada avance en el cifrado provoca nuevos metodos de ataque, y viceversa.

---

## 2. Algoritmos de Resumen (Hash)

### 2.1 Definición y propósito

> **Función Hash criptográfica:** algoritmo que transforma una entrada de tamaño arbitrario en una salida de tamaño fijo (digest/huella/resumen), con la propiedad de que es computacionalmente inviable invertir la función o encontrar colisiones.

**Propiedades obligatorias:**

| Propiedad | Significado |
|-----------|-------------|
| **Resistencia a preimagen** | Dado un hash `h`, es inviable encontrar un mensaje `m` tal que `hash(m) = h` |
| **Resistencia a segunda preimagen** | Dado `m1`, es inviable encontrar `m2 ≠ m1` tal que `hash(m1) = hash(m2)` |
| **Resistencia a colisiones** | Es inviable encontrar dos mensajes `m1 ≠ m2` tal que `hash(m1) = hash(m2)` |
| **Determinismo** | La misma entrada siempre produce la misma salida |
| **Efecto avalancha** | Cambiar un solo bit de la entrada altera ~50% de los bits de salida |

**Función principal:** INTEGRIDAD (verificar que los datos no han sido modificados).

### 2.2 Familias de algoritmos Hash

| Algoritmo | Tamaño (bits) | Estado | Descripción |
|-----------|---------------|--------|-------------|
| **MD2** | 128 | ⛔ Roto | Creado por Ron Rivest (1989). Vulnerable a colisiones. |
| **MD4** | 128 | ⛔ Roto | Predecesor de MD5. Colisiones en segundos. |
| **MD5** | 128 | ⛔ Roto | Muy usado históricamente. Colisiones demostradas en 2004 por Wang. Ya no es seguro para nada criptográfico. |
| **SHA-1** | 160 | ⛔ Roto | Colisión práctica demostrada por Google/Brincat en 2017 (SHAttered). Git aún lo usa internamente pero está migrando. |
| **SHA-2** (SHA-256) | 256 | ✅ Seguro | Estándar actual. Usado en Bitcoin, TLS, firmas digitales. |
| **SHA-2** (SHA-384) | 384 | ✅ Seguro | Variante más larga de SHA-2. |
| **SHA-2** (SHA-512) | 512 | ✅ Seguro | La más larga de la familia SHA-2. |
| **SHA-3** | 224/256/384/512 | ✅ Seguro | Ganador del concurso NIST 2012 (Keccak). Alternativa con estructura esponja, diferente a SHA-2. |
| **Whirlpool** | 512 | ✅ Seguro | Diseñado por Rijmen y Barreto. Basado en AES. Estándar ISO/IEC 10118-3. Alternativa a SHA-2/3. |

> ⚠️ **IMPORTANTE:** Camellia NO es un algoritmo de resumen. Es un **cifrador de bloque simétrico** (como AES), seleccionado por el proyecto NESSIE junto con AES. No genera huellas ni resúmenes.

### 2.3 Aplicaciones de los resúmenes (con ejemplos reales)

#### 2.3.1 Cifrado de contraseñas — Autenticación

| Sistema | Método | Ejemplo |
|---------|--------|---------|
| **Linux** | `/etc/shadow` almacena el hash de la contraseña con sal. Nunca la contraseña en texto claro. | `$6$sal$hashedpassword` (SHA-512) en `/etc/shadow` |
| **Windows** | NTLM (MD4 en LAN Manager) o en Active Directory usa Kerberos con hashes. | Los hashes se almacenan en la SAM (`C:\Windows\System32\config\SAM`) o en NTDS.dit |

```
Proceso de login en Linux:
1. Usuario introduce contraseña "M1P4ssword!"
2. Sistema toma la sal almacenada y calcula hash("M1P4ssword!" + sal)
3. Compara resultado con el hash almacenado en /etc/shadow
4. Si coinciden → acceso permitido
```

#### 2.3.2 Integridad de documentos

**Ejemplo real -- Descarga de software:**
```
1. Descargas ubuntu-24.04.iso desde internet
2. Calculas: sha256sum ubuntu-24.04.iso
3. Comparas con el hash publicado en el sitio oficial
4. Si coinciden: el archivo no ha sido manipulado en tránsito
```

También se usa en sistemas de control de versiones:
- **Git:** cada commit se identifica por su hash SHA-1 (migrando a SHA-256). El hash depende del contenido del commit, padre, autor y timestamp. Cualquier modificación en la historia produce un hash diferente.

#### 2.3.3 Firma digital (cifrado asimétrico del resumen)

```
Documento → hash → cifrado con clave PRIVADA del firmante → Firma digital
```

> Se firma el **resumen** (hash), NO el documento entero. El hash reduce cualquier documento a un tamaño fijo, haciendo la firma eficiente.

**Ejemplo real -- Firma del DNIe:**
- La FNMT firma documentos PDF. Internamente: hash SHA-256 del PDF → cifrado RSA con clave privada del DNI → firma adjunta al PDF.

#### 2.3.4 Firma de claves -- Evitar Man in the Middle

**Ejemplo real -- PGP/GPG:**
```
1. Alice genera par de claves (pública y privada)
2. Alice comparte su clave pública con Bob en persona
3. Bob verifica la huella digital (fingerprint): SHA-256 de la clave pública
4. Bob firma la clave de Alice con su propia clave privada
5. Ahora el anillo de confianza de Bob marca la clave de Alice como "confiable"
```

La huella (fingerprint) de una clave es el hash de la clave pública. Si te muestran la huella por un canal alternativo (voz, presencial), puedes validar que la clave no ha sido suplantada.

#### 2.3.5 Derivación de claves (KDF -- Key Derivation Function)

| Función | Descripción | Ejemplo real |
|---------|-------------|--------------|
| **PBKDF1** | Password-Based Key Derivation Function 1 (PKCS #5 v1.5). Itera hash con sal. Limitado a 160 bits de salida. | Usado en versiones antiguas de Java KeyStore. |
| **PBKDF2** | Password-Based Key Derivation Function 2 (PKCS #5 v2.0). Itera HMAC con sal. Configurable en hash subyacente y longitud de salida. | **Wi-Fi WPA2-PSK:** tu contraseña WiFi se convierte en la clave PMK usando PBKDF2 con HMAC-SHA1 y 4096 iteraciones sobre el SSID como sal. |
| **HKDF** | HMAC-based Key Derivation Function (RFC 5869). Diseñado para extraer múltiples claves de un secreto compartido. | **Protocolo Signal (WhatsApp/Signal):** usa HKDF para derivar múltiples claves de sesión a partir del secreto negociado via Extended Triple Diffie-Hellman. |
| **Argon2** | Ganador del Password Hashing Competition (2015). Resistente a GPU/ASIC. | **KeePassXC, LUKS2** lo usan para derivar la clave maestra desde la contraseña. |

#### 2.3.6 HMAC -- Hash-based Message Authentication Code

> **HMAC** combina una función hash criptográfica con una clave secreta compartida para garantizar **integridad** y **autenticación** simultáneamente.

```
HMAC = hash( (key ⊕ opad) || hash( (key ⊕ ipad) || mensaje ) )
```

| Propiedad | ¿Quién la garantiza? |
|-----------|----------------------|
| Integridad | ✅ -- El hash detecta cualquier modificación |
| Autenticación | ✅ -- Solo quien posee la clave puede generar un HMAC válido |
| Confidencialidad | ❌ -- HMAC no oculta el mensaje |
| No Repudio | ❌ -- La clave es compartida, no hay forma de probar quién generó el HMAC |

**Ejemplo real -- AWS API requests (Signature v4):**
Cuando haces una petición a la API de AWS, el cliente calcula HMAC-SHA256 de la petición usando tu clave secreta de acceso. AWS recalcula el HMAC en el servidor y compara. Si coinciden, la petición es auténtica y no ha sido alterada. Esto evita que un atacante modifique parámetros de la petición o suplante tu identidad.

**Ejemplo real -- JWT (JSON Web Tokens):**
Algoritmo HS256 = HMAC con SHA-256. El servidor firma el token JWT con una clave secreta. Cualquier manipulación del payload invalida la firma HMAC.

### 2.4 Sal criptográfica (Salt)

> **Sal (Salt):** valor aleatorio único añadido a una entrada antes de aplicar la función hash. Su propósito es **evitar ataques de diccionario y rainbow tables**, haciendo que contraseñas iguales produzcan hashes diferentes.

```
hash_sin_sal("123456") → mismo hash para todos los usuarios
hash_con_sal("123456" + "a3f2c8e1") → diferente para cada usuario, incluso con misma contraseña
```

| La sal SÍ protege contra... | La sal NO protege contra... |
|------------------------------|------------------------------|
| Rainbow tables (tablas precomputadas) | Ataques de cumpleaños (paradoja del cumpleaños sobre colisiones) |
| Ataques de diccionario masivos | Fuerza bruta sobre una contraseña concreta |
| Contraseñas idénticas con mismo hash | Ataques de diccionario dirigidos a un solo usuario |

**Ejemplo real -- Linux `/etc/shadow`:**
```
usuario:$6$T0hfIa9S$seN7fFabc123...:19123:0:99999:7:::
        ├──┤├─────────┤├─────────────────────
        │    │          └─ Hash SHA-512 de (contraseña + sal)
        │    └─ Sal única de 8 caracteres
        └─ Algoritmo: $6 = SHA-512
```

### 2.5 HMAC vs funciones Hash simples

| Aspecto | Hash simple (SHA-256) | HMAC (HMAC-SHA-256) |
|---------|----------------------|---------------------|
| ¿Usa clave secreta? | ❌ No | ✅ Sí |
| Garantiza integridad | ✅ Sí | ✅ Sí |
| Garantiza autenticación | ❌ No | ✅ Sí |
| Vulnerable a ataques de extensión de longitud | Sí (SHA-256 sí) | No |
| Uso típico | Checksum de archivos | API auth, JWT, cookies firmadas |

---

## 3. Criptografía de Clave Simétrica

### 3.1 Definición y características

> **Cifrado simétrico:** mismo secreto (clave) usado para cifrar y descifrar. Tanto el emisor como el receptor deben conocer la misma clave secreta.

```
CIFRADO:   TextoClaro + CLAVE_SECRETA → TextoCifrado
DESCIFRADO: TextoCifrado + CLAVE_SECRETA → TextoClaro
```

| Característica | Detalle |
|----------------|---------|
| **Ventaja principal** | Alta velocidad. Ideal para grandes volúmenes de datos. |
| **Problema principal** | Cómo transmitir la clave de forma segura al destinatario sin que un tercero la intercepte. |
| **¿Qué asegura?** | CONFIDENCIALIDAD (el secreto del contenido). |
| **¿Qué NO asegura por sí solo?** | Integridad (no detecta modificaciones) ni No Repudio (no prueba quién envió el mensaje). |
| **Potencia determinada por** | Calidad del algoritmo + Tamaño de la clave. **NO por el secreto del algoritmo** (Principio de Kerckhoffs). |

### 3.2 Principio de Kerckhoffs (1883)

> **"Un sistema criptográfico debe ser seguro incluso si todo sobre él, excepto la clave, es de dominio público."**
>
> -- Auguste Kerckhoffs

La seguridad NO debe depender del secreto del algoritmo. Los algoritmos estandarizados (AES, SHA) son públicos y han sido sometidos a escrutinio de la comunidad criptográfica global. La seguridad reside exclusivamente en el secreto de la **clave**.

**Contraejemplo -- Algoritmos propietarios:** el estándar A5/1 (cifrado GSM) se mantuvo secreto inicialmente. Fue sometido a ingeniería inversa en 1999 y resultó ser débil, con ataques prácticos en minutos.

### 3.3 Algoritmos simétricos históricos y actuales

#### Cifradores de BLOQUE

| Algoritmo | Año | Tamaño de bloque | Tamaño de clave | Estado |
|-----------|-----|-----------------|-----------------|--------|
| **DES** | 1976 | 64 bits | 56 bits (efectivos) | ⛔ Roto. Clave demasiado corta. Roto en 22h con hardware dedicado (1998). **Controversia NSA/IBM:** sospechas de claves debiles introducidas deliberadamente. |
| **3DES / TDES** | 1998 | 64 bits | 112/168 bits | ⚠️ Obsoleto. Aún permitido por PCI-DSS pero en desuso. Bloque pequeño vulnerable a Sweet32. **Mecanica E-D-E:** cifrado-descifrado-cifrado con 2 o 3 claves distintas. |
| **IDEA** | 1992 | 64 bits | 128 bits | ⚠️ Usado en PGP. Patente expirada en 2012. Seguro pero bloque pequeño. **RC5** es otro algoritmo de referencia con parametros variables. |
| **AES** (Rijndael) | 2000 | **128 bits siempre** | 128/192/256 bits | ✅ Estándar mundial. |
| **Camellia** | 2000 | 128 bits | 128/192/256 bits | ✅ Alternativa a AES. Usado en Japón. |
| **Blowfish** | 1993 | 64 bits | 32-448 bits | ⚠️ Legado. Sustituido por Twofish. |
| **Twofish** | 1998 | 128 bits | 128/192/256 bits | ✅ Finalista del concurso AES. Seguro. |

> ⚠️ **IMPORTANTE:** AES tiene tamaño de bloque **FIJO** de 128 bits. Lo que varía es el tamaño de la clave (128, 192 o 256).

#### Cifradores de FLUJO (Stream Ciphers)

A diferencia de los cifradores de bloque, los de flujo cifran bit a bit (o byte a byte) usando un flujo de clave pseudoaleatorio.

| Algoritmo | Características | Estado |
|-----------|-----------------|--------|
| **RC4** | Diseñado por Ron Rivest. Usado en WEP, WPA (TKIP), SSL/TLS inicial. Muy rápido, clave 40-2048 bits. | ⛔ Roto. Prohibido en RFC 7465. Vulnerabilidad grave: el keystream tiene sesgos estadísticos aprovechables. |
| **SEAL** | Cifrador de flujo de longitud variable, diseniado por Phillip Rogaway y Don Coppersmith. Optimizado para software, muy rapido. | ⚠️ Poco usado. Interes historico como cifrador de flujo de proposito general. |
| **Salsa20** | Diseñado por Daniel J. Bernstein. Clave 256 bits. Muy rápido en software. | ✅ Seguro. |
| **ChaCha20** | Mejora de Salsa20. Más difusión por ronda. | ✅ Estándar moderno. TLS 1.3 y WireGuard lo usan. |
| **AES-CTR** | Modo de operación de AES que lo convierte en cifrador de flujo. | ✅ Estándar. |

```
Diferencia clave:
- BLOQUE: procesa bloques de tamaño fijo (ej. AES = 128 bits)
- FLUJO: procesa bit a bit, XOR del texto claro con un keystream
```

> ⚠️ **RC4 es de FLUJO, NO de bloque.** RC2 sí es de bloque. Pregunta típica de examen.

**Actualmente:** AES 128/256 en modo CTR / GCM son los cifradores estandar. Aunque GCM y CTR son los recomendados, en la practica se sigue usando CBC y CFB por compatibilidad con sistemas heredados.

### 3.4 Ejemplo real: WhatsApp y el Protocolo Signal

WhatsApp usa el protocolo **Signal** para cifrado de extremo a extremo (E2EE). Su funcionamiento:

```
1. Negociación de clave: Extended Triple Diffie-Hellman (X3DH) -- asimétrico
2. Cifrado de mensajes: AES-256-CBC (simétrico), con HMAC-SHA256 para integridad/autenticación
3. Ratchet post-compromiso: genera nuevas claves cada mensaje (Double Ratchet)
```

---

## 4. Modos de Operación (Cifrado en Bloque)

Los modos de operación definen cómo se aplica un cifrador de bloque (como AES) a mensajes de más de un bloque.

### 4.1 ECB -- Electronic Codebook (⚠️ MUY PELIGROSO)

```
C_i = E_K(P_i)     Cada bloque se cifra independientemente con la misma clave
```

| Característica | Detalle |
|----------------|---------|
| **¿Usa IV?** | ❌ NO |
| **¿Transforma en flujo?** | ❌ NO |
| **Problema grave** | Bloques iguales de texto claro producen bloques iguales de texto cifrado. Revela patrones del documento. |
| **¿Cuándo usarlo?** | **NUNCA** para datos con patrones repetitivos. |

```
Texto claro (16B bloques): "AAAA" "AAAA" "BBBB" "BBBB"
Texto cifrado (ECB):      "X3f1" "X3f1" "9a7c" "9a7c"
                           ↑↑↑↑   ↑↑↑↑  ← Mismos bloques, MISMO cifrado. ¡MAL!
```

**Ejemplo visual del desastre:** Si cifras una imagen BMP con ECB, la imagen sigue siendo reconocible porque los patrones de color se mantienen. El famoso "ECB penguin" muestra perfectamente la silueta del pingüino de Linux.

### 4.2 CBC -- Cipher Block Chaining

```
C_0 = IV
C_i = E_K(P_i ⊕ C_{i-1})     Cada bloque se XOR-ea con el cifrado del anterior
```

| Característica | Detalle |
|----------------|---------|
| **¿Usa IV?** | ✅ SÍ (necesario, debe ser aleatorio e impredecible) |
| **¿Transforma en flujo?** | ❌ NO (sigue siendo modo de bloque, necesita padding) |
| **Propagación** | Un error en un bloque afecta al descifrado de ese bloque y los dos siguientes. |
| **Vulnerabilidad** | Padding Oracle Attack (si no se usa autenticación) |
| **Uso** | Históricamente el más usado. Sustituido por modos autenticados (GCM). |

### 4.3 PCBC -- Propagating CBC

```
C_0 = IV
C_i = E_K(P_i ⊕ P_{i-1} ⊕ C_{i-1})
```

| Característica | Detalle |
|----------------|---------|
| **¿Usa IV?** | ✅ SÍ |
| **Propagación** | Un error en un bloque invalida TODO el resto del mensaje. |
| **Uso** | Kerberos v4. Prácticamente en desuso. |

### 4.4 OFB -- Output Feedback (Modo de flujo)

```
O_0 = IV
O_i = E_K(O_{i-1})            ← keystream (solo depende del IV y la clave)
C_i = P_i ⊕ O_i              ← XOR con el keystream
```

| Característica | Detalle |
|----------------|---------|
| **¿Usa IV?** | ✅ SÍ |
| **¿Transforma bloque en flujo?** | ✅ SÍ |
| **Ventaja** | No necesita padding. Errores de transmisión no se propagan (solo afectan al bit correspondiente). |
| **Precaución** | Si se reutiliza IV+clave, se pierde la seguridad. El keystream debe ser único. |

### 4.5 CFB -- Cipher Feedback (Modo de flujo)

```
C_0 = IV
C_i = P_i ⊕ E_K(C_{i-1})    ← modo stream autosincronizado
```

| Característica | Detalle |
|----------------|---------|
| **¿Usa IV?** | ✅ SÍ |
| **¿Transforma bloque en flujo?** | ✅ SÍ |
| **Diferencia con OFB** | El keystream depende del texto cifrado anterior, no solo de la clave. Se autosincroniza tras errores. |

### 4.6 CTR -- Counter (Modo de flujo)

```
C_i = P_i ⊕ E_K(IV || counter_i)    ← cifra un contador incrementado
```

| Característica | Detalle |
|----------------|---------|
| **¿Usa IV?** | ✅ SÍ (llamado nonce) |
| **¿Transforma bloque en flujo?** | ✅ SÍ |
| **Ventajas** | Altamente paralelizable (cifrado y descifrado). No necesita padding. Acceso aleatorio a bloques. |
| **Precaución** | Nunca reutilizar (IV+clave, contador). |

### 4.7 GCM -- Galois Counter Mode (AEAD)

> **AEAD:** Authenticated Encryption with Associated Data -- cifrado que proporciona confidencialidad + autenticación en una sola operación.

```
GCM = CTR (cifrado) + GHASH (autenticación con aritmética en GF(2^128))
```

| Característica | Detalle |
|----------------|---------|
| **¿Usa IV?** | ✅ SÍ (nonce, recomendado 96 bits) |
| **¿Cifrado autenticado?** | ✅ SÍ -- genera tag de autenticación (GMAC) |
| **Uso actual** | TLS 1.3, IPsec, SSH. Es el modo estándar moderno. |
| **Precaución** | **NUNCA reutilizar nonce con misma clave.** Reutilizar nonce rompe completamente la seguridad (confidencialidad y autenticación). |

### 4.8 Tabla resumen de modos

| Modo | ¿Usa IV? | ¿Flujo? | ¿Padding? | ¿Paralelizable? | ¿Autenticado? | Seguridad |
|------|----------|---------|-----------|-----------------|---------------|-----------|
| **ECB** | ❌ No | ❌ No | Sí | Sí (cifrado) | ❌ No | ⛔ Inseguro |
| **CBC** | ✅ Sí | ❌ No | Sí | Solo descifrado | ❌ No | ⚠️ Sin autenticar |
| **PCBC** | ✅ Sí | ❌ No | Sí | No | ❌ No | ⚠️ Obsoleto |
| **OFB** | ✅ Sí | ✅ Sí | No | No | ❌ No | ⚠️ Precaución IV |
| **CFB** | ✅ Sí | ✅ Sí | No | Solo descifrado | ❌ No | ⚠️ Precaución IV |
| **CTR** | ✅ Sí | ✅ Sí | No | Sí | ❌ No | ✅ (con cuidado) |
| **GCM** | ✅ Sí | ✅ Sí | No | Sí | ✅ Sí | ✅ Recomendado |

### 4.9 Padding en cifradores de bloque: PKCS#7 a fondo

#### ¿Por que existe el padding?

Un cifrador de **bloque** (AES, DES) opera sobre bloques de tamanio fijo. AES siempre cifra bloques de **128 bits (16 bytes)**. Si un mensaje no es multiplo exacto del bloque, el ultimo bloque queda incompleto. Hay que **rellenarlo** con algo: eso es el padding.

```
Mensaje: "HOLA MUNDO" (10 bytes)

Cifrador de flujo (RC4):
  [H][O][L][A][ ][M][U][N][D][O] → 10 bytes cifrados
  Tamanio final: 10 bytes (IDENTICO)

Cifrador de bloque (AES, bloque = 16 bytes):
  [H][O][L][A][ ][M][U][N][D][O][?][?][?][?][?][?]
  └─────── 10 bytes utiles ──────┘└── 6 bytes de padding ──┘
  Tamanio final: 16 bytes (1 bloque)
```

#### PKCS#7: el estandar de OpenSSL

**PKCS#7** (Public Key Cryptography Standards #7) es el esquema de padding por defecto. Regla:

> Cada byte de padding contiene el **numero total de bytes de padding** anadidos.

| Bytes que faltan | Valor de cada byte | Aspecto del padding |
|:----------------:|:------------------:|---------------------|
| 1 | 0x01 | `[01]` |
| 2 | 0x02 | `[02][02]` |
| 3 | 0x03 | `[03][03][03]` |
| 7 | 0x07 | `[07][07][07][07][07][07][07]` |
| 15 | 0x0F | `[0F]...[0F]` (15 bytes) |
| 0 (multiplo exacto) | 0x10 | `[10]...[10]` (16 bytes, 1 bloque entero) |

**Caso critico: el mensaje ya es multiplo de 16.** Se anade un bloque ENTERO de padding (16 bytes con valor 0x10). ¿Por que? Porque al descifrar, OpenSSL necesita encontrar padding SIEMPRE. Si no hubiera padding, no podria distinguir entre "no habia padding" y "el ultimo byte de datos valia 0x01 por casualidad".

**Al descifrar:**
```
1. Descifrar → obtienes datos + padding
2. Leer el ULTIMO byte. Ej: 0x05
3. Quitar 5 bytes de padding
4. Verificar que los 5 bytes son todos 0x05
   Si no coinciden → "bad padding" (mensaje manipulado o clave incorrecta)
```

#### Calculo del tamanio final en OpenSSL

**Con contrasenia** (`openssl enc -aes-256-cbc -pass pass:...`):
```
Tamanio_final = original + 16 (cabecera "Salted__") + padding hasta multiplo de 16
```
La cabecera son 16 bytes fijos: 8 de texto "Salted__" + 8 de salt aleatoria.

**Con clave + IV directos** (`openssl enc -aes-256-cbc -K ... -iv ...`):
```
Tamanio_final = original + padding hasta multiplo de 16
```
Sin cabecera porque clave e IV ya los proporcionas tu.

**Ejemplos para el examen:**
- 5 bytes con contrasenia → 5 + 16 + 11 = **32 bytes** (2 bloques)
- 16 bytes con clave directa → 16 + 16 = **32 bytes** (bloque completo + bloque de padding)
- 100 bytes con RC4 → **100 bytes** (identico, cifrador de flujo)

#### Padding Oracle Attack (concepto)

Si un servidor responde diferente ante "padding OK" vs "padding incorrecto", un atacante puede descifrar el mensaje entero sin la clave. **Mitigacion:** usar modos AEAD (GCM, ChaCha20-Poly1305) que autentican antes de verificar el padding. TLS 1.3 elimino CBC por esto.

---

## 5. Criptografía de Clave Asimétrica

### 5.1 Definición y características

> **Cifrado asimétrico:** utiliza dos claves matemáticamente relacionadas pero computacionalmente imposibles de derivar una de la otra:
> - **Clave pública:** se distribuye libremente. Sirve para **cifrar** mensajes (solo el dueño de la privada puede descifrar) o **verificar** firmas.
> - **Clave privada:** se guarda en secreto. Sirve para **descifrar** mensajes (cifrados con la pública) o **firmar** documentos.

| Clave pública (distribuida) | Clave privada (secreta) |
|----------------------------|-------------------------|
| Cifrar | Descifrar |
| Verificar firmas | Firmar |

### 5.2 Ventajas y desventajas

| Ventajas | Desventajas |
|----------|-------------|
| Elimina el problema de distribución de clave secreta del modelo simétrico | **Coste computacional:** ~1000-10000 veces más lento que el cifrado simétrico |
| Facilita el No Repudio (la clave privada identifica al emisor) | Claves mucho más largas que las simétricas para seguridad equivalente |
| Escala bien en redes grandes (n participantes = n pares, no n² secretos) | **Pérdida/sustracción de clave privada:** el problema principal. Si alguien obtiene tu clave privada, puede descifrar todo y suplantarte. Solución: revocación mediante certificados y CRL. |

### 5.3 Base matemática

Se fundamenta en problemas matemáticos **computacionalmente difíciles** (inviables con ordenadores clásicos actuales):

- **Factorización de enteros:** descomponer un número grande en sus factores primos
- **Logaritmo discreto:** dado `g^a mod p`, encontrar `a`
- **Curvas elípticas:** problema del logaritmo discreto en el grupo de puntos de una curva elíptica

> ⚠️ **Computación cuántica:** El algoritmo de Shor resuelve factorización y logaritmos discretos en tiempo polinomial. Los algoritmos asimétricos actuales (RSA, ECC, DH) serán **inseguros** con ordenadores cuánticos suficientemente grandes. Los algoritmos de resumen (SHA) y simétricos (AES) solo ven reducida su seguridad a la mitad (algoritmo de Grover).

### 5.4 Principales algoritmos

#### 5.4.1 RSA (Rivest-Shamir-Adleman, 1978)

> **Algoritmo ASIMÉTRICO** basado en la **imposibilidad computacional de factorizar números enteros muy grandes** (producto de dos primos).

```
Generación de claves:
1. Elegir dos primos grandes p y q
2. n = p × q        ← módulo (público)
3. φ(n) = (p-1)(q-1)
4. Elegir e coprimo con φ(n)    ← exponente público (típicamente 65537)
5. d = e⁻¹ mod φ(n)             ← exponente privado
   Clave pública: (n, e)
   Clave privada: (d)

Cifrado:  C = M^e mod n
Descifrado: M = C^d mod n
```

| Característica | Detalle |
|----------------|---------|
| **Tipo** | Asimétrico. **NO es de bloque ni de flujo** (son conceptos del cifrado simétrico). |
| **Tamaño de clave** | 1024-8192 bits. Mínimo recomendado: 2048 bits. |
| **Seguridad** | Basada en factorización de enteros. |
| **Limitación** | Cifra datos de tamaño ≤ tamaño de clave (menos padding). Para datos grandes se usan sistemas mixtos. |
| **Patente** | **Patente hasta 2000.** RSA estuvo protegido por patente de RSA Security hasta su expiracion en septiembre de 2000. |

#### 5.4.2 Diffie-Hellman (1977)

> **Algoritmo ASIMÉTRICO para NEGOCIACIÓN de claves SIMÉTRICAS.** NO transmite claves, negocia un secreto compartido entre dos partes a través de un canal público inseguro.

```
Negociación DH:
Público: número primo p y generador g
1. Alice elige a (secreto) → envía A = g^a mod p a Bob
2. Bob elige b (secreto) → envía B = g^b mod p a Alice
3. Alice calcula: s = B^a mod p = g^(ab) mod p
4. Bob calcula:   s = A^b mod p = g^(ab) mod p
   Ambos comparten s = g^(ab) mod p sin haberlo transmitido nunca
```

| Característica | Detalle |
|----------------|---------|
| **Función** | Negociación de clave secreta compartida (NO cifrado de datos). |
| **Uso real** | TLS (DHE/ECDHE para Perfect Forward Secrecy). Signal (X3DH). SSH (Diffie-Hellman Group Exchange). |
| **Variantes** | DH clásico (módulo primo), ECDH (sobre curvas elípticas). |
| **Patente** | **Patente hasta 1997.** El algoritmo Diffie-Hellman estuvo protegido por patente hasta su expiracion en 1997. |

#### 5.4.3 ElGamal (1985)

> **Algoritmo ASIMÉTRICO** basado en la **dificultad de calcular logaritmos discretos** (NO factorización como RSA).

| Característica | Detalle |
|----------------|---------|
| **Base matemática** | Problema del logaritmo discreto en grupos cíclicos. |
| **Propiedad** | Es **probabilístico**: el mismo texto claro cifrado dos veces produce texto cifrado diferente (propiedad de no determinismo). |
| **Desventaja** | El texto cifrado tiene el doble de tamaño que el texto claro. |
| **Patente** | **NO fue patentado.** ElGamal no tenia proteccion de patente, a diferencia de RSA y DH. Esto facilito su adopcion en software libre. |
| **Algoritmos** | **Dos algoritmos distintos:** uno para cifrado y otro para firma digital. Ambos basados en el mismo problema matematico del logaritmo discreto. |
| **Uso** | Incorporacion a **PGP** como alternativa sin patentes. Base de DSA (Digital Signature Algorithm) y de algunas implementaciones de GPG. |

#### 5.4.4 Schnorr (1989)

> **Algoritmo de firma digital** basado en el problema del logaritmo discreto. Diseniado por Claus-Peter Schnorr.

| Característica | Detalle |
|----------------|---------|
| **Tipo** | Algoritmo de firma digital asimetrico. |
| **Propiedad** | **Lineal y rapido.** Mas eficiente que otras alternativas de la epoca. |
| **Patente** | **Patente hasta 2008.** La patente de Schnorr expiro en febrero de 2008. Durante su vigencia, limito su adopcion generalizada. |

#### 5.4.5 DSA (Digital Signature Algorithm, 1991)

> **Algoritmo de firma digital** desarrollado por la **NSA** y adoptado como estandar federal estadounidense (FIPS 186).

| Característica | Detalle |
|----------------|---------|
| **Origen** | Desarrollado por la NSA como alternativa a Schnorr para evitar su patente. |
| **Propiedad** | **No lineal y lento** en comparacion con Schnorr. Solo sirve para firma, no para cifrado. |
| **Base matematica** | Problema del logaritmo discreto (misma base que ElGamal y Schnorr). |

#### 5.4.6 Curvas Elipticas: ECDH, ECDSA, EdDSA

> **Criptografia de Curva Eliptica (ECC):** alternativa a RSA/DH que ofrece seguridad equivalente con claves mucho mas cortas.

| Algoritmo | Tipo | Tamaño de clave | Descripcion |
|-----------|------|-----------------|-------------|
| **ECDH** | Negociacion de clave | 200-800 bits | Version de Diffie-Hellman sobre curvas elipticas. Equivalente en seguridad a RSA de 2048-8192 bits. |
| **ECDSA** | Firma digital | 200-800 bits | Version de DSA sobre curvas elipticas. Usado en TLS, Bitcoin, DNIe. |
| **EdDSA** (Ed25519) | Firma digital | 256 bits | Firma digital moderna basada en curva Edwards (Curve25519). Rapida, segura y sin riesgos de sesgo en nonces. Usada en SSH, Signal, WireGuard. |

### 5.5 Sistemas criptográficos mixtos (híbridos)

> Dado que los algoritmos asimétricos son lentos y limitan el tamaño de datos de entrada, los sistemas reales combinan ambos enfoques:

```
FLUJO HÍBRIDO ESTÁNDAR (TLS, PGP, Signal):

1. Negociación/Intercambio de clave simétrica
   └→ Diffie-Hellman o RSA para acordar/intercambiar una clave de sesión AES

2. Cifrado de datos
   └→ AES-256-GCM (simétrico) con la clave de sesión acordada
```

| Paso | Algoritmo | Propósito |
|------|-----------|-----------|
| 1 | RSA / ECDH | Intercambio o negociación segura de la clave simétrica |
| 2 | AES-GCM | Cifrado rápido y autenticado de los datos |

> **Algoritmos simetricos tipicos en sistemas mixtos:** TDES, IDEA, RC5 y AES. Para el intercambio del secreto se usa RSA o ECDH. La derivacion de la clave de sesion final se realiza mediante **HKDF** (HMAC-based Key Derivation Function).

**Ejemplo real -- Conexión HTTPS a tu banco:**
```
1. Cliente → Servidor: "Quiero TLS 1.3, soporto ECDHE + AES-256-GCM"
2. Servidor → Cliente: Certificado + ephemeral ECDH public key
3. Cliente/Servidor: ECDHE negocia secreto compartido (no transmisible)
4. Ambos derivan clave de sesión AES-256 via HKDF
5. Datos intercambiados cifrados con AES-256-GCM
```

### 5.6 Man in the Middle (MitM) en sistemas asimétricos

```
Ataque MitM básico:
Alice → [clave pública de Alice] → Mallory → [clave pública de Mallory] → Bob
Alice ← [clave pública de Mallory] ← Mallory ← [clave pública de Bob] ← Bob

Mallory descifra con su privada, lee, y recifra al destinatario real.
```

| Solución | Mecanismo |
|----------|-----------|
| **Firma de claves** | Una tercera parte de confianza firma la clave pública con su clave privada (certificados X.509). |
| **Certificados digitales** | Vinculan identidad del titular con su clave pública, firmados por una CA. |
| **Fingerprint verification** | Verificar la huella (hash) de la clave por un canal alternativo (voz, QR, presencial). |
| **Web of Trust** (PGP) | Usuarios firman las claves de otros usuarios en quien confían. |

> Se combate reforzando la **AUTENTICACIÓN**. El cifrado sin autenticación es vulnerable a MitM.

---

## 6. Firma Digital

### 6.1 Definición

> **Firma digital:** mecanismo criptográfico que permite verificar el origen (autenticación) y la integridad de un documento, con la propiedad de que el emisor no puede negar haberlo generado (no repudio). **Se realiza mediante cifrado ASIMÉTRICO de resúmenes.**

### 6.2 Proceso de firma

```
─────────────── PROCESO DE FIRMA (Emisor) ───────────────

Documento
    │
    ▼
hash(documento) ──► RESUMEN (HASH)
                        │
                        ▼
        Cifrado con CLAVE PRIVADA del firmante
                        │
                        ▼
                  FIRMA DIGITAL
                        │
                        ▼
    Documento + Firma → ENVIADO AL DESTINATARIO


─────────────── PROCESO DE VERIFICACIÓN (Receptor) ───────────────

Documento recibido               Firma recibida
    │                                  │
    ▼                                  ▼
hash(documento)                Descifrar con CLAVE
    │                           PÚBLICA del firmante
    ▼                                  │
RESUMEN CALCULADO                     ▼
    │                          RESUMEN DESCIFRADO
    │                                  │
    └────────── COMPARAR ◄─────────────┘
                    │
        ┌───────────┴───────────┐
        ▼                       ▼
    COINCIDEN               NO COINCIDEN
    ✅ Firma válida          ❌ Firma inválida
    Autenticación ✓          Documento alterado
    Integridad ✓             o firma falsificada
    No Repudio ✓
```

### 6.3 ¿Qué proporciona la firma digital?

| Dimensión | ¿La garantiza? | Explicación |
|-----------|:---:|-------------|
| **Autenticación** | ✅ | Solo el poseedor de la clave privada puede generar la firma. |
| **Integridad** | ✅ | Cualquier modificación del documento cambia el hash y la verificación falla. |
| **No Repudio** | ✅ | La clave privada está vinculada a una identidad única. El firmante no puede negar la firma. |
| **Confidencialidad** | ❌ | La firma digital NO oculta el contenido. El documento viaja en texto claro (a menos que también se cifre). |

> ⚠️ **IMPORTANTE:** La firma se genera cifrando el **resumen (hash)** con la clave **privada** del firmante, NO con la pública. No se cifra el documento entero, solo su huella.

### 6.4 Ejemplo real: Firma de documentos con DNI electrónico

```
Caso: Presentar declaración de la renta a la AEAT

1. Usuario tiene DNIe con chip criptográfico
2. El chip contiene el certificado digital y la clave privada (nunca sale del chip)
3. Al firmar la declaración:
   a. El software calcula SHA-256 del documento
   b. El chip del DNIe cifra ese hash con la clave privada RSA del titular
   c. La firma se incrusta en el documento
4. La AEAT verifica:
   a. Descifra la firma con la clave pública del titular (del certificado)
   b. Compara con SHA-256 del documento recibido
   c. Valida el certificado contra la CA raíz (FNMT)
   d. Comprueba que el certificado no esté revocado (OCSP/CRL)
```

---

## 7. Sistemas Criptográficos Horizontales vs Verticales

### 7.1 Modelo Horizontal -- Web of Trust (Telaraña de confianza)

> **Sistema horizontal:** todos los agentes están al mismo nivel de confianza. No existe una autoridad central. Cada usuario decide en quién confía firmando sus claves. La confianza es transitiva pero con ponderación personal.

```
Ejemplo de Web of Trust:

        Alice ──(firma)──► Bob ──(firma)──► Charlie
          │                   │
          └──(firma)──► Dave──┘
          
Alice confía en Dave porque ella misma firmó su clave.
Alice puede confiar en Charlie si confía en Bob y Bob firmó la clave de Charlie (confianza transitiva).
```

| Característica | Descripción |
|----------------|-------------|
| **Estructura** | Descentralizada. No hay autoridad superior. |
| **Confianza** | Cada usuario decide en quién confiar. Confianza transitiva y ponderada. |
| **Estándares/protocolos** | PGP, GPG, OpenPGP, SSH |
| **Ejemplo real** | PGP para email cifrado: los usuarios organizan key signing parties donde intercambian huellas y firman claves mutuamente. |
| **Ventaja** | Sin punto único de fallo. Privacidad. Control personal. |
| **Desventaja** | No escala a grandes poblaciones. Depende de la diligencia del usuario. |

> **Key servers en sistemas horizontales:** Los servidores de claves publicas (keyservers) son repositorios donde los usuarios de PGP/GPG suben sus claves publicas. Son **poco fiables** porque cualquiera puede subir claves falsas con cualquier identidad. No verifican la autenticidad de las claves. La verificacion depende exclusivamente de la Web of Trust.

### 7.2 Modelo Vertical -- PKI (Public Key Infrastructure)

> **Sistema vertical:** existe una jerarquía con Autoridades de Certificación (CA) en la cima que firman las claves de los niveles inferiores, estableciendo cadenas de confianza desde una raíz pre-confiable.

```
Jerarquía PKI:

              CA Raíz (Root CA)
              (ej: FNMT-RCM, DigiCert)
                    │
                    ▼
         CA Intermedia (Sub CA)
         (ej: FNMT Clase 2 CA)
                    │
                    ▼
          Certificado de usuario
          (ej: DNIe, certificado de servidor web)
```

| Característica | Descripción |
|----------------|-------------|
| **Estructura** | Jerárquica. Las CA están en la cima de la cadena de confianza. |
| **Confianza** | Los usuarios confían en las CA raíz preinstaladas en el sistema operativo/navegador. |
| **Estándares/protocolos** | SSL/TLS, S/MIME, S-HTTP, **SET** |
| **Ejemplo real** | Cuando visitas tu banco por HTTPS, tu navegador valida la cadena de certificados: servidor → CA intermedia → CA raíz (DigiCert, etc.). Si la cadena es válida y no revocada, se establece la conexión segura. |

> **PKI (Infraestructura de Clave Publica):** conjunto de CAs (Autoridades de Certificacion), CRs (Certificate Repositories), Agentes de usuario (personas, dispositivos, programas, algoritmos, certificados, etc.) que operan bajo politicas y procedimientos comunes para gestionar certificados digitales y claves publicas.

> **SET (Secure Electronic Transaction):** protocolo de seguridad para transacciones de tarjetas de credito en Internet, desarrollado por Visa y Mastercard. Utiliza PKI con certificados para autenticar a comerciantes y compradores. Prácticamente en desuso, sustituido por TLS con pasarelas de pago.

> **CA/Browser Forum (cabforum.org):** organizacion voluntaria formada por Autoridades de Certificacion y desarrolladores de navegadores que establece los requisitos y estandares que deben cumplir las CA para que sus certificados sean aceptados por los navegadores. Define las Baseline Requirements (BR) para todos los tipos de certificados.

### 7.3 Comparativa

| Aspecto | Horizontal (PGP) | Vertical (PKI/TLS) |
|---------|-------------------|---------------------|
| **Autoridad central** | No | Sí (CA) |
| **Escalabilidad** | Baja (requiere interacción personal) | Alta (automática via certificados) |
| **Ejemplos** | PGP, GPG, OpenPGP, SSH | SSL/TLS, S/MIME, S-HTTP, SET |
| **Revocación** | Key revocation certificate (publicado por el dueño) | CRL + OCSP (gestionado por la CA) |
| **Caso de uso** | Email personal, desarrolladores (firma de commits) | Web, banca online, email corporativo |

> ⚠️ **Pregunta de examen:** PGP se basa en modelo **HORIZONTAL** (Web of Trust). S-HTTP se basa en modelo **VERTICAL** (usa certificados digitales X.509).

### 7.4 Ejemplos reales

| Sistema | Modelo | Uso real |
|---------|--------|----------|
| **PGP/GPG** | Horizontal | Cifrado y firma de emails. Keybase.io integró GPG con identidades sociales. |
| **SSH** | Horizontal (TOFU) | Conexiones seguras a servidores. Trust On First Use: confía en la primera clave, verifica cambios. |
| **TLS/HTTPS** | Vertical | Toda la web segura. Certificados emitidos por CA reconocidas. |
| **S/MIME** | Vertical | Firma y cifrado de email en entornos corporativos. Certificados de CA empresariales. |
| **DNIe** | Vertical | Certificados emitidos por la FNMT (CA oficial española). |

---

## 8. Certificados Digitales

### 8.1 Definición y estructura X.509

> **Certificado digital X.509:** documento electrónico que vincula una clave pública con la identidad de su titular, firmado digitalmente por una Autoridad de Certificación (CA). Es la base de la PKI.

```
Estructura X.509 v3:

┌─────────────────────────────────────────────┐
│ Versión (v3)                                 │
│ Número de serie                              │
│ Algoritmo de firma de la CA                  │
│ Emisor (CA): CN, O, C...                     │
│ Período de validez: Desde / Hasta            │
│ Titular: CN, O, C...                         │
│ Clave pública del titular (NO la firma)      │
│ Extensiones (v3):                            │
│   - Key Usage (firma, cifrado, etc.)        │
│   - Extended Key Usage (servidor, cliente)  │
│   - Subject Alternative Name (SAN)          │
│   - CRL Distribution Points                 │
│   - Authority Key Identifier                │
│   - Subject Key Identifier                  │
│ Algoritmo de firma de la CA (repetido)      │
│ Firma digital hecha con clave PRIVADA de CA │
└─────────────────────────────────────────────┘
```

> ⚠️ **EXAMEN:** El certificado NO contiene la firma de la clave pública del usuario ni la clave privada de la CA. Contiene: clave pública del titular, datos de identidad, operaciones permitidas y la firma realizada con la clave **PRIVADA** de la CA.

### 8.2 Partes de un certificado

| Parte | Contenido |
|-------|-----------|
| **Clave pública** | La clave pública del titular del certificado. |
| **Datos de identidad** | Nombre (CN), organización (O), país (C), email. |
| **Operaciones permitidas** | Key Usage: firma digital, cifrado de clave, firma de certificados. |
| **Firma de la CA** | Cifrado con clave PRIVADA de la CA del hash del resto del certificado. |

### 8.3 Verificación de un certificado

```
Cuando visitas https://www.bancosantander.es:

1. Navegador recibe el certificado del servidor
2. Verifica la firma de la CA intermedia descifrándola con su clave pública
3. Sigue la cadena hasta la CA raíz (preinstalada en el almacén de confianza)
4. Comprueba período de validez (no caducado)
5. Verifica que el CN/SAN coincide con el dominio bancosantander.es
6. Consulta OCSP o CRL: ¿está el certificado revocado?
7. Si todo OK → candado verde 🔒 → conexión TLS
```

### 8.4 Revocación de certificados: CRL y OCSP

| Mecanismo | Funcionamiento | Ventaja | Desventaja |
|-----------|---------------|---------|------------|
| **CRL** (Certificate Revocation List) | Lista de certificados revocados firmada por la CA. El cliente la descarga periódicamente. | Simple. Offline posible. | No es tiempo real. CRL puede ser enorme. |
| **OCSP** (Online Certificate Status Protocol) | Consulta en tiempo real sobre un certificado específico. Respuesta firmada por el respondedor OCSP. | Tiempo real. Respuesta ligera. | Requiere conectividad. Revela qué sitios visitas a la CA. |
| **OCSP Stapling** | El servidor obtiene periódicamente la respuesta OCSP y la adjunta en el handshake TLS. | Privacidad (la CA no sabe qué clientes consultan). Rendimiento óptimo. | Soporte no universal. |

> **CRL:** Lista de certificados **REVOCADOS** por una Autoridad de Certificación. NO es una lista de certificados válidos, es de revocados.

### 8.5 Tipos de Autoridades de Certificación

| Tipo | Ejemplos | Características |
|------|----------|-----------------|
| **Oficiales** (gubernamentales) | FNMT (España), DNIe, CERES | Emitidas por gobiernos. Reconocimiento legal pleno. El DNIe incluye certificado cualificado de la FNMT. |
| **Comerciales** | Verisign (ahora Symantec/DigiCert), Thawte, Comodo/Sectigo, GoDaddy | Empresas privadas. Preinstaladas en navegadores y SO. Ofrecen diferentes niveles de validación (DV, OV, EV). |
| **Gratuitas** | Let's Encrypt, ZeroSSL, Buypass Go SSL | Automatizan la emisión via ACME. Solo DV (Domain Validation). Revolucionaron la web: el 90%+ de sitios HTTPS usan Let's Encrypt. |

**Ejemplo real -- Let's Encrypt:**
```
# Con certbot, obtener un certificado en 30 segundos:
sudo certbot --nginx -d mitienda.com

Proceso ACME:
1. Certbot genera par de claves
2. Certbot demuestra control del dominio (desafío HTTP-01 o DNS-01)
3. Let's Encrypt emite certificado X.509 firmado por su CA intermedia
4. Certificado válido por 90 días (renovación automática)
```

### 8.6 Generacion de certificados: evolucion historica

> **Inicialmente, certificados generados externamente:** la CA generaba el par de claves y el certificado para el usuario. Esto planteaba un **grave problema de confidencialidad**, ya que la CA conocia la clave privada del usuario.

> **Firma electronica avanzada:** la normativa exige que la **creacion de la clave publica se realice en el ordenador local del usuario** (o en dispositivo seguro bajo su control). La clave privada nunca debe salir del entorno del titular. Solo asi se garantiza el No Repudio verdadero.

> **Actualmente (2026):** Europa esta desarrollando la **Wallet Digital** (EUDI Wallet). Surge el debate sobre la **obligatoriedad del movil** (Apple/Android) como soporte unico para la identidad digital. Implicaciones de seguridad: ¿debe el usuario poder elegir donde residen sus claves?

---

## 9. OpenSSL

### 9.1 Derivación de clave desde contraseña

> **Cuando cifras con OpenSSL usando una contraseña, la clave de cifrado se deriva mediante una FUNCIÓN DE RESUMEN iterada (no mediante un cifrador simétrico o asimétrico directamente).**

```
Proceso real de derivación (EVP_BytesToKey, modo por defecto):

1. OpenSSL genera una sal aleatoria de 8 bytes
2. Clave = primer_momento MD5(contraseña + sal)
3. IV   = segundo_momento MD5(contraseña + sal + clave)
4. Se escribe "Salted__" (8 bytes) + sal (8 bytes) al inicio del archivo cifrado

NUNCA se usa un cifrador simétrico ni asimétrico para derivar la clave desde contraseña.
Se usa una función de resumen (hash) de forma iterada.
```

> ⚠️ **EXAMEN:** La derivación de clave desde contraseña en OpenSSL se hace mediante FUNCIÓN DE RESUMEN (digest) iterada, NO con cifrador simétrico ni asimétrico.

### 9.2 Tamaño de archivos cifrados

#### RC4 (cifrador de flujo)

> **RC4 es un cifrador de FLUJO.** El texto cifrado se obtiene mediante XOR continuo con un keystream. **No necesita padding** porque procesa byte a byte.

```
Tamaño documento original: 1000 bytes
Tamaño documento cifrado con RC4: 1000 bytes (IDÉNTICO)
```

#### AES-256-CBC con contraseña

> AES opera en bloques de **128 bits (16 bytes)**. Se añade cabecera "Salted__" (8 bytes) + sal (8 bytes) y **padding PKCS#7** para completar el último bloque hasta el múltiplo de 16.

```
Archivo original: 1000 bytes

Cifrado con openssl aes-256-cbc -pass pass:M1P4ss:
├─ Cabecera "Salted__" (8 bytes) + sal (8 bytes) = 16 bytes extra
├─ Datos: 1000 bytes → padding hasta próximo múltiplo de 16: 1008 bytes
└─ Total: 16 + 1008 = 1024 bytes

Regla: añade 16 bytes de cabecera + padding hasta múltiplo de 16 bytes (tamaño de bloque AES)
```

> ⚠️ **EXAMEN:** "Salted__" tiene 8 bytes, la sal tiene 8 bytes = 16 bytes de cabecera. AES tiene bloque de 128 bits = 16 bytes.

---

## 10. Protocolos de Seguridad Web

### 10.1 HTTPS (HTTP sobre SSL/TLS)

| Característica | Detalle |
|----------------|---------|
| **Definición** | HTTP sobre TLS/SSL. Proporciona confidencialidad, integridad y autenticación del servidor (y opcionalmente del cliente). |
| **¿Emplea PGP?** | ❌ NO. Usa certificados X.509 y TLS, no PGP. |
| **¿Requiere intercambio de contraseñas?** | ❌ NO. La clave de sesión se negocia mediante Diffie-Hellman o RSA. |
| **¿Precisa certificados digitales?** | ✅ SÍ. El servidor presenta certificado X.509 para autenticarse. |
| **Modelo** | **VERTICAL.** Basado en PKI con Autoridades de Certificación. |

**Ejemplo real -- Conexión a banca online:**
```
1. Escribes https://www.bancosantander.es
2. Navegador inicia handshake TLS 1.3
3. Servidor envía certificado X.509 (emitido por DigiCert, validado OV/EV)
4. Navegador valida la cadena hasta la CA raíz
5. Negociación ECDHE → clave de sesión AES-256-GCM
6. Candado verde. Comunicación cifrada. Intercambio de datos bancarios protegido.
```

### 10.2 S-HTTP (Secure HTTP)

| Característica | Detalle |
|----------------|---------|
| **Definición** | Protocolo de seguridad a nivel de aplicación (capa 7), no de transporte. Alternativa histórica a HTTPS. |
| **Modelo** | **VERTICAL.** Usa certificados digitales X.509. |
| **Estado** | Prácticamente en desuso. HTTPS (TLS) se convirtió en el estándar universal. |
| **Diferencia con HTTPS** | S-HTTP protege la capa HTTP directamente. HTTPS protege la capa de transporte (TLS). |

### 10.3 TLS 1.3

> **TLS 1.3** (RFC 8446, 2018): revisión mayor de TLS. Simplifica el handshake, elimina algoritmos obsoletos y mejora la seguridad.

| TLS 1.3 solo permite (cipher suites oficiales) | Tipo |
|------------------------------------------------|------|
| **AES-256-GCM** | AEAD (cifrado + autenticación) -- cifrador de bloque en modo flujo |
| **AES-128-GCM** | AEAD -- cifrador de bloque en modo flujo |
| **ChaCha20-Poly1305** | AEAD (alternativa a AES, rápida en CPU sin AES-NI) -- cifrador de flujo puro |
| **GOST-MGM** (en Rusia) | AEAD (algoritmo nacional ruso) -- cifrador de bloque en modo flujo |

> TLS 1.3 solo permite 3 familias de cipher suites: **2 cifradores de bloque en modo flujo (AES-GCM, GOST-MGM) y 1 cifrador de flujo puro (ChaCha20-Poly1305).**

| Eliminados en TLS 1.3 | Motivo |
|------------------------|--------|
| RC4 | Roto |
| 3DES | Obsoleto (Sweet32) |
| CBC | Padding oracle attacks |
| SHA-1 en firmas | Colisiones demostradas |
| Renegociación insegura | Triple Handshake attack |
| Compresión | CRIME/BREACH attacks |
| **Algoritmos asimétricos en modo "Anonymous"** | Permitían intercambio de clave sin autenticación del servidor (DH_anon, ECDH_anon). Vulnerables a MitM por definición. |

---

## 11. Algoritmos Probabilísticos

### 11.1 Aplicación principal: pruebas de primalidad

> **Aplicación principal de los algoritmos probabilísticos en criptografía:** determinar si un número muy grande es primo (necesario para generar claves RSA, parámetros Diffie-Hellman, etc.).

| Algoritmo | Tipo | Descripción |
|-----------|------|-------------|
| **Miller-Rabin** | Probabilístico | La prueba de primalidad más usada. Itera sobre diferentes bases. Probabilidad de error: 4⁻ᵏ tras k iteraciones. Con 40 iteraciones, probabilidad de falso positivo < 2⁻⁸⁰. |
| **Solovay-Strassen** | Probabilístico | Obsoleto. Sustituido por Miller-Rabin. |
| **Fermat** | Probabilístico | Base del resto. Detecta pseudoprimos de Fermat. Números de Carmichael la engañan. |
| **AKS** | Determinista | Primer algoritmo determinista en tiempo polinomial (2002). Demasiado lento en práctica; no sustituye a Miller-Rabin para uso real. |

```
Uso real -- Generación de claves RSA (2048 bits):

1. Generar número impar aleatorio de 1024 bits
2. Pasar filtro rápido (divisibilidad por primos pequeños)
3. Aplicar Miller-Rabin con 40 bases aleatorias
4. Si pasa → es primo con altísima probabilidad
5. Repetir para obtener p y q
6. n = p × q (módulo RSA)
```

### 11.2 Cifrado probabilístico

> Un algoritmo de cifrado es **probabilístico** (o no determinista) cuando el mismo texto claro produce diferente texto cifrado en diferentes ejecuciones. Propiedad clave: **indistinguibilidad semántica**.

| Algoritmo | ¿Probabilístico? | Mecanismo |
|-----------|:---:|-----------|
| **ElGamal** | ✅ Sí | Usa un valor aleatorio `k` distinto cada cifrado. |
| **RSA (textbook)** | ❌ No | Mismo texto claro + misma clave = mismo texto cifrado. **Por eso NUNCA se usa RSA sin padding.** |
| **RSA-OAEP** | ✅ Sí | OAEP (Optimal Asymmetric Encryption Padding) añade aleatoriedad al padding. |
| **AES-CBC** | ✅ Sí | IV aleatorio hace que mismo texto produzca diferente cifrado. |
| **AES-ECB** | ❌ No | Sin IV, mismo texto = mismo cifrado. Por eso es inseguro. |

---

## 12. Otros Conceptos

### 12.1 Biometría

> **Biometría:** autenticación basada en rasgos **fisiológicos** (huella dactilar, iris, cara, voz) o **conductuales** (forma de teclear, andar) del usuario. Se basa en "algo que se **es**".

| Factor de autenticación | Tipo | Ejemplos |
|--------------------------|------|----------|
| Conocimiento | Algo que se **sabe** | Contraseña, PIN, frase de seguridad |
| Posesión | Algo que se **tiene** | Tarjeta, token OTP, llave USB, DNIe |
| Inherencia | Algo que se **es** | Huella dactilar, iris, cara, firma manuscrita |

> ⚠️ **EXAMEN:** La biometría NO aplica seguridad por conocimiento (eso son las contraseñas). La biometría es "algo que se es" (factor de inherencia). Además, tiene problemas de seguridad únicos: los rasgos biométricos no se pueden revocar (no puedes cambiar tus huellas si son comprometidas).

> ⚠️ **La biometria se basa en seguridad a traves de la oscuridad** y por tanto NO es un estandar en seguridad de la informacion. No sigue el principio de Kerckhoffs: los rasgos biometricos no son secretos (dejas huellas en todas partes, tu cara es publica). La seguridad depende de la dificultad de replicar el rasgo, no de un secreto protegido criptograficamente.

### 12.2 Esteganografía

> **Esteganografía:** técnica que oculta la existencia misma del mensaje dentro de otro soporte (imagen, audio, video, texto). Se basa en el principio de **seguridad por oscuridad**. **NO es un estándar en Seguridad de la Información.**

```
Ejemplo clásico -- Esteganografía en imágenes PNG:

1. Tienes una imagen PNG de 1024×768 píxeles
2. Cada píxel = 3 bytes (RGB)
3. Modificas el bit menos significativo (LSB) de cada byte
4. El ojo humano no percibe la diferencia visual
5. Esos bits forman el mensaje oculto

Herramientas: steghide, OpenStego, outguess
```

| Criptografía | Esteganografía |
|--------------|----------------|
| Oculta el **contenido** | Oculta la **existencia** del mensaje |
| Es estándar en SI | **NO** es estándar en SI |
| Seguridad por Kerckhoffs (secreto de la clave) | Seguridad por oscuridad (secreto del método) |
| Uso: TLS, PGP, Signal, blockchain | Uso: marcas de agua, canales encubiertos |

> ⚠️ **La esteganografía se basa en seguridad por oscuridad**, principio opuesto al de Kerckhoffs. No debe confundirse con criptografía. No es un estándar reconocido en los sistemas formales de Seguridad de la Información.

> **Marcas de agua (watermarking):** aplicacion practica de la esteganografia. Se incrusta informacion oculta (copyright, autor, origen) en imagenes, audio o video de forma imperceptible pero resistente a manipulaciones. Usado en proteccion de propiedad intelectual y trazabilidad de documentos filtrados.

### 12.3 Seguridad en entorno local

> **Tres alternativas de cifrado local** para proteger datos en reposo:

| Alternativa | Descripcion |
|-------------|-------------|
| **Cifrado de Pendrives con hardware** | Dispositivos USB con cifrado integrado en el propio hardware (controladora). La clave nunca sale del dispositivo. |
| **Cifrado de volumenes de usuario** | Cifrado a nivel de particion o volumen logico (LUKS en Linux, BitLocker en Windows, FileVault en macOS). Protege los datos del usuario mientras el sistema esta apagado. |
| **Cifrado de discos de sistema** | Cifrado completo del disco (FDE -- Full Disk Encryption) incluyendo sistema operativo. El arranque requiere autenticacion previa (pre-boot authentication). |

> **Cifrado de contrasenias vs Cifrado de claves:**
> - **Cifrado de contrasenias:** se almacenan como **resumenes** (hashes) con sal. Nunca se cifran reversiblemente porque no se necesita recuperar la contrasena original, solo verificarla.
> - **Cifrado de claves:** las claves criptograficas privadas se protegen con **passphrases** (frases de paso) que las cifran simetricamente en disco. Cuando se necesitan, se descifran temporalmente en memoria.

### 12.4 Seguridad WiFi

> **Redes Inalambricas:** Siempre son **promiscuas** y por tanto, **inseguras** por naturaleza. Las seniales de radio se propagan mas alla del perimetro fisico y cualquier dispositivo dentro del alcance puede capturar el trafico.

> **Actualmente WiFi esta desplazando a redes mas seguras (Ethernet)** en entornos corporativos y domesticos, lo que incrementa la superficie de ataque. La comodidad prevalece sobre la seguridad en muchos despliegues.

| Estandar | Modos | Caracteristicas |
|----------|-------|-----------------|
| **WPA** | **Personal** | Basado en contrasenas compartidas (PSK). Todos los dispositivos usan la misma clave. Vulnerable a ataques de diccionario sobre la contrasena. |
| **WPA** | **Empresarial** | Basado en autenticacion via servidor **RADIUS** (802.1X). Cada usuario tiene credenciales propias. Mayor seguridad y trazabilidad. |
| **WPA3** | -- | **Mejora la negociacion de claves** (SAE -- Simultaneous Authentication of Equals, reemplaza PSK) y la **integracion de dispositivos IoT** (Wi-Fi Easy Connect via QR). Protege contra ataques de diccionario offline. |

### 12.5 SSH y PGP

> **SSH (Secure Shell):** reemplaza rlogin, telnet, ftp y rsh por versiones cifradas. Proporciona confidencialidad, integridad y autenticacion en conexiones remotas. Usa modelo **horizontal** (TOFU -- Trust On First Use).

**PGP (Pretty Good Privacy):** evolucion historica:

| Epoca | Hito |
|-------|------|
| 1991 | Phil Zimmermann crea PGP. Primer sistema de cifrado accesible al publico general. |
| 1990s | **PGPi** (PGP internacional): version abierta desarrollada fuera de EE.UU. para evitar restricciones de exportacion de criptografia. |
| Finales 1990s | **Obsolescencia de PGPi** al liberalizarse las leyes de exportacion y surgir estandares abiertos. |
| Actualidad | **OpenPGP** (RFC 4880) como estandar abierto y **GnuPG** (GPG) como implementacion libre. |

> **PGP/Mime:** requisito para la comunicacion de incidentes por correo a **CERTs gubernamentales**. Permite cifrar y firmar correos electronicos con formato MIME, asegurando la confidencialidad y autenticidad de los reportes de incidentes.

> **Firma de distribuciones de software abierto:** Linux (kernel), FreeBSD y otras distribuciones firman sus releases con GPG. Los usuarios verifican la firma antes de instalar para garantizar que el software no ha sido manipulado.

**TLS vs SSH -- Modelos complementarios:**

| Aspecto | TLS | SSH |
|---------|-----|-----|
| **Proposito** | Seguridad entre transporte y aplicacion | Seguridad entre componentes software |
| **Modelo** | **Sistema VERTICAL** (PKI, CAs, certificados X.509) | **Sistema HORIZONTAL** (TOFU, claves intercambiadas directamente) |
| **Caso de uso** | HTTPS, SMTPS, IMAPS, FTPS | Administracion remota, tuneles, transferencia de archivos (SFTP) |

> **SSH provee seguridad entre componentes software en sistema HORIZONTAL, TLS entre transporte y aplicacion sobre sistema VERTICAL.** Son complementarios y cubren diferentes capas y modelos de confianza.

### 12.6 IPSec y VPN

> **IPSec (IP Security):** conjunto de protocolos que proporcionan seguridad a nivel de capa de red (IP). Protege la carga util de los paquetes IP.

**Tres componentes fundamentales de IPSec:**

| Componente | Funcion |
|------------|---------|
| **AH** (Authentication Header) | Proporciona integridad y autenticacion de los paquetes IP. NO cifra el contenido. Protege contra suplantacion y modificacion. |
| **ESP** (Encapsulating Security Payload) | **Cifra la carga util** de los paquetes IP. Proporciona confidencialidad, integridad y autenticacion opcional. |
| **IKE** (Internet Key Exchange) | Protocolo de negociacion de claves. Establece las asociaciones de seguridad (SA) necesarias para AH y ESP. Usa Diffie-Hellman. |

**Modos de operacion IPSec:**

| Modo | Funcionamiento | Uso tipico |
|------|----------------|------------|
| **Modo transporte** | Cifra los paquetes IP originales. Solo la carga util (payload) se cifra/protege; la cabecera IP original se mantiene. | Comunicacion extremo a extremo entre dos hosts. |
| **Modo tunel** | Encapsula el paquete IP completo dentro de otro paquete IP (IP dentro de IP). Todo el paquete original se cifra/protege. | **VPN:** conexion red-red (sucursal-oficina central) o usuario-red (teletrabajador). |

**Tecnologias VPN modernas:**

| Tecnologia | Caracteristicas |
|------------|-----------------|
| **OpenVPN** | Usa **TLS** para la negociacion de claves. Funciona sobre **TCP o UDP**. Muy flexible y ampliamente soportado. |
| **WireGuard** | Usa **protocolos fijos** (sin negociacion). Mas rapido y simple que OpenVPN. **Implantado en el kernel Linux** desde la version 5.6. Usa Curve25519, ChaCha20 y Poly1305. |

---

## Resumen para el Examen

### ❌ Errores frecuentes que debes evitar

| Afirmación INCORRECTA | Corrección |
|------------------------|------------|
| "Camellia es un algoritmo de resumen" | ❌ Camellia es un **cifrador de bloque simétrico** (como AES). |
| "RC4 es un cifrador de bloque" | ❌ RC4 es un **cifrador de flujo** (stream cipher). RC2 sí es de bloque. |
| "ECB necesita IV" | ❌ ECB es el **único modo que NO usa IV**. Por eso bloques iguales producen cifrado igual. |
| "La firma digital se hace con cifrado simétrico" | ❌ La firma digital usa **cifrado asimétrico** (clave privada para firmar). |
| "La firma digital cifra el documento entero" | ❌ La firma digital **cifra el resumen (hash)** del documento, no el documento completo. |
| "La sal protege contra ataques de cumpleaños" | ❌ La sal protege contra **diccionario y rainbow tables**. No afecta a la paradoja del cumpleaños. |
| "PGP se basa en modelo vertical (PKI)" | ❌ PGP se basa en modelo **HORIZONTAL** (Web of Trust). S-HTTP/SSL sí son verticales. |
| "RSA es un cifrador de bloque" | ❌ RSA es **asimétrico**. Los conceptos bloque/flujo son del cifrado simétrico. |
| "El certificado contiene la clave privada de la CA" | ❌ Contiene la **firma hecha con** la clave privada de la CA, pero NO la clave privada en sí. |
| "La derivación de clave en OpenSSL usa cifrador simétrico" | ❌ Usa **función de resumen (digest) iterada**, no cifrador. |
| "Diffie-Hellman transmite claves" | ❌ DH **negocia** un secreto compartido. En ningún momento se transmite la clave. |
| "TLS/HTTPS usa PGP" | ❌ HTTPS usa **certificados X.509 y TLS**, no tiene relación con PGP. |
| "La biometría es un estándar de seguridad" | ❌ La biometría se basa en **seguridad por oscuridad**. NO es un estándar en SI. |
| "Todos los algoritmos asimetricos tienen patente" | ❌ **ElGamal NO fue patentado.** RSA tuvo patente hasta 2000, DH hasta 1997, Schnorr hasta 2008. |
| "SSH usa modelo vertical como TLS" | ❌ SSH usa modelo **HORIZONTAL** (TOFU). TLS usa modelo VERTICAL (PKI). |

### ✅ Checklist de conceptos clave

| # | Concepto | Respuesta correcta |
|---|----------|-------------------|
| 1 | ¿Qué garantiza el hash? | **Integridad** |
| 2 | ¿Qué garantiza HMAC? | **Integridad + Autenticación** |
| 3 | ¿Qué garantiza el cifrado simétrico? | **Confidencialidad** |
| 4 | ¿Qué garantiza la firma digital? | **Autenticación + Integridad + No Repudio** |
| 5 | ¿Qué tamaño de bloque tiene AES? | **128 bits (siempre)** |
| 6 | ¿Qué modos necesitan IV? | **CBC, PCBC, OFB, CFB, CTR, GCM** |
| 7 | ¿Qué modos convierten bloque en flujo? | **OFB, CFB, CTR** |
| 8 | ¿En qué se basa RSA? | **Factorización de enteros** |
| 9 | ¿En qué se basa ElGamal? | **Logaritmo discreto** |
| 10 | ¿Qué es Diffie-Hellman? | **Negociación asimétrica de clave simétrica** |
| 11 | ¿Cómo se combate MitM? | **Reforzando la autenticación** (certificados, firma de claves) |
| 12 | Modelo de PGP | **Horizontal (Web of Trust)** |
| 13 | Modelo de S-HTTP y TLS | **Vertical (PKI, certificados)** |
| 14 | ¿Qué contiene un certificado X.509? | Clave pública + identidad + usos permitidos + firma de la CA |
| 15 | ¿Qué es una CRL? | **Lista de certificados revocados** |
| 16 | Algoritmos que TLS 1.3 permite | **AES-GCM, ChaCha20-Poly1305, GOST** |
| 17 | Aplicación de algoritmos probabilísticos | **Pruebas de primalidad** (Miller-Rabin) |
| 18 | ¿Cómo deriva OpenSSL clave desde contraseña? | **Función de resumen (digest) iterada** |
| 19 | Biometría = ¿algo que se...? | **Es** (inherencia, rasgos fisiológicos/conductuales) |
| 20 | Esteganografía = ¿seguridad por...? | **Oscuridad** (oculta existencia del mensaje) |
| 21 | ¿Que algoritmo NO tuvo patente? | **ElGamal** (RSA hasta 2000, DH hasta 1997, Schnorr hasta 2008) |
| 22 | Componentes de IPSec | **AH (autenticacion), ESP (cifrado), IKE (negociacion)** |
| 23 | WPA modos | **Personal (contrasenias) y Empresarial (RADIUS)** |
| 24 | SSH reemplaza a... | **rlogin, telnet, ftp, rsh** |
| 25 | ¿Que es PGP/Mime? | **Requisito para comunicacion de incidentes a CERTs gubernamentales** |

### 📐 Fórmulas y datos numéricos

| Concepto | Valor |
|----------|-------|
| Tamaño de bloque AES | 128 bits (16 bytes) |
| Claves AES | 128 / 192 / 256 bits |
| Clave DES efectiva | 56 bits |
| Clave 3DES | 112 o 168 bits |
| Clave RSA recomendada mínima | 2048 bits |
| Hash SHA-256 | 256 bits (32 bytes) |
| Hash SHA-512 | 512 bits (64 bytes) |
| Cabecera OpenSSL "Salted__" | 8 bytes texto + 8 bytes sal = 16 bytes total |
| Iteraciones PBKDF2 en WPA2 | 4096 |
| Claves ECC (ECDH/ECDSA/EdDSA) | 200-800 bits (equivalentes RSA 2048-8192 bits) |
| Valvulas Colossus (1er computador electronico) | ~1500 valvulas de vacio |
| Patente RSA | Expiro en 2000 |
| Patente DH | Expiro en 1997 |
| Patente Schnorr | Expiro en 2008 |

### 🔐 Cifrado híbrido (el flujo real)

```
1. Diffie-Hellman (asimétrico) → negociar clave de sesión
2. AES-GCM (simétrico) → cifrar datos con la clave negociada
3. HMAC/GMAC → autenticación del mensaje
```

Este es el patrón universal de la criptografía moderna: TLS, Signal, WireGuard, IPsec... todos funcionan así.

### 🔑 Algoritmos simetricos en sistemas mixtos: TDES, IDEA, RC5, AES + RSA/ECDH para intercambio de secreto + HKDF para derivacion de clave de sesion.
