# UA 4: Mecanismos de Defensa

> **Navegación:**
> - [← README](../README.md)
> - [← Tema 3](03-amenazas-sistemas.md)
> - [GLOSARIO](../GLOSARIO.md)
> - [Chuleta numérica](08-cheat-sheet-numeros.md)
> - [Tema 5 →](05-gestion-seguridad.md)

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
| **Desactivar el servidor DHCP** | Usar asignación de **IP estática** en los equipos de la red local. Evita que dispositivos no autorizados obtengan dirección IP automáticamente al conectarse |
| **Usar 802.1X / RADIUS** | Autenticación de dispositivos antes de permitir el acceso a la red. Proporciona control centralizado de credenciales y evita conexiones no autorizadas |

#### MALAS prácticas (NO hacer)

| Mala práctica | Riesgo |
|---|---|
| **Permitir acceso remoto a la configuración del router** | Cualquiera desde Internet puede intentar acceder al panel de administración |
| **Desactivar el cifrado WiFi** | Red abierta: cualquiera puede conectarse y capturar tráfico |
| **Entregar conexiones a DMZ / Default Workstation** | Exponer un equipo directamente a Internet sin protección del firewall del router |

> **PREGUNTA TIPO EXAMEN:** "¿Cuál de estas es una buena práctica en la configuración de un router ADSL doméstico?" — Si las opciones son las 3 malas prácticas anteriores más "Ninguna de las anteriores", la respuesta correcta es **"Ninguna de las anteriores es buena práctica"**.

> **IMPORTANTE - Segunda opinión:** Es **IMPRESCINDIBLE** instalar una buena suite de seguridad y realizar **escaneos periódicos remotos con OTRA suite** diferente (segunda opinión) para detectar posibles infecciones que la primera suite haya pasado por alto. Ningún antimalware es infalible; una segunda herramienta reduce el riesgo de falsos negativos.

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

### 2.1 Recepción de correo

| Práctica | Descripción |
|---|---|
| **No abrir correos sospechosos** | Remitente desconocido, asuntos alarmantes, archivos adjuntos no solicitados |
| **Jamás responder SPAM** | Responder confirma al remitente que la dirección está activa, lo que genera más spam |
| **No hacer click en enlaces de credenciales** | Los servicios legítimos NUNCA piden contraseñas por email. Verificar escribiendo la URL directamente en el navegador |
| **Escanear adjuntos** | Pasar por antivirus o VirusTotal antes de abrir cualquier archivo adjunto |
| **Desconfiar del remitente** | Verificar la dirección real del remitente (cabeceras del correo), no solo el nombre mostrado. Comprobar que el dominio es legítimo |

### 2.2 Envío de correo

| Práctica | Descripción |
|---|---|
| **Usar Asunto descriptivo** | Facilitar que el destinatario identifique el correo como legítimo y evitar que sea marcado como spam |
| **No proporcionar información personal/financiera** | Evitar enviar DNI, datos bancarios, contraseñas o cualquier dato sensible por email |
| **No participar en cadenas de correo** | Las cadenas son fuente de propagación de malware, bulos y recopilación de direcciones de correo |
| **Usar CCO (Bcc - Blind Carbon Copy)** | Proteger la privacidad de los destinatarios, no exponer direcciones de terceros |
| **No responder SPAM (salvo Lista Robinson)** | La única respuesta admisible a un correo no deseado es darse de baja mediante el servicio **Lista Robinson** (listas de exclusión publicitaria oficiales) |

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
- **Cuidado con Google (Black Hat SEO)**: las técnicas de Black Hat SEO pueden posicionar sitios tóxicos y fraudulentos en los primeros resultados de búsqueda, llevándonos a páginas maliciosas sin que el usuario sea consciente del riesgo
- **Evitación de Código Tóxico y control de pestañas**: no mantener abiertas simultáneamente en el mismo navegador sesiones de redes sociales y banca online. Un código malicioso ejecutándose en una pestaña podría acceder a los datos de sesión de otra
- **"Googlear" toda URL sospechosa antes de acceder**: antes de hacer click en un enlace sospechoso, buscar la URL o el nombre del sitio en un buscador para verificar si existen reportes de fraude, malware o phishing asociados

### Privacidad en Redes Sociales (RRSS)

> En navegación en RRSS aplica **todo lo indicado anteriormente** (HTTPS, 2FA, contraseñas, no recordar claves en navegador, control de cookies, etc.) más las siguientes medidas específicas:

| Acción | Recomendación |
|---|---|
| **Política de uso y privacidad** | Leer y entender la política de privacidad y condiciones de cada red social antes de crear un perfil |
| **Nivel de privacidad** | Configurar el perfil como privado, limitar la visibilidad a contactos de confianza |
| **Evitar acceso a "amigos de amigos"** | Esta opción amplía enormemente la exposición; desactivarla siempre |
| **Información personal** | No publicar dirección, teléfono, ubicación en tiempo real, planes de vacaciones |
| **Información de terceros** | No publicar fotos, vídeos o datos personales de terceros sin su consentimiento explícito. Respeta la privacidad ajena tanto como la propia |

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

#### Tipos de análisis (caja blanca, negra, gris)

| Tipo | Descripción |
|---|---|
| **Caja negra (Black Box)** | El pentester no dispone de información previa del sistema. Simula un ataque externo real sin conocimiento interno de la infraestructura |
| **Caja blanca (White Box)** | El pentester tiene acceso completo a la información del sistema: código fuente, diagramas de red, credenciales, documentación. Es el análisis más exhaustivo |
| **Caja gris (Grey Box)** | El pentester dispone de información parcial (ej. credenciales de usuario estándar). Simula un ataque desde dentro con privilegios limitados |

#### OSINT (Open Source Intelligence)

Empleo de herramientas **OSINT** (Open Source Intelligence) para la recopilación de información pública sobre el objetivo: dominios, direcciones IP, correos electrónicos, perfiles en redes sociales, repositorios de código, metadatos de documentos, etc. Herramientas comunes: **Maltego**, **theHarvester**, **Shodan**, **Recon-ng**. Es una fase fundamental en la etapa de reconocimiento del pentesting.

### 4.7 Análisis forense

Disciplina que investiga incidentes de seguridad mediante la recolección, preservación, análisis y presentación de evidencias digitales. Debe mantener la **cadena de custodia** para que las evidencias sean admisibles en procesos judiciales.

**Fases:** Identificación → Adquisición → Preservación → Análisis → Documentación → Presentación.

#### Tipos de análisis forense

| Tipo | Descripción |
|---|---|
| **Análisis Forense (equipos activos)** | Se realiza sobre sistemas en funcionamiento. Permite capturar información volátil: procesos en memoria, conexiones de red activas, usuarios logueados, claves de cifrado en RAM. Requiere actuación inmediata porque esta información se pierde al apagar el equipo |
| **Análisis Post-mortem (equipos no activos)** | Se realiza sobre sistemas apagados o discos duros extraídos. Se analizan medios de almacenamiento no volátiles (HDD, SSD, USB). Es el más común en investigaciones judiciales y permite trabajar con imágenes forenses sin prisas |

---

## 5. Seguridad en servidores Web

### 5.1 OWASP (Open Worldwide Application Security Project)

> **Anteriormente:** Open Web Application Security Project

Fundación sin ánimo de lucro que desarrolla y mantiene recursos gratuitos para mejorar la seguridad del software.

| Recurso | Descripción |
|---|---|
| **OWASP Top 10** | Lista de los 10 riesgos de seguridad más críticos en aplicaciones web. Se actualiza **cada 4 años**. Edición actual (2021): Inyección, Fallos de Autenticación, Exposición de Datos Sensibles, XXE, Control de Acceso Roto, Configuraciones Incorrectas, XSS, Deserialización Insegura, Componentes Vulnerables, Monitoreo Insuficiente |
| **ASVS** (Application Security Verification Standard) | Estándar de verificación de seguridad para aplicaciones. **Versión 5.0.0 (2025)**, estructurada en **17 apartados** que cubren arquitectura, autenticación, control de acceso, validación de entradas, criptografía, gestión de errores, etc. |
| **WSTG** (Web Security Testing Guide) | Guía completa de pruebas de seguridad en aplicaciones web. **Versión 5.0.0 (2025)**. Disponible para descarga desde el repositorio oficial de **GitHub** de OWASP |
| **API Security Top 10** | Lista específica de riesgos de seguridad en APIs. **Versión 2023**. Cubre riesgos como Broken Object Level Authorization, Broken Authentication, Excessive Data Exposure, Lack of Resources & Rate Limiting, etc. |

### 5.2 WAF (Web Application Firewall)

| Característica | Descripción |
|---|---|
| **Capa OSI** | Opera en **capa 7** (Aplicación) |
| **Funcionamiento** | Analiza el contenido de las peticiones HTTP/HTTPS buscando ataques como SQLi, XSS, CSRF, inclusión de archivos, etc. |
| **Listas negras** | Bloquea patrones de ataque conocidos (signatures) |
| **Listas blancas** | Solo permite tráfico que cumple reglas definidas como válidas |
| **Modo detección** | Monitoriza y registra, pero no bloquea (útil en fase de tuning) |
| **Modo prevención** | Bloquea activamente el tráfico malicioso |

#### Modos de despliegue

| Modo | Descripción |
|---|---|
| **Proxy inverso** | El WAF se sitúa delante del servidor web como proxy inverso, filtrando antes de que el tráfico llegue a la aplicación. Es la configuración más común. El tráfico pasa físicamente a través del WAF |
| **Modo inline (transparente)** | El WAF se sitúa en línea con el tráfico de red, actuando como un puente transparente a nivel 2. No modifica las direcciones IP de origen/destino. Puede bloquear tráfico malicioso |
| **Port mirroring (SPAN)** | El tráfico se copia a un puerto de monitorización donde el WAF analiza de forma pasiva. No puede bloquear tráfico, solo detectar y alertar. Útil para análisis sin impacto en producción |

#### Servidor único vs Cluster

| Configuración | Descripción |
|---|---|
| **Servidor único** | Un solo nodo WAF. Sencillo de desplegar pero introduce un punto único de fallo (SPOF - Single Point of Failure) |
| **Cluster** | Varios nodos WAF trabajando en conjunto. Proporciona: **balanceo de carga** (distribución del tráfico entre nodos), **redundancia** (alta disponibilidad: si un nodo falla, los demás asumen el tráfico) y **sincronización de reglas** (todas las políticas de seguridad se replican automáticamente entre los nodos del cluster) |

#### Cloud WAF

- Servicio **SaaS** (Software as a Service) gestionado íntegramente por el proveedor (Cloudflare WAF, AWS WAF, Azure WAF, Imperva Cloud WAF)
- **Ventajas**: despliegue sencillo (cambio de DNS), no requiere mantenimiento de infraestructura, actualizaciones automáticas de reglas, escalabilidad gestionada
- **Desventaja crítica**: se **cede el tráfico a un tercero**, lo que implica consideraciones de confidencialidad, soberanía del dato y cumplimiento normativo (RGPD)

#### Problema crítico: descifrado TLS

- Para analizar el tráfico HTTPS, el WAF necesita **descifrar el contenido** de las peticiones
- El WAF actúa como un **"man-in-the-middle" legal**: descifra el tráfico del cliente con su propio certificado, analiza la petición, y la vuelve a cifrar hacia el servidor de origen
- Para ello, el WAF debe tener un **certificado propio** de confianza instalado y aceptado por la infraestructura
- **Introduce latencia** adicional en cada petición debido al proceso de descifrado/análisis/cifrado

### 5.3 ModSecurity

> **Referencia de WAF open source.** Desarrollado originalmente por **Trustwave**, desde **2024** es un proyecto bajo el paraguas de la **OWASP Foundation**.

- Motor de detección de intrusiones para aplicaciones web (también llamado "IDS/IPS para HTTP")
- Funciona como módulo de Apache, Nginx o IIS
- Usa su propio lenguaje de reglas: **SecLang** (ModSecurity Rule Language)
- Utiliza el **OWASP Core Rule Set (CRS)** como conjunto de reglas base

#### Proyectos bajo OWASP Foundation

OWASP gestiona tres proyectos complementarios relacionados con WAF:

| Proyecto | Descripción |
|---|---|
| **ModSecurity** | WAF original escrito en C/C++. Maduro, ampliamente probado en producción, pero con limitaciones de rendimiento en entornos de alto tráfico |
| **Coraza** | WAF alternativo escrito en **Go** (Golang). Mayor rendimiento y menor consumo de recursos, diseñado para entornos cloud, contenedores y Kubernetes |
| **OWASP Core Rule Set (CRS)** | Conjunto de reglas genéricas que cubren el **OWASP Top 10**: protección contra SQLi, XSS, inyección de código, RFI/LFI, etc. Es independiente del motor WAF utilizado |

#### Retos operativos

| Reto | Descripción |
|---|---|
| **Falsos positivos** | El CRS genérico puede bloquear tráfico legítimo. Requiere una fase de **tuning** (ajuste de reglas) para cada aplicación, desactivando o modificando reglas que generen falsos positivos en el contexto específico |
| **Descifrado TLS** | Mismo problema que cualquier WAF: necesidad de descifrar el tráfico HTTPS para analizarlo, actuando como man-in-the-middle con certificado propio |
| **Mantenimiento del CRS** | Las reglas deben actualizarse periódicamente para cubrir nuevas amenazas, vectores de ataque y vulnerabilidades. Un CRS desactualizado deja puntos ciegos |
| **Rendimiento** | El análisis de cada petición HTTP consume CPU y añade latencia. **Coraza** (Go) mejora el rendimiento respecto a ModSecurity (C) en entornos de alto tráfico |

> **CONCEPTO CLAVE:** "Un WAF **no sustituye al desarrollo seguro** ni al parcheo de vulnerabilidades. Es una capa de protección adicional (**parche virtual**) que reduce la **ventana de exposición** mientras se desarrolla y despliega el parche definitivo en el código."

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

### 6.4 Mando Conjunto de Ciberdefensa

Creado en **2014**, dependiente del **JEMAD** (Jefe del Estado Mayor de la Defensa). Responsable de la **planificación y ejecución** de las operaciones de ciberdefensa militar en las Fuerzas Armadas españolas. Actúa como mando operativo de las capacidades de ciberdefensa del Ministerio de Defensa.

### 6.5 SOCs (Security Operation Center)

Centros de operaciones de seguridad que **monitorizan 24x7x365** las redes y sistemas en busca de amenazas e incidentes de ciberseguridad.

| SOC | Ámbito |
|---|---|
| **SOC AGE** (Administración General del Estado) | Gestionado por el **CCN**. Monitoriza los sistemas y redes de la Administración General del Estado, proporcionando vigilancia continua y respuesta temprana ante ciberamenazas |
| **SOCs privados** | Empresas de ciberseguridad que ofrecen servicios de monitorización gestionada (MSSP - Managed Security Service Provider) a organizaciones que no disponen de SOC propio |

### 6.6 CERTs autonómicos y privados

Los **CERTs autonómicos** y **CERTs privados** actúan como **primer escalón** en la respuesta a incidentes de ciberseguridad. Gestionan incidentes de su ámbito competencial y derivan los casos más graves o que exceden sus capacidades a los CERTs nacionales de referencia (CCN-CERT, INCIBE-CERT).

### 6.7 CNPIC — Detalle adicional

Creado en **2007**, el **Centro Nacional de Protección de Infraestructuras Críticas** (CNPIC) es el responsable de impulsar, coordinar y supervisar la protección de las infraestructuras críticas en España.

**Objetivos clave:**
- Proteger **12 sectores** estratégicos: energía, agua, transporte, telecomunicaciones/TIC, sistema financiero, salud, alimentación, espacio, industria nuclear, industria química, administración, instalaciones de investigación
- Mantener el **Catálogo Nacional de Infraestructuras Críticas**, que inventaría y cataloga los activos esenciales del país cuya perturbación o destrucción tendría un grave impacto en los servicios esenciales

### 6.8 AEPD — Detalle adicional

La **Agencia Española de Protección de Datos** (AEPD) opera a nivel nacional como autoridad de control independiente en materia de protección de datos.

Existen **agencias autonómicas** de protección de datos en:
- **Madrid** (Agencia de Protección de Datos de la Comunidad de Madrid)
- **Cataluña** (Autoritat Catalana de Protecció de Dades - APDCAT)
- **País Vasco** (Euskal Autonomia Erkidegoko Datuen Babeserako Agentzia - AVPD)

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
