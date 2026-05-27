# Examen 02: Casos Prácticos

> 📚 [← README](../README.md) | [← Simulacro 01](01-teoria-general.md) | [Simulacro 03 →](03-nivel-experto.md)

**20 preguntas tipo test de casos prácticos: Nivel MEDIO**
*Cada pregunta plantea un escenario realista de aplicación de conceptos de Seguridad de la Información.*

---

## UA1: Conceptos Fundamentales (2 preguntas)

### 1. Trabajas en la startup "PayFlow". Un viernes por la tarde, un desarrollador despliega una actualización en producción que borra accidentalmente la tabla de transacciones. El CTO te dice: "tranquilo, tenemos backup de ayer a las 3 a.m." Sin embargo, la restauración tarda 6 horas, durante las cuales ningún cliente puede operar. El CEO está furioso. ¿Qué dimensión de la seguridad ha fallado principalmente y qué medida debería haberse previsto?

- A) Falló la Confidencialidad; deberían haber cifrado la tabla de transacciones para evitar accesos indebidos.
- B) Falló la Disponibilidad; el error humano causó una interrupción prolongada y la restauración del backup no fue lo bastante ágil para garantizar la continuidad del negocio.
- C) Falló la Integridad; el borrado accidental alteró datos sin autorización.
- D) Falló la Autenticación; el desarrollador no debería haber tenido acceso a producción con ese privilegio.

> **Respuesta: B**
>
> **Justificación (breve):** Aunque el borrado accidental afecta a la integridad (C), el problema principal para el negocio fue la indisponibilidad del servicio durante 6 horas. La Disponibilidad garantiza que la información esté accesible cuando se necesita, y una ventana de restauración de 6 horas evidencia falta de planificación de continuidad (RTO inadecuado). La opción A confunde confidencialidad con disponibilidad. La D apunta a un fallo de control de acceso, que contribuye pero no es la dimensión que el CEO sufre directamente.

---

### 2. Eres administrador de sistemas en "BureauConsulting". Una auditora externa te pregunta cómo verificas que los candidatos a un puesto con acceso a datos financieros no tengan antecedentes penales por delitos económicos. Le respondes que "RRHH les pide el CV y ya está". La auditora anota una no conformidad grave. ¿Qué medida fundamental con el personal está omitiendo vuestra organización?

- A) Formación: los empleados no han recibido capacitación en protección de datos financieros.
- B) Seguimiento: no se monitoriza la actividad de los empleados con acceso a datos críticos.
- C) Fiabilidad: no se verifica la confianza y antecedentes del personal que manejará información sensible.
- D) Concienciación: no se realizan campañas de phishing simulado para medir el riesgo humano.

> **Respuesta: C**
>
> **Justificación (breve):** Las tres medidas con el personal son Formación, Fiabilidad y Seguimiento. La Fiabilidad implica verificar la confianza del personal antes de otorgar acceso a información sensible (verificación de antecedentes, referencias, etc.). Pedir solo el CV sin contrastarlo es una omisión grave de esta medida. La opción A es otra medida necesaria pero no la que describe el escenario. B y D son relevantes pero posteriores a la contratación.

---

## UA2: Criptografía (5 preguntas)

### 3. En "CloudNova", un desarrollador backend cifra los backups nocturnos de la base de datos (50 GB) usando AES-256 en modo ECB. Al revisar visualmente el fichero cifrado con un visor hexadecimal, el CISO detecta patrones repetitivos cada 16 bytes durante largos tramos. ¿Cuál es la causa raíz del problema?

- A) AES-256 es demasiado débil para archivos de 50 GB; deberían haber usado AES-512.
- B) El modo ECB no oculta patrones: bloques de texto claro idénticos producen bloques de texto cifrado idénticos.
- C) El visor hexadecimal está malinterpretando los datos; ECB es perfectamente seguro para backups.
- D) La clave de 256 bits se truncó a 128 bits porque ECB solo soporta claves de ese tamaño.

> **Respuesta: B**
>
> **Justificación (breve):** ECB (Electronic Codebook) cifra cada bloque de forma independiente con la misma clave. Si dos bloques del texto claro son idénticos, producirán bloques de texto cifrado idénticos, revelando patrones del original. Para backups, deben usarse modos como CBC o GCM con un IV aleatorio. La opción A es falsa (AES-256 es robusto; el problema es el modo). C es peligrosamente incorrecta. D es técnicamente falsa (el tamaño de bloque de AES es siempre 128 bits, independientemente del tamaño de clave).

---

### 4. En "MediTech Solutions", el equipo de desarrollo almacena contraseñas de usuarios aplicando SHA-256 con una sal global (la misma cadena fija para todos los usuarios, hardcodeada en la aplicación). Una auditoría de seguridad detecta que dos usuarios tienen el mismo hash almacenado. ¿Qué vector de ataque concreto sigue siendo viable que una sal por usuario habría neutralizado?

- A) Ataque de fuerza bruta contra el algoritmo SHA-256.
- B) Ataque de denegación de servicio contra la tabla de usuarios.
- C) Identificación de usuarios que comparten la misma contraseña, lo que permite priorizar el ataque de diccionario contra esas cuentas.
- D) Inyección SQL que extrae los hashes directamente del servidor.

> **Respuesta: C**
>
> **Justificación (breve):** Con una sal global, dos usuarios con la misma contraseña producen el mismo hash. Un atacante que obtenga la base de datos puede identificar instantáneamente qué usuarios comparten contraseña y centrar el ataque de diccionario/fuerza bruta en ellos. Una sal única por usuario garantiza que incluso contraseñas idénticas generen hashes completamente distintos. Además, las rainbow tables precalculadas para esa sal global también serían efectivas contra todos los usuarios simultáneamente. La opción A describe un ataque genérico no específico al fallo de diseño. B y D son ataques no relacionados.

---

### 5. El portal de reservas de "TravelCorp" funciona con HTTPS, pero un investigador de seguridad descubre que el servidor solo admite TLS 1.0 con el cipher suite TLS_RSA_WITH_RC4_128_MD5. El CTO responde: "está cifrado, no veo el problema". ¿Qué riesgo específico y concreto están ignorando?

- A) Ninguno; mientras use HTTPS, la comunicación es segura independientemente de la versión de TLS.
- B) TLS 1.0 y RC4 están obsoletos y son vulnerables: RC4 tiene sesgos estadísticos que permiten recuperar texto claro, y TLS 1.0 es vulnerable a BEAST y carece de forward secrecy.
- C) El problema es solo que MD5 está roto para integridad, pero RC4 sigue siendo seguro.
- D) El riesgo es que el certificado caduque antes de tiempo si usa TLS 1.0.

> **Respuesta: B**
>
> **Justificación (breve):** TLS 1.0 (1999) está deprecado por el PCI DSS desde 2018 y por los principales navegadores. RC4 tiene sesgos en su keystream que permiten recuperar partes del texto claro tras analizar millones de sesiones. La combinación con RSA sin forward secrecy (usando la clave privada del servidor para el intercambio) significa que si la clave privada se compromete en el futuro, todas las sesiones pasadas capturadas pueden descifrarse. La opción A es falsa y peligrosa. C minimiza el riesgo real de RC4. D es una invención.

---

### 6. En "BlockStorage Inc.", un desarrollador genera claves AES "aleatorias" calculando `SHA-256(fecha_hora_actual)` y truncando a 128 bits. Un pentester externo rompe una de estas claves en 4 horas con un portátil. ¿Cuál es el error criptográfico fundamental?

- A) AES no soporta claves de 128 bits; el mínimo son 256 bits.
- B) SHA-256 no es adecuado para generar material de clave porque es un algoritmo de resumen, no de cifrado.
- C) La clave no se generó con un generador criptográficamente seguro (CSPRNG): al usar una marca temporal como única fuente de entropía, el espacio de claves efectivo es minúsculo y predecible.
- D) El truncamiento de 256 a 128 bits invalida la seguridad del algoritmo AES.

> **Respuesta: C**
>
> **Justificación (breve):** El error es usar una fuente predecible (timestamp) en lugar de un CSPRNG como `/dev/urandom` o `SecureRandom` de Java. Si el atacante conoce el día en que se generó la clave, el espacio de búsqueda se reduce a 86.400 segundos/día × precisión de milisegundos (~2^26 combinaciones), trivial para fuerza bruta. La opción A es falsa (AES-128 es perfectamente válido). B es incorrecta: SHA-256 sí puede usarse en una KDF como HKDF, pero no como sustituto directo de un CSPRNG. D es falsa.

---

### 7. En "AcmeCorp", dos departamentos necesitan intercambiar informes confidenciales. Alicia, del Dpto. Financiero, quiere enviar el informe trimestral a Benito de Auditoría de forma que solo Benito pueda leerlo. Alicia ejecuta: `openssl rsautl -encrypt -inkey alicia_privada.pem -in informe.pdf -out informe.cifrado`. Cuando Benito intenta descifrarlo con la clave pública de Alicia, lo consigue, pero exclama: "¡esto no puede ser, cualquiera con tu clave pública puede leerlo!" ¿Qué operación criptográfica realizó Alicia realmente?

- A) Cifró correctamente el archivo; el problema es que Benito usó mal OpenSSL.
- B) Aplicó una firma digital: cifrar con la clave privada produce una firma que cualquiera puede verificar con la clave pública. Para garantizar confidencialidad, debería haber cifrado con la clave pública de Benito.
- C) Realizó un HMAC del archivo, no un cifrado.
- D) Usó el algoritmo equivocado: `rsautl` no cifra archivos, solo genera resúmenes.

> **Respuesta: B**
>
> **Justificación (breve):** En RSA, cifrar con la clave privada equivale a FIRMAR (cualquiera con la clave pública puede "descifrar" = verificar). Para CONFIDENCIALIDAD (solo Benito lee), Alicia debe cifrar con la clave pública de Benito, y solo él, con su clave privada, podrá descifrarlo. Es un error conceptual clásico. La opción A es incorrecta porque la operación aplicada proporciona autenticación/no repudio, no confidencialidad. C y D son técnicamente incorrectas.

---

## UA3: Amenazas (3 preguntas)

### 8. La empresa de energía renovable "GreenVolt" detecta tráfico anómalo saliente desde su servidor de monitorización SCADA: conexiones a IPs en el extranjero a altas horas de la madrugada. La investigación forense revela que el vector de entrada fue una actualización de firmware del fabricante de los controladores PLC, descargada desde el portal oficial del proveedor, que contenía una puerta trasera insertada por un atacante que comprometió los sistemas del fabricante. ¿Qué tipo de ataque describe este escenario?

- A) Un ataque de phishing dirigido (spear-phishing) contra los ingenieros de la planta.
- B) Un ataque de denegación de servicio distribuido (DDoS) contra la infraestructura SCADA.
- C) Un ataque a la cadena de suministro (supply chain attack): el atacante comprometió a un proveedor de confianza para distribuir malware a sus clientes.
- D) Un ataque de fuerza bruta contra las contraseñas de los controladores PLC.

> **Respuesta: C**
>
> **Justificación (breve):** El escenario describe un ataque a la cadena de suministro: el atacante no ataca directamente a GreenVolt, sino que compromete al fabricante de los PLC y utiliza su canal de distribución de software legítimo como vector para infectar a los clientes. Es el mismo patrón que el ataque de SolarWinds (2020). La opción A es incorrecta porque el vector no fue un correo electrónico. B describe un efecto (tráfico anómalo) pero no el tipo de ataque. D no encaja con la evidencia.

---

### 9. El CEO de "RetailMax" recibe un mensaje de WhatsApp de la CFO (con su foto de perfil y tono habitual): "Estoy en una reunión, necesito que transfieras 50.000 € urgentemente a esta cuenta para cerrar un contrato antes de las 12. Luego te paso la factura." El CEO realiza la transferencia. Horas después, la CFO real llama preguntando por qué se ha vaciado la cuenta de imprevistos. ¿Qué variante de ataque de ingeniería social se ha producido?

- A) Phishing masivo: se envió el mismo mensaje a todos los empleados de la empresa.
- B) Vishing: el atacante llamó por teléfono haciéndose pasar por la CFO.
- C) Whaling combinado con suplantación de identidad (spoofing): un ataque de ingeniería social altamente dirigido contra un alto directivo (CEO), usando información contextual para hacerse pasar por otro directivo (CFO) a través de un canal de mensajería.
- D) Smishing: el atacante envió un SMS con un enlace malicioso a un formulario falso.

> **Respuesta: C**
>
> **Justificación (breve):** Whaling es una forma de spear-phishing dirigida específicamente a altos directivos (las "ballenas" de la organización). El atacante investigó previamente quiénes son CEO y CFO, probablemente obtuvo la foto de perfil de LinkedIn, y usó ingeniería social contextual (urgencia, autoridad). La opción A es incorrecta (no fue masivo, fue dirigido). B implicaría una llamada telefónica. D es un ataque por SMS genérico.

---

### 10. Un desarrollador junior de "DataVault Analytics" está trabajando desde casa en hora punta. Para compartir un volcado de la base de datos de clientes con un compañero, lo sube a un repositorio público de GitHub "solo un par de horas". Antes de que pueda borrarlo, los crawlers de búsqueda indexan el archivo y un investigador externo lo encuentra y lo notifica. ¿Cómo se clasifica principalmente este incidente?

- A) Ataque externo malicioso: un cracker accedió al repositorio y robó los datos.
- B) Amenaza interna no intencionada (insider threat accidental): un empleado legítimo, sin intención maliciosa, expuso información confidencial por negligencia o desconocimiento del procedimiento.
- C) Inyección de código: el desarrollador insertó accidentalmente datos sensibles en el commit.
- D) Ataque de intermediario (MitM): los datos fueron interceptados durante la subida a GitHub.

> **Respuesta: B**
>
> **Justificación (breve):** El incidente es una amenaza interna de tipo no intencionado: el empleado tenía acceso legítimo y no buscaba causar daño, pero su acción negligente (subir datos sensibles a un repositorio público) provocó una brecha de confidencialidad. No hubo ataque externo (A), ni inyección (C), ni interceptación (D). La causa raíz es la falta de controles DLP y de formación en seguridad para desarrolladores.

---

## UA4: Defensa (4 preguntas)

### 11. El hospital "MedNet" ha implantado dispositivos IoT médicos (bombas de infusión, monitores de glucosa) que se comunican con el sistema de historia clínica electrónica. El CISO detecta que todos los dispositivos :médicos, ordenadores de administración, impresoras y el WiFi de visitantes: comparten la misma VLAN y subnet. ¿Qué medida de arquitectura de red debe implantar con urgencia?

- A) Instalar un antivirus corporativo en cada dispositivo IoT médico.
- B) Segmentar la red creando VLANs separadas: una para dispositivos médicos, otra para la red administrativa, otra para visitantes, con reglas de firewall entre ellas que limiten las comunicaciones estrictamente necesarias.
- C) Cambiar el direccionamiento IP de clase C a clase A para tener más capacidad.
- D) Sustituir todos los switches por hubs para simplificar la topología.

> **Respuesta: B**
>
> **Justificación (breve):** La segmentación de red con VLANs + ACLs/firewall es una defensa fundamental. Los dispositivos IoT médicos suelen tener sistemas operativos limitados que no pueden recibir antivirus (A). Deben aislarse en una VLAN propia, con reglas que solo permitan la comunicación necesaria con el HIS (Hospital Information System), bloqueando el acceso a Internet y a otras redes internas. La opción C es irrelevante. D es contraproducente (los hubs no segmentan).

---

### 12. "CloudHost Ltd." sufre una intrusión. El atacante explotó una vulnerabilidad en Apache Struts de su aplicación web pública. La vulnerabilidad tenía un CVE asignado, un parche oficial disponible desde hacía 8 meses, y un exploit público circulando desde hacía 5 meses. El servidor estaba en una DMZ con firewall, antivirus actualizado y contraseñas robustas. ¿Qué capa de defensa falló estructuralmente?

- A) Falló el firewall perimetral, que debería haber bloqueado el exploit a nivel de paquete.
- B) Falló la gestión de parches (patch management): ninguna medida de seguridad compensa la falta de aplicación oportuna de actualizaciones de software.
- C) Falló la autenticación multifactor del servidor web.
- D) Falló el cifrado de los datos en reposo.

> **Respuesta: B**
>
> **Justificación (breve):** El firewall no puede inspeccionar tráfico HTTP a nivel de aplicación para detectar exploits de Struts a menos que sea un WAF específicamente configurado. El antivirus no protege contra exploits de aplicaciones web. La DMZ contiene el movimiento lateral pero no impide la explotación inicial. La gestión de parches es una capa de defensa insustituible: una vulnerabilidad con parche disponible durante 8 meses y exploit público es un fallo de proceso, no de tecnología. La opción A es incorrecta porque los firewalls tradicionales operan a nivel de red/transporte. C y D son irrelevantes para este vector.

---

### 13. Un empleado de "LegalCorp" encuentra una memoria USB en el parking de la oficina. Por curiosidad, la conecta a su estación de trabajo corporativa para ver su contenido. La memoria contiene un documento PDF falso que, al abrirse, ejecuta un exploit de día cero y compromete el equipo. La empresa tenía antivirus actualizado y firewall perimetral. ¿Qué combinación de controles falló?

- A) Falló exclusivamente el antivirus, que debería haber detectado el exploit.
- B) Falló la concienciación del empleado (no conectar dispositivos desconocidos) y la configuración técnica del endpoint (no estar deshabilitada la ejecución automática/autorun USB vía GPO).
- C) Falló el firewall perimetral, que debería haber bloqueado el exploit cuando el USB se conectó.
- D) No falló nada; un ataque de día cero es imposible de prevenir.

> **Respuesta: B**
>
> **Justificación (breve):** El escenario evidencia dos fallos combinados: (1) factor humano: el empleado carece de concienciación sobre el riesgo de conectar dispositivos USB desconocidos (vector clásico de ingeniería social física, como el experimento de los USBs en aparcamientos); (2) control técnico ausente: deshabilitar la ejecución automática de USBs vía GPO es una medida básica de hardening que habría mitigado el ataque incluso con el error humano. La opción A ignora que un día cero, por definición, no tiene firma en el antivirus. C es absurda (el firewall no interviene en USB). D es derrotista y falsa: la defensa en profundidad sí mitiga días cero con controles complementarios.

---

### 14. La universidad "EduNet" observa en sus logs más de 80.000 intentos de inicio de sesión fallidos en su portal del alumnado en una sola noche, procedentes de más de 3.000 direcciones IP distintas distribuidas en 40 países. Usan combinaciones de usuario/contraseña probablemente filtradas de otras brechas. El portal usa autenticación simple usuario+contraseña. ¿Qué mecanismo de defensa específico aborda MÁS directamente este tipo de ataque?

- A) Cifrar la base de datos de contraseñas con AES-256.
- B) Implementar limitación de tasa (rate limiting) por IP y por cuenta, combinada con CAPTCHA progresivo tras N intentos fallidos y bloqueo temporal de cuenta.
- C) Migrar el portal a un proveedor de hosting con más ancho de banda.
- D) Sustituir las contraseñas por autenticación biométrica de huella dactilar.

> **Respuesta: B**
>
> **Justificación (breve):** El ataque descrito es de tipo credential stuffing: el atacante prueba pares usuario/contraseña obtenidos de otras brechas, explotando la reutilización de contraseñas. La defensa primaria es rate limiting + account lockout + CAPTCHA para ralentizar la automatización. La opción A protege los datos en reposo pero no evita el ataque en curso. C no mitiga el ataque (más ancho de banda no bloquea intentos maliciosos). D no es viable para 30.000 alumnos y no es la defensa más directa contra credential stuffing.

---

## UA5: Gestión de la Seguridad (4 preguntas)

### 15. "InsureTech Seguros" está implantando un SGSI según ISO 27001. En el análisis de impacto sobre el negocio (BIA) determinan que su aplicación core de gestión de pólizas tiene un RTO (Recovery Time Objective) de 4 horas y un RPO (Recovery Point Objective) de 15 minutos. Sin embargo, la infraestructura actual de backup solo puede restaurar datos con un RPO de 24 horas (backup diario nocturno). ¿Cómo debe gestionarse esta situación desde la perspectiva del análisis de riesgos?

- A) Aceptar el RPO de 24 horas porque el backup diario es suficiente para cualquier empresa.
- B) Identificar la brecha como un riesgo, evaluar su impacto potencial y proponer medidas de tratamiento como implantar replicación síncrona o backups incrementales cada 15 minutos para reducir el RPO real al nivel requerido.
- C) Modificar el RPO requerido a 24 horas en la documentación del BIA para que coincida con la realidad técnica.
- D) Transferir el riesgo a la aseguradora sin modificar la infraestructura de backup.

> **Respuesta: B**
>
> **Justificación (breve):** La brecha entre el RPO requerido (15 min) y el RPO real (24 h) constituye un riesgo que debe ser identificado, evaluado y tratado. La opción correcta es mitigarlo: implantar tecnología que reduzca el RPO (replicación continua, snapshots frecuentes). La opción A es negligente porque ignora un requisito de negocio. C es un fraude documental (falsear el BIA). D es válida como estrategia complementaria pero no sustituye la mitigación técnica cuando la brecha es tan grande.

---

### 16. El ayuntamiento "MuniCorp" realiza su primera auditoría de seguridad y el informe final arroja 73 hallazgos entre no conformidades mayores, menores y observaciones. El concejal de nuevas tecnologías, abrumado, ordena: "contratad a una consultora y resolvedlo todo en un mes". Como responsable de seguridad, ¿qué enfoque metodológico debes proponer basándote en las buenas prácticas de gestión?

- A) Ejecutar un proyecto de 30 días contratando consultores externos para cerrar todos los hallazgos simultáneamente.
- B) Priorizar los hallazgos por nivel de riesgo (impacto × probabilidad), elaborar un plan de tratamiento con plazos realistas para los críticos/altos, y abordar el resto de forma progresiva en ciclos sucesivos siguiendo el modelo de mejora continua (PDCA).
- C) Apelar el informe de auditoría alegando que 73 hallazgos es una cifra inasumible.
- D) Implementar únicamente las medidas técnicas, ignorando las organizativas porque "no son tangibles".

> **Respuesta: B**
>
> **Justificación (breve):** La gestión de seguridad efectiva se basa en la priorización por riesgo y en la mejora continua (PDCA). Intentar resolver todo simultáneamente (A) es inviable y probablemente introducirá nuevos problemas. La opción C es una huida hacia adelante. La D ignora que las medidas organizativas son tan importantes como las técnicas (ej: políticas, procedimientos, formación). La respuesta correcta aplica dos principios clave: priorización basada en riesgos y mejora iterativa.

---

### 17. En "FinServe Bank", una auditoría revela que el mismo empleado que aprueba órdenes de compra de material informático es también quien concilia las cuentas bancarias y quien realiza el inventario físico del almacén. Adicionalmente, el administrador que despliega reglas de firewall es la misma persona encargada de revisar trimestralmente los logs del firewall. ¿Qué principio fundamental de control interno se está vulnerando?

- A) Principio de defensa en profundidad: no hay suficientes capas de seguridad entre el empleado y los activos.
- B) Principio de mínimo privilegio: el empleado tiene más permisos de los estrictamente necesarios.
- C) Principio de segregación de funciones (separation of duties): las tareas de ejecución y control deben recaer en personas distintas para evitar conflictos de intereses y prevenir el fraude.
- D) Principio de seguridad por oscuridad: los empleados no deben conocer los procesos internos.

> **Respuesta: C**
>
> **Justificación (breve):** La segregación de funciones (SoD) es un control organizativo clave: quien ejecuta una acción no debe ser quien la revisa o audita. Si la misma persona compra, concilia y hace inventario, puede cometer fraude sin detección. Si quien configura el firewall revisa sus propios logs, puede ocultar configuraciones maliciosas o errores. La opción A es un concepto de arquitectura de seguridad, no de control interno. B es relevante pero no captura el problema central del conflicto de funciones. D no es un principio de seguridad válido.

---

### 18. La empresa "NovaPay" obtuvo la certificación ISO 27001 hace 3 años, pero desde entonces no ha vuelto a realizar una auditoría interna completa ni ha actualizado su declaración de aplicabilidad. Solo renuevan el certificado anualmente con el auditor externo haciendo una revisión mínima. El CISO alerta al CEO: "estamos en riesgo de perder la certificación". ¿Qué requisito fundamental de la ISO 27001 están incumpliendo?

- A) No están aplicando cifrado a los datos en tránsito.
- B) No están manteniendo el ciclo de mejora continua (PDCA): la ISO 27001 exige auditorías internas periódicas, revisión del SGSI por la dirección, y actualización continua del sistema, no solo una revisión externa anual.
- C) No están utilizando la versión más reciente de la norma ISO 27001:2022.
- D) No han contratado un CISO a tiempo completo.

> **Respuesta: B**
>
> **Justificación (breve):** La ISO 27001 exige la operación continua del SGSI, incluyendo auditorías internas a intervalos planificados (cláusula 9.2), revisión por la dirección (9.3) y mejora continua (cláusula 10). La certificación no se "mantiene" simplemente pasando una auditoría externa anual mínima; el SGSI debe estar vivo. La opción A puede ser cierta pero no es el motivo de pérdida de la certificación. C es incorrecta (las transiciones de versión tienen períodos de gracia). D no es un requisito explícito de la norma.

---

## UA6: Legislación (2 preguntas)

### 19. La empresa española "AdTarget SL" utiliza un CRM alojado en servidores de un proveedor cloud estadounidense. Almacenan nombres, correos electrónicos, direcciones IP y preferencias de compra de 500.000 ciudadanos europeos. El proveedor estadounidense NO está acogido al Data Privacy Framework (DPF) UE-EE.UU. y el contrato no incluye cláusulas contractuales tipo (SCC). El asesor legal externo dice: "los datos están en Estados Unidos, así que la normativa española no aplica." ¿Cuál es la situación legal real?

- A) El asesor tiene razón: los datos en servidores de EE.UU. se rigen exclusivamente por la legislación estadounidense.
- B) Se está vulnerando el RGPD: el Capítulo V exige que las transferencias internacionales de datos solo se realicen a países con nivel adecuado de protección o con garantías como SCC. Al no cumplirse ninguna, la transferencia es ilícita.
- C) Solo se necesita el consentimiento de los usuarios para transferir los datos, sin necesidad de otras garantías.
- D) La LOPD de 1999 sigue siendo la norma aplicable porque el contrato con el proveedor cloud es anterior al RGPD.

> **Respuesta: B**
>
> **Justificación (breve):** El RGPD (art. 44-49) regula estrictamente las transferencias internacionales. EE.UU. no tiene una decisión de adecuación general de la Comisión Europea; el DPF sustituyó al invalidado Privacy Shield, pero el proveedor no está acogido. Las SCC son el mecanismo estándar para legitimar la transferencia. Sin DPF ni SCC, la transferencia es ilegal, independientemente de dónde estén físicamente los servidores (el RGPD aplica porque los datos son de ciudadanos de la UE tratados por una empresa establecida en la UE). La opción A es falsa (extraterritorialidad del RGPD, art. 3). C es insuficiente: el consentimiento es una excepción limitada y no válida para transferencias masivas y sistemáticas. D es falsa: la LOPD 1999 está derogada.

---

### 20. La cadena de clínicas privadas "SaludPlus" sufre un ataque de ransomware que cifra las bases de datos con historiales médicos de 50.000 pacientes. El director de TI ordena pagar el rescate en Bitcoin y no informar a nadie "para no alarmar y evitar sanciones". Como asesor de protección de datos, le recuerdas sus obligaciones legales bajo el RGPD. ¿Qué debe hacer SaludPlus respecto a la comunicación de esta brecha?

- A) Nada: al ser un ataque externo, la responsabilidad recae en el atacante, no en la clínica.
- B) Notificar la brecha a la AEPD (Agencia Española de Protección de Datos) en un plazo máximo de 72 horas desde que tuvieron constancia, y comunicarlo a los pacientes afectados sin dilación indebida si existe un alto riesgo para sus derechos y libertades, dado que afecta a categorías especiales de datos (salud).
- C) Solo notificar a los pacientes cuyo historial médico contenga datos especialmente sensibles, ignorando al resto.
- D) Publicar una nota de prensa genérica sin dar detalles y esperar a que la AEPD investigue por su cuenta.

> **Respuesta: B**
>
> **Justificación (breve):** El RGPD (art. 33 y 34) obliga a notificar cualquier brecha de datos personales a la autoridad de control competente (AEPD) en un plazo máximo de 72 horas. Si la brecha implica un alto riesgo para los derechos y libertades de los afectados :como ocurre con datos de salud, que son categorías especiales (art. 9): debe comunicarse también a los interesados sin dilación indebida. Pagar el rescate no exime de estas obligaciones. La opción A es falsa (el responsable del tratamiento responde aunque el ataque sea externo). C ignora que todos los datos de salud son categorías especiales. D incumple los requisitos de notitud del RGPD.

---

## 📋 Soluciones

| # | UA | Respuesta | Explicación breve |
|---|-----|-----------|------------------|
| 1 | UA1 | **B** | Falló la Disponibilidad: el servicio estuvo 6 horas inaccesible por un error humano y la restauración lenta. La integridad también se vio afectada, pero la dimensión principal que impactó al negocio fue la falta de disponibilidad. |
| 2 | UA1 | **C** | Fiabilidad: de las tres medidas con el personal (Formación, Fiabilidad y Seguimiento), falta verificar la confianza/antecedentes del personal antes de otorgar acceso a información sensible. |
| 3 | UA2 | **B** | ECB cifra bloques idénticos de forma idéntica, revelando patrones. Para backups de 50 GB debe usarse un modo con IV (CBC, GCM). El tamaño de bloque de AES es siempre 128 bits, independientemente de la clave. |
| 4 | UA2 | **C** | Con sal global, usuarios con misma contraseña producen mismo hash → el atacante identifica duplicados y prioriza esas cuentas. Una sal única por usuario elimina este vector y fuerza rainbow tables individuales. |
| 5 | UA2 | **B** | TLS 1.0 + RC4-MD5 es una combinación obsoleta y vulnerable. RC4 tiene sesgos estadísticos explotables; TLS 1.0 carece de forward secrecy y es vulnerable a BEAST. HTTPS no garantiza seguridad si la configuración subyacente es débil. |
| 6 | UA2 | **C** | La clave se generó a partir de un timestamp (entropía predecible) en lugar de un CSPRNG. El espacio de búsqueda efectivo es minúsculo (~2^26 para un día con precisión de ms). SHA-256 puede usarse en KDF pero no sustituye a un CSPRNG. |
| 7 | UA2 | **B** | Cifrar con clave privada RSA = firma digital (cualquiera con la pública verifica). Para confidencialidad (solo Benito lee), Alicia debió cifrar con la clave pública de Benito. Es un error conceptual frecuente. |
| 8 | UA3 | **C** | Ataque a la cadena de suministro (supply chain): el atacante compromete al fabricante de PLC e infecta a sus clientes a través del canal de actualización legítimo. Mismo patrón que SolarWinds (2020). |
| 9 | UA3 | **C** | Whaling + suplantación de identidad: ataque dirigido a un alto directivo haciéndose pasar por otro directivo usando WhatsApp. Combina investigación previa (foto de perfil, contexto) con ingeniería social de urgencia y autoridad. |
| 10 | UA3 | **B** | Amenaza interna no intencionada (insider threat accidental): empleado legítimo expone datos por negligencia, sin intención maliciosa. La causa raíz es la falta de controles DLP y formación. |
| 11 | UA4 | **B** | Segmentación de red con VLANs + firewall entre ellas: separar dispositivos médicos, red administrativa y WiFi de visitantes. Los dispositivos IoT médicos no pueden ejecutar antivirus (A); un hub(D) empeoraría la seguridad. |
| 12 | UA4 | **B** | Falló la gestión de parches: vulnerabilidad con CVE, parche disponible 8 meses y exploit público. Ni DMZ, ni antivirus, ni contraseñas compensan la falta de aplicación oportuna de actualizaciones. |
| 13 | UA4 | **B** | Fallo combinado: concienciación del empleado (no conectar USBs desconocidos) + hardening técnico ausente (GPO para deshabilitar autorun). La defensa en profundidad mitiga incluso ataques de día cero con controles complementarios. |
| 14 | UA4 | **B** | Rate limiting + CAPTCHA + bloqueo temporal de cuenta es la defensa directa contra credential stuffing (80K intentos desde 3K IPs con credenciales filtradas). Cifrar la BD (A) no detiene el ataque en curso. |
| 15 | UA5 | **B** | La brecha entre RPO requerido (15 min) y RPO real (24 h) es un riesgo que debe mitigarse implantando replicación continua o backups incrementales frecuentes. Falsear el BIA (C) es fraude documental. |
| 16 | UA5 | **B** | Priorización por riesgo (impacto × probabilidad) y mejora continua (PDCA): abordar críticos primero con plazos realistas, el resto en ciclos sucesivos. Intentar todo a la vez (A) es inviable y contraproducente. |
| 17 | UA5 | **C** | Segregación de funciones (SoD): quien ejecuta no debe controlar/auditar. Compras + conciliación bancaria + inventario en la misma persona permite fraude sin detección. Misma lógica para el administrador de firewall que revisa sus propios logs. |
| 18 | UA5 | **B** | ISO 27001 exige mejora continua (PDCA): auditorías internas periódicas, revisión por la dirección y actualización del SGSI. Una certificación no se mantiene solo con revisiones externas anuales mínimas. |
| 19 | UA6 | **B** | El RGPD exige garantías para transferencias internacionales (decisión de adecuación o SCC). Sin DPF ni SCC, la transferencia de datos de ciudadanos UE a EE.UU. es ilícita. El RGPD tiene efecto extraterritorial (art. 3). |
| 20 | UA6 | **B** | RGPD art. 33-34: notificar brecha a la AEPD en ≤72h y comunicar a los afectados si hay alto riesgo. Los datos de salud son categorías especiales (art. 9) → riesgo alto inherente → obligación de comunicar a pacientes. |

---

> **Fin del Examen 02: Casos Prácticos**
> [← Volver al README](../README.md) | [← Simulacro 01](01-teoria-general.md) | [Simulacro 03 →](03-nivel-experto.md)
