# UA 4: Mecanismos de Defensa

> Guía completa de referencia — Seguridad de la Información

---

## Índice

1. [Defensa desde perspectiva doméstica](#1-defensa-desde-perspectiva-doméstica)
2. [Correo electrónico seguro](#2-correo-electrónico-seguro)
3. [Navegación segura](#3-navegación-segura)
4. [Defensa perimetral organizacional](#4-defensa-perimetral-organizacional)
5. [Seguridad en servidores Web](#5-seguridad-en-servidores-web)
6. [Defensa gubernamental en España](#6-defensa-gubernamental-en-españa)
7. [Direcciones IP](#7-direcciones-ip)
8. [SQL Injection — Prevención](#8-sql-injection--prevención)
9. [Resumen para el examen](#resumen-para-el-examen)

---

## 1. Defensa desde perspectiva doméstica

### 1.1 Recomendaciones básicas

#### Cuentas de usuario vs Administrador

| Práctica | Descripción |
|---|---|
| **Usar cuenta estándar** | Para el día a día, NUNCA navegar o trabajar con cuenta de Administrador |
| **Administrador solo para tareas puntuales** | Instalar software, cambiar configuración del sistema. Usar UAC (User Account Control) |
| **Separación de privilegios** | Si un malware infecta una cuenta estándar, su capacidad de daño es limitada |

**Ejemplo real:** En entornos Windows corporativos, los empleados trabajan con cuentas de dominio sin privilegios locales. Si un ransomware como WannaCry infecta esa sesión, no puede cifrar archivos del sistema porque carece de permisos de escritura en `C:\Windows\System32`.

#### Política de contraseñas

| Elemento | Recomendación |
|---|---|
| **Longitud mínima** | 12-14 caracteres |
| **Complejidad** | Mayúsculas, minúsculas, números, caracteres especiales |
| **No reutilizar** | Contraseña diferente para cada servicio |
| **Gestor de contraseñas** | Bitwarden, KeepassXC, 1Password |
| **Rotación** | Cambiar ante sospecha de compromiso, no forzar cambios arbitrarios (NIST SP 800-63B ya no recomienda caducidad periódica) |

**Ejemplo real:** El ataque de *Credential Stuffing* explota la reutilización de contraseñas. Si tu contraseña de LinkedIn se filtró en 2012, y la reutilizas en Gmail, un atacante puede acceder a ambos.

#### Actualizaciones automáticas

- Activar **Windows Update / Actualizaciones automáticas** en todos los sistemas operativos
- Mantener actualizado el firmware del router, navegadores, plugins y aplicaciones
- Las vulnerabilidades *zero-day* se parchean constantemente; un sistema desactualizado es un blanco fácil

**Ejemplo real:** El ataque de ransomware **WannaCry (mayo 2017)** explotó la vulnerabilidad EternalBlue (MS17-010), parcheada por Microsoft en marzo de 2017. Las máquinas que NO habían aplicado la actualización fueron infectadas masivamente (Telefónica, NHS británico, etc.).

#### Política de copias de seguridad

| Regla | Descripción |
|---|---|
| **Estrategia 3-2-1** | 3 copias, 2 soportes distintos, 1 copia externa (offline/offsite) |
| **Periodicidad** | Diaria para datos críticos, semanal para el resto |
| **Verificación** | Probar periódicamente la restauración (una copia que no se restaura NO es una copia) |
| **Aisladas** | Copias offline o inmutables para protegerse del ransomware |

**Ejemplo real:** La Universidad de Maastricht (2019) pagó 30 BTC de rescate por ransomware. Si hubieran tenido backups offline funcionales, no habrían necesitado pagar.

#### Suites de seguridad (antivirus/antimalware) — **IMPRESCINDIBLE**

| Componente | Función |
|---|---|
| **Antivirus** | Detección basada en firmas de malware conocido |
| **Firewall personal** | Filtrado de tráfico entrante/saliente |
| **Antispyware** | Detección de software espía y adware |
| **Protección web** | Bloqueo de URLs maliciosas y phishing |
| **Anti-ransomware** | Módulo específico contra cifrado no autorizado |

**Ejemplos reales de suites:**
- **Windows Defender** (integrado en Windows 10/11, gratuito, eficaz)
- **Kaspersky Internet Security**
- **Bitdefender Total Security**
- **ESET Smart Security Premium**

---

### 1.2 Router ADSL doméstico

**ADSL = Asymmetric Digital Subscriber Line** — la "A" es de **Asíncrona** (velocidad de bajada > velocidad de subida).

#### Buenas prácticas

| Práctica | Por qué |
|---|---|
| **Cambiar la contraseña de acceso al router** | La contraseña por defecto (admin/admin, 1234) es pública y conocida |
| **Evitar el acceso a la configuración desde Internet** | Desactivar administración remota vía WAN |
| **Modo firewall activo** | El firewall integrado del router (SPI/NAT) debe estar siempre habilitado |

#### MALAS prácticas (NO hacer)

| Mala práctica | Riesgo |
|---|---|
| **Permitir acceso remoto a la configuración del router** | Cualquiera desde Internet puede intentar acceder al panel de administración |
| **Desactivar el cifrado WiFi** | Red abierta: cualquiera puede conectarse y capturar tráfico |
| **Entregar conexiones a DMZ / Default Workstation** | Exponer un equipo directamente a Internet sin protección del firewall del router |

> **PREGUNTA TIPO EXAMEN:** "¿Cuál de estas es una buena práctica en la configuración de un router ADSL doméstico?" — Si las opciones son las 3 malas prácticas anteriores más "Ninguna de las anteriores", la respuesta correcta es **"Ninguna de las anteriores es buena práctica"**.

---

### 1.3 Seguridad WiFi

#### Protocolos de cifrado

| Protocolo | Año | Cifrado | Estado |
|---|---|---|---|
| **WEP** | 1999 | RC4 (64/128 bits) | **Roto y obsoleto** — se crackea en minutos |
| **WPA** | 2003 | TKIP + RC4 | Obsoleto, vulnerable |
| **WPA2** | 2004 | AES + CCMP | **Seguro** (aunque KRACK afecta, requiere parche) |
| **WPA3** | 2018 | AES + GCMP-256 / SAE | **Más seguro** — protección contra diccionario offline |

**IMPORTANTE:** WEP **NO es seguro**. Es INCORRECTO usar WEP como medida de protección WiFi. Cualquier pregunta de examen que sugiera WEP como medida válida debe marcarse como FALSA.

**WPA** se usa para **cifrar las comunicaciones WiFi**.

#### Medidas básicas de seguridad WiFi

| Medida | Descripción |
|---|---|
| **Desactivar WPS** | Wi-Fi Protected Setup es peligrosísimo: el PIN de 8 dígitos se puede forzar por fuerza bruta en horas. **SIEMPRE desactivarlo** |
| **Ocultar SSID** | No difundir el nombre de la red (medida de oscuridad, no impide un ataque pero reduce exposición básica) |
| **ACL por MAC** | Filtrado de direcciones MAC: solo equipos autorizados se conectan. Medida complementaria (la MAC se puede suplantar) |
| **Usar WPA2 o WPA3** | Estándar mínimo exigible para la encriptación del tráfico |

> **PREGUNTA TIPO EXAMEN:** "¿Qué protocolo es seguro para proteger una red WiFi?" → **WPA2** (dentro de las opciones típicas de examen). WPA3 es superior pero en muchos temarios aún no aparece como opción principal.

---

### 1.4 Dispositivos móviles

| Ámbito | Medidas |
|---|---|
| **Cifrado de información** | Cifrado del almacenamiento interno (en reposo) y de las comunicaciones (en tránsito: TLS/HTTPS) |
| **WiFi segura** | Evitar redes WiFi públicas abiertas; si se usan, emplear siempre VPN |
| **Bluetooth** | Mantenerlo desactivado si no se usa. Modo "no visible". Peligroso por ataques como BlueBorne, Bluejacking, Bluesnarfing |
| **Suite de seguridad** | Instalar antimalware específico para móviles (Bitdefender Mobile Security, Kaspersky, etc.) |
| **Control de permisos de apps** | Revisar qué permisos solicita cada app (cámara, micrófono, contactos, ubicación). Principio de mínimo privilegio |

**Ejemplo real:** En 2021, se descubrieron apps en Google Play con el malware **Joker** que se suscribían a servicios premium sin consentimiento del usuario, abusando de permisos de SMS.

---

## 2. Correo electrónico seguro

### Buenas prácticas

| Práctica | Descripción |
|---|---|
| **Varias cuentas** | Separar cuenta personal, profesional y de registro en servicios dudosos |
| **Consultar periódicamente** | Revisar todas las cuentas; una cuenta abandonada comprometida puede usarse para suplantación de identidad |
| **No abrir correos sospechosos** | Remitente desconocido, asuntos alarmantes ("Tu cuenta ha sido bloqueada"), archivos adjuntos no solicitados |
| **No responder SPAM** | Responder confirma al remitente que la dirección está activa → más spam |
| **No hacer click en enlaces de credenciales** | Los bancos y servicios legítimos NUNCA piden contraseñas por email. Verificar escribiendo la URL directamente en el navegador |
| **Escanear adjuntos** | Antes de abrir cualquier archivo adjunto, pasarlo por el antivirus o usar VirusTotal |
| **Usar CCO (Copia de Carbón Oculta)** | Al enviar a múltiples destinatarios, usar CCO para no exponer direcciones de terceros |

### Integridad vs Confidencialidad del correo

| Propiedad | Cómo se garantiza |
|---|---|
| **Integridad** (el mensaje no ha sido alterado) | **Firmando digitalmente** el correo |
| **Confidencialidad** (solo el destinatario puede leerlo) | **Cifrando** el contenido del correo |

> **CLAVE DE EXAMEN:** Cifrar un correo proporciona **confidencialidad**, NO integridad. La integridad se garantiza con **firma digital**. Son conceptos distintos que NO deben confundirse.

### Protocolos de correo seguro

| Estándar | Descripción |
|---|---|
| **S/MIME** (Secure/Multipurpose Internet Mail Extensions) | Usa certificados X.509. Integrado en clientes de correo como Outlook, Thunderbird |
| **PGP** (Pretty Good Privacy) / **OpenPGP** (GPG) | Usa clave pública/privada. No depende de una PKI centralizada, modelo de "red de confianza" (Web of Trust) |

**Ejemplo real:** Un periodista que necesita recibir filtraciones de un denunciante puede publicar su clave pública PGP. El denunciante cifra el correo con esa clave pública y solo el periodista (con su clave privada) puede descifrarlo.

---

## 3. Navegación segura

### HTTPS

- Verificar siempre que la URL comienza por `https://` y que el certificado es **válido** (candado verde/cerrado)
- Un certificado caducado, autofirmado o emitido para otro dominio debe generar alarma
- HTTPS proporciona: confidencialidad, integridad y autenticación del servidor

### Autenticación de dos factores (2FA / MFA)

| Tipo | Ejemplo |
|---|---|
| **Algo que sabes** | Contraseña |
| **Algo que tienes** | Móvil (código SMS, app autenticadora como Google Authenticator), token físico (YubiKey) |
| **Algo que eres** | Huella dactilar, reconocimiento facial |

**Activar 2FA en todos los servicios que lo permitan** (banca online, correo, redes sociales).

### Otras medidas

- **No recordar contraseñas en el navegador** (especialmente en equipos compartidos). Usar gestor de contraseñas externo
- **Control de cookies**: eliminar periódicamente cookies de terceros, usar modo incógnito cuando proceda
- **Evitar URLs sospechosas**: dominios mal escritos (faceboook.com, g00gle.com), acortadores (bit.ly) sin contexto
- **Black Hat SEO**: técnicas de posicionamiento malicioso para que sitios fraudulentos aparezcan en los primeros resultados de búsqueda. Desconfiar de resultados patrocinados no verificados

### Privacidad en Redes Sociales (RRSS)

| Acción | Recomendación |
|---|---|
| **Política de uso** | Leer y entender la política de privacidad y condiciones de cada red social |
| **Nivel de privacidad** | Configurar el perfil como privado, limitar la visibilidad a contactos de confianza |
| **No compartir con "amigos de amigos"** | Esta opción amplía enormemente la exposición; desactivarla |
| **Datos personales** | No publicar dirección, teléfono, ubicación en tiempo real, planes de vacaciones |

**Ejemplo real:** El caso de **Cambridge Analytica (2018)** explotó los permisos de Facebook que permitían a una app recopilar datos no solo del usuario que la instalaba, sino también de **todos sus amigos**, afectando a ~87 millones de perfiles.

---

## 4. Defensa perimetral organizacional

### 4.1 Firewalls

| Nivel OSI | Capa | Qué filtra | Ejemplo |
|---|---|---|---|
| **Nivel 3 — Red** | IP | Direcciones IP origen/destino | Listas de control de acceso (ACL) en routers Cisco |
| **Nivel 4 — Transporte** | TCP/UDP | Puertos origen/destino, estado de conexión (stateful) | iptables, pfSense |
| **Nivel 7 — Aplicación** | HTTP/DNS/etc. | Contenido del tráfico, URLs, payloads, SQLi, XSS | WAF, proxy de aplicación |

### 4.2 DMZ (Zona Desmilitarizada)

> **DEFINICIÓN DE EXAMEN:** La DMZ es una subred dentro de la red interna de la organización donde se ubican los servidores que ofrecen servicios al **exterior** (Internet). Contiene los **bastiones** (servidores públicos).

**Lo que la DMZ SÍ es:**
- Parte de la red interna (separada de la intranet corporativa)
- Zona donde se alojan servidores públicos: Web, DNS, SMTP, FTP corporativo
- Contiene equipos **bastión** (endurecidos y preparados para resistir ataques)

**Lo que la DMZ NO es:**
- ❌ La intranet corporativa
- ❌ Donde se conectan los PCs de los usuarios/empleados
- ❌ Parte de Internet (está entre Internet y la red interna, pero pertenece a la organización)

```
[Internet] <--> [Firewall externo] <--> [DMZ (servidores públicos)] <--> [Firewall interno] <--> [Intranet corporativa]
```

### 4.3 Intranet corporativa

Zona segura interior de la organización. Contiene los equipos de los empleados, servidores internos (Directorio Activo, ficheros, BBDD internas), impresoras, etc. Protegida tras el firewall interno.

### 4.4 VPN (Red Privada Virtual)

> **DEFINICIÓN DE EXAMEN:** Sistema de interconexión o acceso a redes privadas a través de redes públicas (Internet). Crea un "túnel" cifrado extremo a extremo.

**Lo que la VPN SÍ es:**
- Túnel cifrado sobre red pública
- Permite acceso remoto seguro a la red corporativa
- Interconexión segura entre sedes (VPN site-to-site)

**Lo que la VPN NO es:**
- ❌ Virtualización de redes (eso es SDN — Software Defined Networking)
- ❌ Un anonimizador (aunque algunos proveedores la comercialicen así)

**Protocolos VPN comunes:** IPsec, OpenVPN, WireGuard, L2TP/IPsec.

### 4.5 IDS / IPS

| Sistema | Siglas | Qué hace |
|---|---|---|
| **IDS** (Intrusion Detection System) | Sistema de Detección de Intrusiones | Monitoriza y alerta, pero no bloquea |
| **IPS** (Intrusion Prevention System) | Sistema de Prevención de Intrusiones | Monitoriza, alerta y bloquea en tiempo real |

### 4.6 Hacking ético y Pentesting

| Concepto | Definición |
|---|---|
| **Hacking ético** | Uso de técnicas de hacking con autorización del propietario del sistema para identificar vulnerabilidades. El objetivo es **mejorar la seguridad**, no explotar debilidades |
| **Pentesting** (Test de Penetración) | Simulación controlada de un ataque real a un sistema, red o aplicación para evaluar su seguridad. Se entrega un informe con hallazgos y recomendaciones |

**Metodologías:** OSSTMM, OWASP Testing Guide, PTES, ISSAF.

### 4.7 Análisis forense

Disciplina que investiga incidentes de seguridad mediante la recolección, preservación, análisis y presentación de evidencias digitales. Debe mantener la **cadena de custodia** para que las evidencias sean admisibles en procesos judiciales.

**Fases:** Identificación → Adquisición → Preservación → Análisis → Documentación → Presentación.

---

## 5. Seguridad en servidores Web

### 5.1 OWASP (Open Worldwide Application Security Project)

> **Anteriormente:** Open Web Application Security Project

Fundación sin ánimo de lucro que desarrolla y mantiene recursos gratuitos para mejorar la seguridad del software.

| Recurso | Descripción |
|---|---|
| **OWASP Top 10** | Lista de los 10 riesgos de seguridad más críticos en aplicaciones web. Edición actual (2021): Inyección, Fallos de Autenticación, Exposición de Datos Sensibles, XXE, Control de Acceso Roto, Configuraciones Incorrectas, XSS, Deserialización Insegura, Componentes Vulnerables, Monitoreo Insuficiente |
| **ASVS** (Application Security Verification Standard) | Estándar de verificación de seguridad para aplicaciones |
| **WSTG** (Web Security Testing Guide) | Guía completa de pruebas de seguridad en aplicaciones web |
| **API Security Top 10** | Lista específica de riesgos de seguridad en APIs |

### 5.2 WAF (Web Application Firewall)

| Característica | Descripción |
|---|---|
| **Capa OSI** | Opera en **capa 7** (Aplicación) |
| **Funcionamiento** | Analiza el contenido de las peticiones HTTP/HTTPS buscando ataques como SQLi, XSS, CSRF, inclusión de archivos, etc. |
| **Listas negras** | Bloquea patrones de ataque conocidos (signatures) |
| **Listas blancas** | Solo permite tráfico que cumple reglas definidas como válidas |
| **Modo detección** | Monitoriza y registra, pero no bloquea (útil en fase de tuning) |
| **Modo prevención** | Bloquea activamente el tráfico malicioso |
| **Proxy inverso** | El WAF se sitúa delante del servidor web como proxy inverso, filtrando antes de que el tráfico llegue a la aplicación |

### 5.3 ModSecurity

> **Referencia de WAF open source.** Originalmente desarrollado por Trustwave, ahora es un proyecto bajo el paraguas de **OWASP**.

- Motor de detección de intrusiones para aplicaciones web (también llamado "IDS/IPS para HTTP")
- Funciona como módulo de Apache, Nginx o IIS
- Usa el lenguaje de reglas **ModSecurity Rule Language** y el **OWASP Core Rule Set (CRS)**
- Permite crear reglas personalizadas y es altamente configurable

### 5.4 Inyección SQL — Prevención

> **La inyección SQL se evita en el CÓDIGO de la aplicación web**, filtrando todo el tráfico de entrada. **NO se evita en el firewall** (aunque un WAF ayuda como defensa en profundidad, la solución real es en el código).

**Técnicas correctas de prevención:**

| Técnica | Descripción |
|---|---|
| **Consultas parametrizadas (Prepared Statements)** | Separar la estructura SQL de los datos del usuario. El motor SABE qué es código y qué es dato |
| **Procedimientos almacenados** | Lógica SQL encapsulada en el SGBD con parámetros tipados |
| **Validación de entrada (whitelist)** | Aceptar solo caracteres/formato esperado (ej. un DNI: 8 dígitos + letra) |
| **Escapado de caracteres** | Neutralizar caracteres especiales (`'`, `"`, `--`, `;`) |
| **Principio de mínimo privilegio** | La cuenta de BBDD que usa la aplicación NO debe ser administradora |
| **ORM** (Object-Relational Mapping) | Frameworks como Hibernate, Entity Framework que abstraen las consultas y usan parámetros por defecto |

---

## 6. Defensa gubernamental en España

### 6.1 CERT / CSIRT

> **CERT** = Computer Emergency Response Team
> **CSIRT** = Computer Security Incident Response Team

Son **Centros de Respuesta ante Incidentes** de seguridad informática. Ofrecen servicios de coordinación, alerta temprana, gestión de incidentes y análisis de vulnerabilidades.

**Lo que NO son:**
- ❌ CAU (Centro de Atención al Usuario)
- ❌ CRU (Centro de Respuesta Unificada)
- ❌ CAS (Centro de Atención a Servicios)

Son exclusivamente centros de respuesta a **incidentes de seguridad informática**.

### 6.2 CERTs/CSIRTs en España

| Organismo | Ámbito | Dependencia |
|---|---|---|
| **CCN-CERT** | Administración pública y sistemas clasificados (secretos oficiales) | CCN (Centro Criptológico Nacional), adscrito al **CNI** |
| **INCIBE-CERT** | Empresas, ciudadanos y red académica (RedIRIS) | INCIBE — Instituto Nacional de Ciberseguridad |
| **ESP DEF CERT** | Ministerio de Defensa y Fuerzas Armadas | EMAD (Estado Mayor de la Defensa) |
| **IRIS-CERT** | Red académica y científica española (RedIRIS) | Asignado por **Real Decreto-Ley 12/2018** |

### 6.3 Otros organismos

| Organismo | Siglas | Función |
|---|---|---|
| **ENISA** | European Union Agency for Network and Information Security (ahora EU Agency for Cybersecurity) | Agencia europea de ciberseguridad. Coordina, asesora y emite recomendaciones a nivel europeo |
| **CNPIC** | Centro Nacional de Protección de Infraestructuras Críticas | Protege infraestructuras esenciales (energía, agua, transporte, telecomunicaciones, etc.) |
| **CCN** | Centro Criptológico Nacional | Organismo adscrito al **CNI** encargado de la seguridad de las TIC en el sector público y sistemas clasificados |
| **INCIBE** | Instituto Nacional de Ciberseguridad (antes **INTECO**) | Investigación, formación, concienciación y respuesta a incidentes para empresas y ciudadanos. Con sede en León |
| **AEPD** | Agencia Española de Protección de Datos | Autoridad de control independiente que vela por el cumplimiento de la normativa de protección de datos (RGPD, LOPDGDD) |

---

## 7. Direcciones IP

### Rangos privados (RFC 1918)

| Clase | Rango CIDR | Rango de IPs | Ejemplos |
|---|---|---|---|
| **Clase A** | `10.0.0.0/8` | 10.0.0.0 – 10.255.255.255 | 10.1.1.1, 10.200.50.3 |
| **Clase B** | `172.16.0.0/12` | 172.16.0.0 – 172.31.255.255 | 172.26.0.1, 172.30.100.5 |
| **Clase C** | `192.168.0.0/16` | 192.168.0.0 – 192.168.255.255 | 192.168.1.1, 192.168.0.100 |

> **PREGUNTA TIPO EXAMEN:** "¿Cuál de estas direcciones es pública?"

| Dirección | ¿Privada o Pública? | Por qué |
|---|---|---|
| 10.1.1.1 | **Privada** | Está en 10.0.0.0/8 |
| 172.26.0.1 | **Privada** | Está en 172.16.0.0/12 |
| 192.168.1.1 | **Privada** | Está en 192.168.0.0/16 |
| **11.1.1.1** | **Pública** | No pertenece a ningún rango privado RFC 1918 |

> **ATENCIÓN:** 11.1.1.1 es una IP **pública**. No está comprendida en los rangos 10.x.x.x, 172.16-31.x.x ni 192.168.x.x. Cualquier IP fuera de esos tres rangos (y no siendo loopback 127.x.x.x ni APIPA 169.254.x.x) es pública.

---

## 8. SQL Injection — Prevención

### Principio fundamental

> La inyección SQL **se previene en el código de la aplicación web**, filtrando y validando todo el tráfico de entrada. **NO se previene configurando un firewall** (aunque un WAF añade una capa adicional de defensa, la solución real está en el código).

### Cómo se produce la inyección SQL

Un atacante inyecta comandos SQL maliciosos en campos de entrada (formularios, parámetros URL, cookies) cuando la aplicación **concatena directamente** la entrada del usuario en las consultas SQL sin validarla ni parametrizarla.

**Ejemplo VULNERABLE (NO hacer):**

```python
# ❌ CÓDIGO VULNERABLE
usuario = request.GET['usuario']
consulta = "SELECT * FROM usuarios WHERE nombre = '" + usuario + "'"
cursor.execute(consulta)
```

Si el atacante introduce: `' OR '1'='1' --` la consulta se convierte en:
```sql
SELECT * FROM usuarios WHERE nombre = '' OR '1'='1' --'
```

**Ejemplo CORREGIDO (consultas parametrizadas):**

```python
# ✅ CÓDIGO SEGURO
usuario = request.GET['usuario']
consulta = "SELECT * FROM usuarios WHERE nombre = %s"
cursor.execute(consulta, [usuario])
```

### Resumen de defensas

| Método | ¿Dónde se aplica? | Eficacia |
|---|---|---|
| **Consultas parametrizadas / Prepared Statements** | **Código** | ✅ Definitiva |
| **Validación de entrada (whitelist)** | **Código** | ✅ Alta |
| **Procedimientos almacenados** | **Código / BBDD** | ✅ Alta |
| **ORM con parámetros** | **Código** | ✅ Alta |
| **Escapado de caracteres** | **Código** | ⚠️ Parcial (frágil) |
| **WAF** | Perimetral | ⚠️ Capa adicional, NO solución |
| **Firewall de red** | Perimetral | ❌ No previene SQLi |

---

## Resumen para el examen

### Claves absolutas (preguntas trampa frecuentes)

| Situación | Respuesta correcta |
|---|---|
| Buenas prácticas router ADSL: permitir acceso remoto, desactivar cifrado, entregar conexiones a DMZ | **Ninguna** es buena práctica |
| ¿Qué mide la A de ADSL? | **Asíncrona** (Asymmetric) |
| ¿Qué protocolo WiFi es seguro? | **WPA2** (WPA3 es mejor, pero en examen clásico la respuesta es WPA2) |
| ¿Es WEP seguro? | **NO**. Es INCORRECTO usarlo como medida de protección |
| ¿Hay que activar o desactivar WPS? | **Desactivar** siempre (es peligrosísimo) |
| Cifrar el correo garantiza... | **Confidencialidad** (no integridad) |
| La integridad del correo se garantiza... | **Firmando** digitalmente |
| ¿Qué es la DMZ? | Subred donde se colocan servidores que ofrecen servicios al **exterior** |
| La DMZ, ¿es la intranet? | **NO** |
| ¿Qué es una VPN? | Sistema de interconexión/acceso a redes privadas sobre redes públicas |
| VPN, ¿es virtualización de redes? | **NO** (eso es SDN) |
| ¿En qué capa OSI trabaja un WAF? | **Capa 7** (Aplicación) |
| ¿Cómo se evita la inyección SQL? | En el **CÓDIGO** de la aplicación web, filtrando el tráfico de entrada |
| ¿Se evita SQLi en el firewall? | **NO** (se evita en el código) |
| 11.1.1.1 ¿es pública o privada? | **Pública** (fuera de los rangos 10/8, 172.16/12, 192.168/16) |
| 10.1.1.1, 172.26.0.1, 192.168.1.1 | Las tres son **privadas** |

### Siglas y organismos

| Siglas | Significado |
|---|---|
| CERT | Computer Emergency Response Team |
| CSIRT | Computer Security Incident Response Team |
| CCN-CERT | Administración pública y sistemas clasificados |
| INCIBE-CERT | Empresas, ciudadanos, red académica |
| ESP DEF CERT | Ministerio de Defensa |
| IRIS-CERT | Red académica RedIRIS (RD-Ley 12/2018) |
| ENISA | Agencia europea de ciberseguridad |
| CNPIC | Protección infraestructuras críticas |
| CCN | Centro Criptológico Nacional (adscrito al CNI) |
| INCIBE | Instituto Nacional de Ciberseguridad (antes INTECO) |
| AEPD | Agencia Española de Protección de Datos |
| OWASP | Open Worldwide Application Security Project |
| WAF | Web Application Firewall |

### Rangos privados IP

```
10.0.0.0/8       →  10.x.x.x
172.16.0.0/12    →  172.16.x.x - 172.31.x.x
192.168.0.0/16   →  192.168.x.x
```

---

> **"En un examen, la diferencia entre aprobar y suspender está en no confundir confidencialidad con integridad, código con firewall, y DMZ con intranet."**
