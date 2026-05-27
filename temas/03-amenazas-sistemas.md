# UA 3: Amenazas a los Sistemas de Información

---

## 1. Tipos de Amenazas

Las amenazas a los sistemas de información pueden clasificarse según su origen y naturaleza:

### 1.1 Clasificación por origen

| Tipo | Descripción | Ejemplo |
|------|-------------|---------|
| **Ataques dirigidos (específicos)** | Orientados contra una organización o persona concreta | APT contra SONY (2014) |
| **Ataques indiscriminados** | Lanzados masivamente sin objetivo fijo, buscando víctimas vulnerables | Campaña de ransomware WannaCry (2017) |
| **Accidentes** | Fallos no intencionados: cortes eléctricos, errores de configuración, desastres naturales | Borrado accidental de base de datos en GitLab (2017) |
| **Negligencias (factor humano)** | Descuidos, malas prácticas, falta de formación | Dejar contraseñas en post-it, no aplicar parches de seguridad |

> **El factor humano es el eslabón más débil de la seguridad.** La mayoría de incidentes tienen su origen en negligencias o errores humanos, no en fallos técnicos.

### 1.2 Efectos de un ataque

**TODAS LAS SIGUIENTES SON CONSECUENCIAS REALES DE UN ATAQUE:**

| Efecto | Descripción |
|--------|-------------|
| **Pérdida de información** | Destrucción, cifrado o borrado de datos |
| **Pérdida de disponibilidad** | Interrupción del servicio (DDoS, ransomware) |
| **Pérdida de confidencialidad** | Fuga de datos sensibles o secretos |
| **Pérdida de intimidad/privacidad** | Exposición de datos personales |
| **Daño a la reputación** | Pérdida de confianza de clientes y socios |
| **Daños a la propiedad** | Destrucción de equipos o infraestructura |

> **PREGUNTA DE EXAMEN:** "¿Cuáles son los efectos de un ataque?" → **TODAS SON CORRECTAS**

### 1.3 Motivaciones: M.I.C.E.

| Sigla | Significado | Explicación |
|-------|-------------|-------------|
| **M** | **Money** (Dinero) | Beneficio económico: ransomware, robo de datos bancarios, fraude |
| **I** | **Ideology** (Ideología) | Hacktivismo, causas políticas o religiosas (Anonymous, ataques geopolíticos) |
| **C** | **Compromise** (Compromiso) | Obligación forzada: chantaje, extorsión, presión sobre un empleado |
| **E** | **Ego** (Ego) | Reconocimiento, desafío intelectual, fama en la comunidad |

> **Nemotécnico:** M.I.C.E. — "Money rules, Ideology drives, Compromise forces, Ego fuels"

---

## 2. Perfiles del Atacante

### 2.1 Diferencia fundamental: intención de dañar

| Perfil | Conocimientos | Intención de dañar | Motivación |
|--------|:------------:|:------------------:|------------|
| **Hacker** | Altos | **NO** | Curiosidad, desafío intelectual, aprendizaje |
| **Cracker** | Altos | **SÍ** | Beneficio económico, venganza, malicia |
| **Script kiddie** | Bajos | **SÍ** | Diversión, molestar, sentirse poderoso |
| **Phreaker** | Medios/Altos | Variable | Interés en sistemas telefónicos |
| **Carder** | Medios | **SÍ** | Robo y tráfico de tarjetas de crédito |
| **(Ex)Empleados** | Variables | **SÍ** (a menudo) | Venganza, beneficio económico |

> **PREGUNTA CLAVE DE EXAMEN:** La diferencia entre hacker y cracker es la **intención de dañar**.
> - Hacker: conocimientos técnicos, **sin** intención de dañar
> - Cracker: conocimientos técnicos, **con** intención de dañar

### 2.2 Descripciones detalladas

- **Hacker:** Persona con profundos conocimientos técnicos que explora sistemas por curiosidad intelectual y afán de aprendizaje. El término original (años 60-70 en el MIT) era positivo. Los medios de comunicación han distorsionado su significado.
- **Cracker:** Individuo con conocimientos técnicos que vulnera sistemas con fines maliciosos: robo, destrucción, extorsión.
- **Script kiddie:** Persona sin conocimientos técnicos profundos que utiliza herramientas y exploits creados por otros. Poco sofisticados pero peligrosos por su número.
- **Phreaker:** Especialista en sistemas de telecomunicaciones (phreaking = phone + freak). Históricamente relevantes (Captain Crunch, blue boxes).
- **Carder:** Dedicado al robo, clonación y venta de tarjetas de crédito en foros clandestinos.
- **(Ex)Empleados:** Amenaza interna. Conocen los sistemas, tienen accesos legítimos y pueden actuar por venganza, despido o soborno.

---

## 3. El Activo Más Importante

> **La INFORMACIÓN es el activo más importante de una organización.**
>
> No son los beneficios económicos, ni la seguridad física, ni los empleados. Todo lo demás es secundario o deriva de la información.

La seguridad de la información se basa en el **trinomio CIA**:

| Pilar | Inglés | Significado |
|-------|--------|-------------|
| **Confidencialidad** | Confidentiality | Solo acceden personas autorizadas |
| **Integridad** | Integrity | La información no se altera sin autorización |
| **Disponibilidad** | Availability | Accesible cuando se necesita |

---

## 4. Cookies

> **DEFINICIÓN:** Fragmento de información que se almacena en el disco duro del visitante a petición del servidor web.

### 4.1 Lo que las cookies NO son

| Afirmación falsa | Realidad |
|------------------|----------|
| ❌ "Son código publicitario" | Son archivos de texto con datos, no código ejecutable |
| ❌ "Son necesariamente maliciosas" | La mayoría son legítimas y necesarias (sesión, carrito, preferencias) |
| ❌ "Son una página web en caché" | No almacenan páginas completas, sino pequeños fragmentos de información |

### 4.2 Tipos de cookies problemáticas

| Tipo | Descripción |
|------|-------------|
| **Cookies espía (tracking cookies)** | Rastrean la actividad del usuario entre sitios web para crear perfiles publicitarios (third-party cookies) |
| **Cookies tóxicas** | Cookies maliciosas que capturan datos sensibles o modifican el comportamiento del navegador |

### 4.3 Problemas de privacidad

- Las cookies de terceros (third-party) permiten a anunciantes construir perfiles detallados de navegación.
- Regulaciones como el **RGPD** (Reglamento General de Protección de Datos) y la **ePrivacy Directive** exigen consentimiento explícito para cookies no esenciales.
- Los banners de cookies que aparecen en los sitios web son consecuencia directa de esta regulación.

---

## 5. Malware (Software Malicioso)

### 5.1 Clasificación según mecanismo de propagación

#### 5.1.1 Virus

> Software malicioso que **necesita intervención humana** para propagarse. Se adjunta a un archivo o programa legítimo (host).

- **Vías de infección:** Adjunto de email, USB infectado, descarga de software, ejecución de un archivo.
- **No se propaga solo:** Requiere que el usuario ejecute, abra o copie el archivo infectado.

#### 5.1.2 Gusano (Worm)

> Software malicioso que se propaga **AUTOMÁTICAMENTE** por la red, **sin intervención humana**.

| Característica | Virus | Gusano (Worm) |
|---------------|-------|---------------|
| Propaga automáticamente | No | **Sí** |
| Necesita intervención humana | Sí | **No** |
| Necesita archivo host | Sí | No necesariamente |
| Explota vulnerabilidades de red | No típicamente | **Sí** |

> **PREGUNTA DE EXAMEN:** La diferencia clave entre virus y gusano es que el gusano se propaga automáticamente sin intervención humana.

**Ejemplo real: Stuxnet (2010)**
- Gusano diseñado para sabotear centrifugadoras nucleares iraníes.
- Se propagaba automáticamente por redes Windows y USB.
- Atribuido a EE.UU. e Israel (Operación Olympic Games).
- Primer malware conocido diseñado para causar daños físicos a infraestructura industrial (SCADA).

**Ejemplo real: Conficker (2008)**
- Gusano que infectó millones de ordenadores explotando una vulnerabilidad de Windows.
- Creó una de las botnets más grandes de la historia.

#### 5.1.3 Troyano (Trojan)

> Software que se **camufla como legítimo** para engañar al usuario y ejecutar acciones maliciosas.

**Vías de entrada (TODAS SON CORRECTAS):**
- Descarga arrastrada por otro malware (dropper)
- Adjunto en correo electrónico
- Visita a una web maliciosa (drive-by download)
- Descarga de software de fuentes no confiables
- Ingeniería social (falsas actualizaciones, codecs, etc.)

> **PREGUNTA DE EXAMEN:** "¿Cuáles son las vías de entrada de un troyano?" → **TODAS LAS RESPUESTAS SON CORRECTAS**

### 5.2 Clasificación según comportamiento

#### 5.2.1 Rootkits

> Software que **sustituye componentes del sistema operativo** para ocultar su presencia y la de otro malware.

- **NO es** un virus, ni un gusano, ni un troyano per se (aunque puede combinarse con cualquiera de ellos).
- Opera a nivel de kernel o de aplicación para interceptar llamadas al sistema.
- Extremadamente difícil de detectar con antivirus convencionales.

**Ejemplo real: Sony BMG Rootkit (2005)**
- Sony incluyó un rootkit en CDs de música como "protección anticopia".
- Se instalaba sin consentimiento al reproducir el CD en un PC.
- Ocultaba archivos y procesos, y debilitaba la seguridad del sistema.
- Escándalo masivo que obligó a Sony a retirar los CDs.

#### 5.2.2 Backdoors y Downloaders

| Tipo | Función |
|------|---------|
| **Backdoor (puerta trasera)** | Permite acceso remoto no autorizado al sistema, sorteando la autenticación normal |
| **Downloader** | Descarga e instala malware adicional en el sistema comprometido. Suele ser la primera etapa de una infección |

#### 5.2.3 Spyware, PWStealers, Keyloggers

| Tipo | Función |
|------|---------|
| **Spyware** | Espía la actividad del usuario sin su consentimiento: hábitos de navegación, aplicaciones usadas, datos del sistema |
| **PWStealer** | Especializado en robar contraseñas almacenadas en navegadores, clientes FTP, gestores de correo |
| **Keylogger** | Registra todas las pulsaciones del teclado, capturando contraseñas, conversaciones, números de tarjeta |

#### 5.2.4 Bots y Botnets

> **Bot:** Programa que ejecuta tareas automatizadas bajo control remoto.
> **Botnet:** Red de ordenadores infectados (zombis) controlados por un atacante (botmaster).

**Aplicaciones maliciosas de las botnets:**

| Uso | Descripción |
|-----|-------------|
| **DDoS** | Ataques distribuidos de denegación de servicio |
| **Spam masivo** | Envío de millones de correos basura |
| **Minado de criptomonedas** | Uso de CPU/GPU de las víctimas para minar sin su conocimiento |
| **Robo de datos** | Captura y exfiltración de información |
| **Proxy malicioso** | Usar las máquinas zombi para anonimizar otras actividades delictivas |

**Ejemplo real: Mirai Botnet (2016)**
- Infectó dispositivos IoT (cámaras IP, routers) usando contraseñas por defecto.
- Lanzó ataques DDoS récord (~1 Tbps) contra Dyn DNS, tumbando Twitter, Netflix, Reddit, etc.

#### 5.2.5 Adware, Clickers, Secuestradores de Web

| Tipo | Función |
|------|---------|
| **Adware** | Muestra publicidad no deseada (pop-ups, banners inyectados) |
| **Clicker** | Realiza clics automáticos en anuncios para generar ingresos fraudulentos |
| **Secuestrador de web (browser hijacker)** | Modifica la página de inicio, buscador por defecto o redirige el tráfico del navegador |

#### 5.2.6 Ransomware (Criptovirus)

> Malware que **secuestra la información** (normalmente cifrándola) y exige un **rescate económico** para recuperarla.

- El rescate se suele exigir en criptomonedas (Bitcoin, Monero) para dificultar el rastreo.
- **Afecta especialmente a la política de copias de seguridad:** si hay backups actualizados y aislados, el impacto se minimiza.

**Ejemplo real: WannaCry (12 de mayo de 2017)**

| Aspecto | Detalle |
|---------|---------|
| **Vector** | Explotó la vulnerabilidad EternalBlue (MS17-010) en Windows SMBv1 |
| **Propagación** | Se propagaba como un gusano automáticamente por la red |
| **Impacto** | +200.000 equipos en +150 países en menos de 24 horas |
| **Víctimas destacadas** | NHS británico (hospitales paralizados) |
| **Rescate** | $300 en Bitcoin, luego $600 |
| **Fallo de diseño** | Tenía un "kill switch" (dominio no registrado) que un investigador (MalwareTech) activó accidentalmente |

**Ejemplo real: NotPetya (2017, vinculado a Rusia)**
- Parecía ransomware pero era un **wiper** (destructor de datos disfrazado). Cifraba sin posibilidad de recuperación.

**Ejemplo real: CryptoLocker (2013)**
- Uno de los primeros ransomware modernos con cifrado asimétrico. Infectó ~250.000 sistemas.

#### 5.2.7 Killers y Bombas Lógicas

| Tipo | Función |
|------|---------|
| **Killer** | Malware diseñado para desactivar otros malware o software de seguridad (antivirus, firewall). A veces usado en "guerras" entre grupos criminales |
| **Bomba lógica** | Código malicioso que permanece latente hasta que se cumple una condición (fecha, evento, orden remota) |

**Ejemplo real: Bomba lógica en SIEMENS (ex-empleado)**
- Un ex-empleado programó una bomba lógica que se activó tras su despido, causando daños en sistemas de control industrial.

---

## 6. Ataques Específicos

### 6.1 Denegación de Servicio Distribuido (DDoS)

> **Definición:** Conjunto de máquinas (botnet) que saturan con peticiones al sistema víctima hasta dejarlo fuera de servicio.

- **NO es** distribuir contraseñas entre atacantes.
- **NO es** distribuir el trabajo entre varios hackers.

| Objetivo | Cómo funciona |
|----------|---------------|
| **Agotar el ancho de banda** | Inundar la red con tráfico masivo (ataques volumétricos) |
| **Agotar recursos del servidor** | Consumir CPU, memoria o conexiones (SYN flood, HTTP flood) |
| **Agotar recursos de aplicación** | Peticiones lentas que mantienen conexiones abiertas (Slowloris) |

**Ejemplo real: Ataque DDoS a la banca española (2022-2023)**
- Grupos prorrusos (Killnet, NoName057) lanzaron ataques DDoS masivos contra bancos y administraciones españolas tras el apoyo a Ucrania.

### 6.2 Inyección SQL (SQL Injection — SQLi)

> **Definición:** Técnica que inserta código SQL malicioso en las entradas de una aplicación web para manipular la base de datos.

- **Se evita FILTRANDO TODAS LAS ENTRADAS** a la aplicación web (en el código de la app).
- **NO se evita** con suite antivirus, ni con firewalls (aunque un WAF ayuda como capa adicional).
- La mitigación correcta es: **consultas parametrizadas / prepared statements** y validación de inputs.

```
Ejemplo clásico de inyección:
Entrada: ' OR '1'='1' --
Resultado: SELECT * FROM users WHERE user='' OR '1'='1' -- ' AND password='...'
           → Devuelve TODOS los usuarios (autenticación saltada)
```

**Ejemplo real: TalkTalk (2015)**
- Ataque de SQL injection a la operadora británica. Datos de 157.000 clientes expuestos. Multa récord de £400.000.

### 6.3 Phising (Suplantación por correo)

> **Definición:** Suplantación de identidad mediante correo electrónico fraudulento para obtener credenciales, datos bancarios o información sensible.

- El correo imita a una entidad legítima (banco, RRSS, administración pública).
- Incluye un enlace a una web falsa que copia el aspecto de la original.

**Técnicas comunes:**
- **Spear phising:** dirigido a una persona u organización concreta.
- **Whaling:** dirigido a altos directivos (CEOs, CFOs).
- **Smishing:** phising vía SMS.
- **Vishing:** phising vía llamada telefónica.

### 6.4 Pharming

> **Definición:** Intoxicación o envenenamiento del DNS para redirigir a los usuarios a una web maliciosa sin que lo sepan.

| Técnica | Cómo funciona |
|---------|---------------|
| **DNS Cache Poisoning** | Se corrompe la caché de un servidor DNS para que devuelva IPs falsas |
| **Modificación del archivo HOSTS** | En el equipo local, se modifica HOSTS para asociar dominios legítimos a IPs maliciosas |

**Diferencia clave con Spoofing:**
- **Pharming:** Redirige el tráfico modificando el sistema de resolución de nombres (DNS, HOSTS). Afecta a muchos usuarios a la vez.
- **Spoofing:** Suplanta una identidad (IP, DNS, Web) emitiendo paquetes falsos.

### 6.5 Spoofing (Suplantación)

| Tipo | Descripción |
|------|-------------|
| **IP Spoofing** | Falsificar la dirección IP de origen de los paquetes |
| **DNS Spoofing** | Falsificar respuestas DNS para redirigir tráfico |
| **Web Spoofing** | Crear una réplica de un sitio web legítimo |
| **ARP Spoofing** | Falsificar la tabla ARP para interceptar tráfico en red local (Man-in-the-Middle) |

### 6.6 Rootkit (ataque)

Ver sección 5.2.1. En el contexto de ataques, un rootkit es tanto el software como el resultado de una intrusión profunda en el sistema.

### 6.7 XSS (Cross-Site Scripting)

> **Definición:** Inyección de código JavaScript malicioso en páginas web vistas por otras víctimas.

| Tipo | Descripción | Persistencia |
|------|-------------|:------------:|
| **XSS Reflejado (No persistente)** | El script se envía en la petición HTTP y se refleja en la respuesta inmediatamente. Requiere que la víctima haga clic en un enlace manipulado | No |
| **XSS Almacenado (Persistente)** | El script se almacena en el servidor (ej. en un comentario, perfil) y se ejecuta cada vez que un usuario visita la página afectada | **Sí** |
| **XSS basado en DOM** | La manipulación ocurre en el lado del cliente mediante JavaScript que modifica el DOM | No |

### 6.8 APT (Amenaza Avanzada y Persistente — Advanced Persistent Threat)

> **Definición:** Ataque prolongado y dirigido en el que un actor altamente capacitado (a menudo estatal) se infiltra en una red y permanece oculto durante meses o años.

**Características:**
- **Avanzada:** Usa técnicas sofisticadas, exploits de día cero, malware a medida.
- **Persistente:** Mantiene acceso duradero, extrayendo información progresivamente.
- **Amenaza:** Actores con recursos: estados-nación, grupos de ciberespionaje.

**Ejemplo real: Ataque APT a SONY Pictures (2014)**

| Aspecto | Detalle |
|---------|---------|
| **Atacante** | Grupo "Guardians of Peace", atribuido a Corea del Norte |
| **Motivación** | Represalia por la película "The Interview" (sátira sobre Kim Jong-un) |
| **Técnicas** | Malware destructivo (wiper), robo masivo de datos, filtración de correos internos |
| **Impacto** | 100 TB de datos robados, filtración de emails de ejecutivos, paralización total de la red corporativa durante semanas |
| **Datos filtrados** | Películas inéditas, datos de empleados, correos comprometedores entre ejecutivos |

---

## 7. Amenazas en Distintos Ámbitos

### 7.1 Correo Electrónico

| Amenaza | Descripción |
|---------|-------------|
| **Spam** | Correo no deseado masivo. Representa aproximadamente el **90% del tráfico de correo mundial** |
| **Phising** | Suplantación de identidad para robo de credenciales |
| **Malware en adjuntos** | Archivos infectados (.doc, .pdf, .zip, .exe) enviados como adjuntos |
| **Spoofing de email** | Falsificación de la dirección de remitente (no requiere comprometer la cuenta real) |

> **PREGUNTA DE EXAMEN:** El spam supone aproximadamente el **90%** del correo electrónico mundial.

### 7.2 Web

| Amenaza | Descripción |
|---------|-------------|
| **Cookies** | Seguimiento de actividad, perfiles de navegación, privacidad |
| **Pharming** | Redirección por envenenamiento DNS |
| **XSS** | Inyección de scripts maliciosos en páginas web |
| **Black Hat SEO** | Técnicas engañosas de posicionamiento web para dirigir tráfico a sitios maliciosos: keyword stuffing, cloaking, granjas de enlaces, páginas puerta |

### 7.3 Redes Sociales

| Amenaza | Descripción |
|---------|-------------|
| **Tabnabbing** | Ataque de phishing que modifica una pestaña inactiva del navegador para que parezca una página legítima (ej. Gmail) y robe credenciales cuando el usuario vuelve a ella |
| **Clickjacking** | Ocultar elementos en los que el usuario hace clic sin saberlo (botones invisibles superpuestos) mediante iframes transparentes. El usuario cree que hace clic en un "Me gusta" pero realmente está haciendo clic en otra cosa |
| **Gusanos en RRSS** | Malware que se propaga automáticamente mediante mensajes, publicaciones o etiquetas (ej. Koobface en Facebook) |
| **Cookies maliciosas** | Robo de sesión, seguimiento no consentido |
| **Riesgos de privacidad** | Sobreexposición de información personal, scraping de datos, ingeniería social, suplantación de identidad |

**Ejemplo real: Cambridge Analytica (2018)**
- Datos de 87 millones de usuarios de Facebook recolectados sin consentimiento a través de una app de test de personalidad.
- Usados para crear perfiles psicológicos y dirigir publicidad política en Brexit y elecciones de EE.UU. 2016.

### 7.4 Cloud Computing

> La nube implica **externalizar el activo más importante** (la información) a un tercero.

| Riesgo / Requisito | Descripción |
|--------------------|-------------|
| **Externalización de la información** | Los datos dejan de estar bajo control físico directo de la organización |
| **RGPD** | Obligatorio cumplimiento del Reglamento General de Protección de Datos (UE 2016/679). Requiere garantías sobre tratamiento de datos personales en la nube |
| **Nubes cifradas** | El cifrado debe aplicarse tanto en tránsito (TLS) como en reposo. Idealmente con claves gestionadas por el cliente (no por el proveedor cloud) |
| **Residencia de datos** | Los datos deben residir en jurisdicciones que cumplan la normativa aplicable. Muchos proveedores cloud ofrecen regiones específicas (EU, US, etc.) |

**Responsabilidad compartida en cloud:**
- El proveedor cloud asegura la infraestructura.
- El cliente es responsable de la seguridad de sus datos, accesos y configuraciones.
- Un bucket S3 mal configurado es responsabilidad del cliente, no de AWS.

### 7.5 WiFi Doméstico

| Riesgo | Descripción |
|--------|-------------|
| **WEP** | Protocolo de cifrado obsoleto y **roto**. Se puede descifrar en minutos con herramientas como Aircrack-ng. **NO usar nunca** |
| **WPS (WiFi Protected Setup)** | Sistema de configuración simplificada con PIN. **Peligroso:** el PIN de 8 dígitos es vulnerable a fuerza bruta (solo 11.000 intentos en lugar de 100 millones) |
| **Contraseñas por defecto** | Muchos routers vienen con SSID y contraseña predefinidos. Si no se cambian, son objetivo fácil de ataques de diccionario |
| **Router como puerta de enlace** | Un router comprometido permite al atacante interceptar, redirigir o modificar todo el tráfico de la red doméstica |

**Buenas prácticas WiFi:**
- Usar **WPA3** o al menos **WPA2-AES** (nunca WEP, nunca WPA-TKIP).
- Desactivar WPS.
- Cambiar SSID y contraseña por defecto.
- Mantener el firmware del router actualizado.
- Crear una red de invitados separada para dispositivos IoT.

---

## 8. Ataques Elaborados

### 8.1 Escaneo de Puertos e Identificación de Vulnerabilidades

> Fase de reconocimiento: el atacante explora el objetivo para identificar puertos abiertos, servicios en ejecución y versiones, buscando vulnerabilidades conocidas.

| Herramienta | Uso |
|-------------|-----|
| **Nmap** | Escáner de puertos y servicios. Permite identificar sistema operativo, versiones de software y puertos abiertos |
| **Nessus, OpenVAS** | Escáneres de vulnerabilidades. Comparan versiones detectadas con bases de datos de CVEs |
| **Metasploit** | Framework de explotación. Permite lanzar exploits contra vulnerabilidades identificadas |

### 8.2 Eavesdropping y Sniffing

| Técnica | Descripción |
|---------|-------------|
| **Eavesdropping** | Escucha pasiva de comunicaciones sin autorización. En redes no cifradas (HTTP, FTP, Telnet) los datos viajan en texto plano |
| **Sniffing** | Captura y análisis de paquetes de red mediante herramientas como Wireshark o tcpdump |
| **Man-in-the-Middle (MitM)** | El atacante se interpone entre dos partes que se comunican, pudiendo leer y modificar el tráfico. ARP Spoofing en redes locales |

**Defensas:** Usar siempre protocolos cifrados (HTTPS/TLS, SSH en lugar de Telnet, SFTP en lugar de FTP).

### 8.3 Google Hacking (Google Dorks)

> Uso de operadores avanzados de búsqueda de Google para encontrar información sensible expuesta inadvertidamente.

| Operador | Ejemplo | Qué encuentra |
|----------|---------|---------------|
| `site:` | `site:example.com` | Resultados solo de ese dominio |
| `filetype:` | `filetype:pdf confidencial` | Archivos de un tipo concreto |
| `intitle:` | `intitle:"webcam" inurl:view` | Cámaras web expuestas |
| `inurl:` | `inurl:admin` | Paneles de administración |
| `ext:` | `ext:sql "password"` | Backups de bases de datos SQL expuestos |

**Ejemplo real:** La base de datos GHDB (Google Hacking Database) mantiene miles de "dorks" que localizan desde cámaras IP sin protección hasta archivos con contraseñas.

### 8.4 Ingeniería Social

> **El punto más débil de cualquier sistema de seguridad es el ser humano.**

La ingeniería social es el arte de manipular a las personas para que revelen información confidencial o realicen acciones que comprometan la seguridad.

| Técnica | Descripción |
|---------|-------------|
| **Pretexting** | Crear un escenario falso para obtener información (hacerse pasar por soporte técnico) |
| **Baiting** | Dejar un cebo físico (USB infectado etiquetado como "Nóminas 2024" en el parking) |
| **Quid pro quo** | Ofrecer algo a cambio de información (falso soporte técnico que pide credenciales "para ayudar") |
| **Tailgating** | Seguir físicamente a alguien autorizado para acceder a una zona restringida |

**Ejemplo real: Kevin Mitnick**
- Uno de los hackers más famosos de los 80-90. Usaba principalmente ingeniería social, no exploits técnicos complejos. Conseguía contraseñas y accesos convenciendo a empleados por teléfono.

**Ejemplo real: Twitter Bitcoin Scam (2020)**
- Un joven de 17 años usó ingeniería social (vishing) contra empleados de Twitter para acceder a herramientas internas.
- Secuestró cuentas verificadas de Elon Musk, Barack Obama, Bill Gates y otras para publicar una estafa de Bitcoin.
- Beneficio: ~$117.000 en Bitcoin.

### 8.5 IA y LLMs como Vector de Ataque

La inteligencia artificial generativa ha transformado el panorama de amenazas:

| Vector | Descripción |
|--------|-------------|
| **Phising hiperrealista** | LLMs generan emails de phishing sin errores ortográficos ni gramaticales, en múltiples idiomas, imitando estilos corporativos |
| **Deepfakes** | Suplantación de voz e imagen. En 2024, un empleado de una multinacional en Hong Kong transfirió $25M tras una videollamada deepfake con el falso CFO |
| **Generación de malware** | LLMs pueden generar código malicioso, variantes de malware polimórfico, y ayudar a programar exploits |
| **Automatización de ataques** | IA para escaneo inteligente, selección de víctimas, personalización de ataques a escala |
| **Envenenamiento de datos** | Comprometer los datos de entrenamiento de modelos de IA para introducir comportamientos maliciosos |
| **Prompt injection** | Manipular LLMs para que ignoren sus restricciones de seguridad |

---

## 9. CVE, CVSS y NVD

### 9.1 CVE (Common Vulnerabilities and Exposures)

> **Identificador estándar común de vulnerabilidades**, mantenido por **MITRE Corporation**.

- Formato: `CVE-AAAA-NNNNN` (ej. `CVE-2021-44228` — Log4Shell).
- Cada CVE identifica una vulnerabilidad de forma única e inequívoca.
- Permite que distintas herramientas y bases de datos hablen el mismo lenguaje.
- No incluye puntuación de gravedad (eso es CVSS).

### 9.2 CVSS (Common Vulnerability Scoring System)

> **Sistema de puntuación numérica** que evalúa la gravedad de una vulnerabilidad en una escala de **0 a 10**.

| Puntuación | Nivel de gravedad |
|:----------:|-------------------|
| 0.0 | Ninguna (None) |
| 0.1 – 3.9 | Baja (Low) |
| 4.0 – 6.9 | Media (Medium) |
| 7.0 – 8.9 | Alta (High) |
| 9.0 – 10.0 | **Crítica (Critical)** |

- **CVSS v4.0** se publicó en noviembre de 2023, entrando en uso en **2024**.
- Métricas evaluadas:
  - **Base:** Características intrínsecas de la vulnerabilidad (exploitabilidad, impacto).
  - **Temporal:** Factores que cambian con el tiempo (disponibilidad de exploit, parches).
  - **Environmental:** Factores específicos del entorno de la organización afectada.

### 9.3 NVD (National Vulnerability Database)

> Base de datos nacional de vulnerabilidades de EE.UU., gestionada por el **NIST** (National Institute of Standards and Technology).

- **Enriquece los CVEs** con puntuaciones CVSS, referencias, clasificaciones CWE y metadatos adicionales.
- Es la fuente de referencia mundial para consultar vulnerabilidades.
- URL: https://nvd.nist.gov

### 9.4 CNAs (CVE Numbering Authorities)

Organizaciones autorizadas para asignar identificadores CVE en sus ámbitos:

| CNA | Ámbito |
|-----|--------|
| **MITRE** | CNA raíz y coordinador general |
| **ENISA** | Agencia de Ciberseguridad de la Unión Europea |
| **INCIBE** | Instituto Nacional de Ciberseguridad de España |
| **Microsoft, Apple, Google...** | CNAs para sus propios productos |

### 9.5 Ataques de Día Cero (Zero-Day)

> Vulnerabilidad **desconocida** para el fabricante y para la que **no existe parche** en el momento del ataque.

- Son las más peligrosas porque no hay defensa disponible.
- Se comercian en mercados clandestinos por cifras millonarias (empresas como Zerodium, grupos estatales).
- El ciclo es:
  1. Descubrimiento de la vulnerabilidad.
  2. Explotación activa (ataque día cero).
  3. Descubrimiento público por el fabricante.
  4. Desarrollo y publicación del parche.
  5. → En este punto deja de ser "día cero".
  6. El exploit se convierte en "n-day" y se integra en herramientas de ataque masivo (Metasploit, etc.).

**Ejemplo real: Log4Shell (CVE-2021-44228)**
- Vulnerabilidad en Log4j (biblioteca de logging de Java ubicua).
- Puntuación CVSS: **10.0** (crítica).
- Permitía ejecución remota de código (RCE) sin autenticación.
- Afectó a millones de sistemas: AWS, Apple iCloud, Twitter, Steam, Minecraft...

**Ejemplo real: EternalBlue (MS17-010)**
- Exploit de día cero desarrollado por la NSA, filtrado por el grupo Shadow Brokers en 2017.
- Usado por WannaCry y NotPetya.
- Demuestra el peligro de que los estados acumulen vulnerabilidades sin comunicarlas.

---

## 10. Resumen para el Examen

### Conceptos que NO pueden fallar en el examen

1. **Diferencia hacker vs cracker:** La **intención de dañar**.
2. **Diferencia virus vs gusano:** El gusano se propaga **automáticamente sin intervención humana**.
3. **El activo más importante es la INFORMACIÓN** (no los beneficios, no la seguridad, no los empleados).
4. **Una cookie es:** fragmento de información almacenado en disco duro del visitante a petición del servidor. **No es** código publicitario, no es necesariamente maliciosa, no es una página web en caché.
5. **Efectos de un ataque:** TODAS SON CORRECTAS (disponibilidad, confidencialidad, intimidad, reputación, daños a la propiedad, pérdida de información).
6. **Vías de entrada de un troyano:** TODAS SON CORRECTAS (descarga por malware, adjunto email, web maliciosa).
7. **SQL injection se evita:** Filtrando TODAS las entradas en el código de la aplicación web. **No** con suite antivirus, no solo con firewall.
8. **DDoS es:** conjunto de máquinas que saturan al sistema víctima. **No** es distribuir contraseñas, no es distribuir trabajo.
9. **Pharming es:** intoxicación/envenenamiento del DNS.
10. **Ransomware afecta especialmente a:** la **política de copias de seguridad**.
11. **El spam supone aproximadamente el 90%** del correo electrónico.
12. **M.I.C.E.:** Money, Ideology, Compromise, Ego.
13. **CVE:** Identificador estándar de vulnerabilidades (MITRE). **CVSS:** Sistema de puntuación 0-10. **NVD:** National Vulnerability Database (NIST).
14. **Rootkit:** software que sustituye componentes del SO. **No es** por definición un virus, gusano o troyano.
15. **WEP es débil, WPS es peligroso, contraseñas por defecto** en routers son un riesgo grave.
16. **La ingeniería social es el punto más débil** de la seguridad.
17. **Cloud computing:** externalizas tu activo más importante. Necesitas RGPD, cifrado y control de residencia de datos.

### Tabla rápida de diferencias clave

| Concepto A | Concepto B | Diferencia |
|------------|------------|------------|
| Hacker | Cracker | **Intención de dañar** (NO en hacker, SÍ en cracker) |
| Virus | Gusano | **Propagación automática** (NO en virus, SÍ en gusano) |
| Pharming | Spoofing | Pharming modifica el sistema DNS; Spoofing suplanta identidad emitiendo paquetes falsos |
| XSS Reflejado | XSS Almacenado | El almacenado es **persistente** (se guarda en el servidor); el reflejado no |
| CVE | CVSS | CVE es un **identificador**; CVSS es una **puntuación numérica** |

### Nemotécnicos para el examen

| Sigla | Significado |
|-------|-------------|
| **CIA** (trinomio) | Confidencialidad, Integridad, Disponibilidad |
| **M.I.C.E.** | Money, Ideology, Compromise, Ego |
| **CVE-CVSS-NVD** | CVE: identifica (MITRE), CVSS: puntúa (0-10), NVD: base de datos (NIST) |
| **APT** | Amenaza Avanzada y Persistente (estados-nación, ciberespionaje prolongado) |

### Ejemplos reales que citar

| Amenaza | Ejemplo | Año |
|---------|---------|-----|
| Gusano | **Stuxnet** (sabotaje nuclear iraní) | 2010 |
| Ransomware | **WannaCry** (NHS, 200.000 equipos en 150 países) | 2017 |
| APT | **SONY Pictures** (Corea del Norte, 100TB robados) | 2014 |
| DDoS + Botnet IoT | **Mirai** (tumbó Dyn DNS, afectó a Twitter, Netflix) | 2016 |
| Ingeniería social | **Twitter Bitcoin Scam** (cuentas verificadas secuestradas) | 2020 |
| Día cero | **Log4Shell** (CVSS 10.0, RCE en Log4j) | 2021 |
| Día cero | **EternalBlue** (NSA, filtrado, usado por WannaCry) | 2017 |
| Deepfake + IA | **Fraude de $25M** con videollamada deepfake del CFO | 2024 |
| Rootkit | **Sony BMG Rootkit** en CDs de música | 2005 |
| Privacidad RRSS | **Cambridge Analytica** (87M de perfiles de Facebook) | 2018 |

---

*Documento de referencia para UA 3 — Amenazas a los Sistemas de Información*
