# Examen 03: Nivel Experto

> 📚 [← README](../README.md) | [← Simulacro 02](02-casos-practicos.md)

---

## UA 1. SEGURIDAD DE LA INFORMACIÓN: UNA VISIÓN INTEGRAL (3 preguntas)

### 1. Respecto al principio de defensa en profundidad (defense in depth), ¿cuál de las siguientes afirmaciones es INCORRECTA?

- A) La defensa en profundidad postula que deben desplegarse múltiples capas de controles de seguridad superpuestos, de modo que si una capa falla, las restantes puedan contener o detectar el ataque.
- B) La defensa en profundidad abarca controles físicos (vallado, guardias, CCTV), técnicos (firewalls, IDS, cifrado) y administrativos (políticas, formación, procedimientos).
- C) Implementar defensa en profundidad garantiza que un sistema es invulnerable, ya que un atacante que supere N capas de seguridad siempre será detectado por la capa N+1.
- D) Un ejemplo canónico de defensa en profundidad es combinar firewall perimetral, segmentación de red interna mediante VLANs, autenticación multifactor, cifrado en reposo y monitorización continua con SIEM.

---

### 2. Durante la investigación de un incidente, se descubre que un empleado del departamento financiero ha leído expedientes médicos de otros empleados almacenados en una carpeta de red sin permisos adecuados. El empleado no ha modificado ni borrado nada: solo ha leído. ¿Cuál de las siguientes afirmaciones describe con mayor precisión qué dimensiones de la seguridad se han visto comprometidas?

- A) Únicamente la Disponibilidad, porque la carpeta de red no estaba correctamente protegida frente a accesos no autorizados.
- B) La Confidencialidad y la Integridad, porque el acceso indebido vulnera tanto el secreto de los datos como su fiabilidad.
- C) Principalmente la Confidencialidad, puesto que se ha producido un acceso no autorizado a información que debería ser secreta, sin que necesariamente se haya vulnerado la Integridad ni la Disponibilidad.
- D) La Autenticación y el No Repudio, porque el empleado ha accedido con sus credenciales legítimas y no puede negar haber leído los expedientes, siendo esto independiente de la Confidencialidad.

---

### 3. La segregación de funciones (separation of duties) y el principio de mínimo privilegio (least privilege) son dos conceptos complementarios pero distintos. ¿Cuál de las siguientes situaciones ilustra correctamente la APLICACIÓN CONJUNTA de ambos principios?

- A) Un administrador de sistemas tiene acceso root a todos los servidores, pero debe registrar cada acceso en un formulario en papel para que quede constancia ante auditoría.
- B) Un desarrollador puede desplegar código en producción directamente, siempre que el despliegue se realice fuera del horario laboral y con notificación previa al equipo de QA.
- C) La persona que solicita una transferencia bancaria no es la misma que la autoriza, y además cada una dispone únicamente de los permisos de acceso al sistema estrictamente necesarios para realizar su función específica.
- D) Todos los empleados del departamento de TI comparten la misma cuenta de administrador para agilizar las intervenciones de urgencia, pero las acciones se registran en un SIEM centralizado con alertas en tiempo real.

---

## UA 2. FUNDAMENTOS EN SEGURIDAD DIGITAL (8 preguntas)

### 4. ¿Cuál de las siguientes consecuencias es ESPECÍFICA de la reutilización de un mismo nonce (par clave, nonce repetido) en el modo de operación AES-GCM, y NO ocurre necesariamente en otros modos AEAD como ChaCha20-Poly1305?

- A) El atacante puede recuperar el texto claro de ambos mensajes realizando XOR entre los dos textos cifrados.
- B) El atacante puede recuperar la subclave de autenticación H de GHASH y, a partir de ese momento, forjar tags de autenticación válidos para cualquier texto cifrado arbitrario: rompiendo la integridad del canal de forma definitiva.
- C) El atacante puede derivar la clave simétrica AES original a partir de los dos textos cifrados, permitiendo descifrar todos los mensajes pasados y futuros protegidos con dicha clave.
- D) El atacante puede provocar una denegación de servicio haciendo que el servidor rechace todos los mensajes subsiguientes con tags de autenticación incorrectos.

---

### 5. Un administrador inspecciona un certificado X.509 con OpenSSL y entre la salida observa los siguientes dos campos:

```
X509v3 Key Usage: critical
    Digital Signature, Key Encipherment
X509v3 Extended Key Usage:
    TLS Web Server Authentication, TLS Web Client Authentication
```

¿Qué indica simultáneamente la presencia de `Key Encipherment` y `TLS Web Client Authentication` en este certificado?

- A) Que el certificado puede usarse tanto para autenticar un servidor web (HTTPS) como para que el titular firme digitalmente documentos PDF con validez legal según eIDAS.
- B) Que el certificado es necesariamente de tipo Extended Validation (EV), ya que solo los EV permiten combinar Key Encipherment con TLS Web Client Authentication.
- C) Que el certificado puede emplearse tanto en el lado servidor (protegiendo la clave de sesión durante el handshake TLS) como en el lado cliente (autenticando al usuario ante un servidor que requiera certificado de cliente).
- D) Que la clave privada asociada a este certificado se ha generado en un HSM (Hardware Security Module) con nivel FIPS 140-2 Nivel 3, requisito obligatorio para combinar ambas extensiones.

---

### 6. ¿Cuál de las siguientes afirmaciones sobre los sistemas de verificación del estado de los certificados: CRL (Certificate Revocation List) y OCSP (Online Certificate Status Protocol): es correcta?

- A) La CRL es un mecanismo en tiempo real: el cliente consulta a la CA cada vez que necesita verificar un certificado; OCSP, en cambio, descarga periódicamente una lista completa de certificados revocados.
- B) OCSP Stapling permite al servidor TLS adjuntar una respuesta OCSP firmada y con timestamp durante el handshake, eliminando la necesidad de que el cliente realice una consulta OCSP independiente a la CA y preservando así su privacidad.
- C) Ambos mecanismos: CRL y OCSP: garantizan que un certificado recién revocado sea detectado instantáneamente por todos los clientes, sin ventana de vulnerabilidad entre la revocación y la detección.
- D) OCSP es obligatorio en TLS 1.3 mientras que CRL es obligatorio en TLS 1.2; un servidor que no soporte OCSP no puede establecer conexiones TLS 1.3.

---

### 7. En relación con la generación de números aleatorios en criptografía, ¿cuál de las siguientes afirmaciones es correcta?

- A) Un PRNG (Pseudo-Random Number Generator) correctamente sembrado con suficiente entropía de fuentes hardware (como `/dev/random` en Linux) produce números indistinguibles de los generados por un TRNG (True Random Number Generator) basado en fenómenos físicos, y es seguro para generar claves criptográficas.
- B) `/dev/urandom` en Linux es inseguro para fines criptográficos porque, a diferencia de `/dev/random`, no bloquea cuando la entropía estimada se agota, pudiendo devolver números predecibles.
- C) Un CSPRNG (Cryptographically Secure PRNG) como el utilizado por OpenSSL no necesita ser resombrado (reseeding) periódicamente, ya que la aleatoriedad inicial se mantiene de forma perpetua gracias a la naturaleza determinista del algoritmo.
- D) Los generadores cuánticos de números aleatorios (QRNG) son la única fuente aceptable de aleatoriedad para generar claves RSA-4096 según FIPS 140-3; los PRNG sembrados con entropía de sistema se consideran inseguros.

---

### 8. En criptografía de curva elíptica, ¿qué afirmación describe correctamente la relación entre el tamaño de clave simétrica equivalente y el tamaño de clave de curva elíptica, según las recomendaciones de seguridad actuales (NIST, ENISA)?

- A) Una clave de curva elíptica de 256 bits proporciona aproximadamente el mismo nivel de seguridad que una clave simétrica AES de 128 bits, mientras que para alcanzar el equivalente a AES-256 se necesita una curva de aproximadamente 512 bits.
- B) Una clave de curva elíptica de 256 bits equivale aproximadamente a una clave RSA de 256 bits, ya que ambos algoritmos están basados en problemas matemáticos de dificultad equivalente.
- C) Una clave de curva elíptica de 521 bits (como NIST P-521) proporciona un nivel de seguridad equivalente a AES-256, aproximadamente.
- D) La seguridad de las curvas elípticas escala linealmente con el tamaño de clave: al doblar el número de bits se dobla la seguridad: mientras que RSA escala de forma logarítmica, lo que hace a ECC más eficiente.

---

### 9. ¿Cuál es la diferencia fundamental entre una sal criptográfica (salt) y un nonce (number used once) en el contexto de funciones de derivación de clave (KDF) como PBKDF2?

- A) La sal es secreta y debe almacenarse cifrada, mientras que el nonce se hace público y se envía en texto claro junto al texto cifrado.
- B) La sal se utiliza para evitar ataques de diccionario y rainbow tables en el almacenamiento de contraseñas hasheadas, mientras que el nonce se utiliza para garantizar la unicidad de cada operación de cifrado incluso con la misma clave: ambos se almacenan en texto claro junto con el resultado.
- C) La sal y el nonce son términos intercambiables; la única diferencia es que "salt" es la nomenclatura usada en UNIX y "nonce" en TLS.
- D) La sal debe tener un tamaño fijo de 16 bytes mientras que el nonce debe tener un mínimo de 32 bytes según el estándar FIPS 198-1.

---

### 10. Dada una función hash criptográfica H que produce resúmenes de n bits, ¿cuál de las siguientes afirmaciones cuantifica correctamente la resistencia a colisiones esperada, asumiendo que H es una función hash ideal (modelo de oráculo aleatorio)?

- A) Encontrar una colisión (dos mensajes M1 ≠ M2 con H(M1) = H(M2)) requiere aproximadamente 2^n operaciones, mientras que encontrar una preimagen requiere 2^(n/2) operaciones.
- B) Encontrar una colisión requiere aproximadamente 2^(n/2) operaciones debido a la paradoja del cumpleaños, mientras que encontrar una preimagen o segunda preimagen requiere aproximadamente 2^n operaciones.
- C) La resistencia a colisiones es siempre el doble de la resistencia a preimagen: si una función hash es de 256 bits, se requieren 2^256 operaciones para encontrar una colisión y 2^128 para una preimagen.
- D) Tanto la resistencia a colisiones como la resistencia a preimagen requieren exactamente 2^(n/2) operaciones en el modelo de oráculo aleatorio, lo que implica que SHA-256 ofrece 128 bits de seguridad en ambos casos.

---

### 11. En un ataque de tipo "keystream reuse" contra un cifrador de flujo, un atacante intercepta dos textos cifrados C1 y C2 que sabe que fueron generados con la misma clave y el mismo flujo de clave (keystream). Si el atacante conoce o puede adivinar parte del texto claro P1, ¿qué operación le permite recuperar P2?

- A) C2 ⊕ C1 ⊕ P1 = P2, porque C1 = P1 ⊕ K y C2 = P2 ⊕ K, y al hacer C1 ⊕ C2 ⊕ P1 = P1 ⊕ K ⊕ P2 ⊕ K ⊕ P1 = P2 (las K y P1 se cancelan).
- B) C1 × C2 / P1 = P2, porque la operación de cifrado en flujo es multiplicativa sobre el grupo finito GF(2^128).
- C) C2 ⊕ C1 = P2, porque al cancelarse el keystream K directamente en C1 ⊕ C2 = P1 ⊕ K ⊕ P2 ⊕ K = P1 ⊕ P2 = P2 (asumiendo P1 es cero).
- D) El atacante necesita obligatoriamente una tercera muestra C3 con el mismo keystream para triangular P2; con solo dos textos cifrados el sistema de ecuaciones tiene infinitas soluciones.

---

## UA 3. AMENAZAS A LOS SISTEMAS DE INFORMACIÓN (4 preguntas)

### 12. Una organización descubre que un atacante ha comprometido el repositorio de código fuente de un proveedor de software y ha insertado una puerta trasera en la librería de autenticación que la organización utiliza en sus aplicaciones de banca electrónica. La puerta trasera permite al atacante autenticarse como cualquier usuario sin conocer su contraseña. ¿Cómo se clasifica PRINCIPALMENTE este tipo de ataque?

- A) Ataque de tipo watering hole, porque el atacante ha comprometido un recurso que sabía que los empleados de la organización visitarían o utilizarían habitualmente.
- B) Ataque de tipo Man-in-the-Middle (MitM) en la cadena de suministro (supply chain), porque el atacante ha interceptado y modificado el software durante su ciclo de desarrollo y distribución, antes de que llegara a la organización víctima.
- C) Ataque de denegación de servicio distribuido (DDoS), porque al permitir la autenticación no autorizada, el sistema legítimo queda inutilizado para los usuarios reales.
- D) Ataque de tipo phishing dirigido (spear-phishing), porque el atacante tuvo que enviar previamente un correo electrónico al proveedor de software para obtener sus credenciales y acceder al repositorio de código.

---

### 13. ¿Cuál de las siguientes afirmaciones describe correctamente un cambio específico introducido por CVSS v4.0 respecto a CVSS v3.1 en relación con la distinción entre el sistema vulnerable y los sistemas afectados subsiguientemente?

- A) CVSS v4.0 mantiene la métrica Scope (Alcance) como métrica base, pero añade la métrica "Cascade Impact" que mide la propagación del daño a sistemas dependientes que no son directamente vulnerables.
- B) CVSS v4.0 elimina la métrica binaria Scope (Changed/Unchanged) y en su lugar introduce métricas de impacto separadas para el sistema vulnerable (Vulnerable System) y el sistema subsiguiente (Subsequent System), permitiendo evaluar de forma independiente los efectos sobre cada uno.
- C) CVSS v4.0 prescinde completamente de la distinción entre sistemas, asumiendo que el impacto sobre cualquier sistema es siempre idéntico al impacto sobre el sistema vulnerable original, simplificando así la puntuación.
- D) CVSS v4.0 introduce la métrica "Attack Chain Length" que cuenta el número de sistemas intermedios que el atacante debe atravesar, reemplazando la necesidad de distinguir entre sistema vulnerable y subsiguiente.

---

### 14. ¿Cuál de los siguientes perfiles de atacante NO está definido por su motivación principal, sino por su relación contractual o de patrocinio con la organización objetivo?

- A) Hacktivista: cuya motivación es ideológica, política o social, y que busca visibilidad mediática para su causa mediante la filtración de datos o la defacement de sitios web.
- B) Insider malicioso (insider threat): un empleado, contratista o exempleado que utiliza su acceso legítimo para dañar a la organización por rencor, lucro personal o coerción externa.
- C) Cracker: un individuo con altos conocimientos técnicos que vulnera sistemas con intención deliberada de causar daño u obtener beneficio económico ilegal.
- D) Grupo APT patrocinado por un Estado-nación: cuyos recursos, objetivos y alcance temporal están condicionados por las prioridades estratégicas del Estado patrocinador, no por la motivación personal de sus miembros.

---

### 15. En relación con las botnets y sus arquitecturas de mando y control (C2), ¿cuál de las siguientes configuraciones hace más resistente a la botnet frente a intentos de desmantelamiento (takedown)?

- A) Arquitectura centralizada con un único servidor C2 alojado en un proveedor de hosting bulletproof en una jurisdicción sin tratados de extradición, usando IP fija y protocolo IRC.
- B) Arquitectura centralizada con múltiples servidores C2 redundantes, todos registrados bajo el mismo dominio pero con direcciones IP diferentes mediante DNS round-robin.
- C) Arquitectura descentralizada peer-to-peer (P2P) donde cada nodo infectado actúa simultáneamente como bot y como servidor C2, comunicándose mediante una red superpuesta (overlay) sin puntos únicos de fallo.
- D) Arquitectura centralizada con HTTP/HTTPS como protocolo C2, utilizando domain generation algorithm (DGA) para rotar diariamente entre cientos de dominios diferentes.

---

## UA 4. MECANISMOS DE DEFENSA (3 preguntas)

### 16. ¿Cuál de las siguientes afirmaciones describe correctamente la diferencia de capacidades entre un WAF (Web Application Firewall), un IPS (Intrusion Prevention System) y un NGFW (Next-Generation Firewall) en el contexto de la protección de una aplicación web?

- A) El WAF opera exclusivamente en capa 3 (red) inspeccionando direcciones IP; el IPS opera en capa 4 (transporte) bloqueando puertos; el NGFW opera en capa 7 (aplicación) analizando payloads HTTP.
- B) El WAF es el único de los tres capaz de detectar y bloquear ataques de inyección SQL y XSS analizando el contenido del tráfico HTTP/HTTPS a nivel de aplicación (capa 7), mientras que IPS y NGFW trabajan principalmente en capas 3-4.
- C) El WAF inspecciona el tráfico HTTP/HTTPS en capa 7 con reglas específicas para aplicaciones web (ej. OWASP CRS); el IPS analiza patrones de ataque y anomalías de protocolo en capas 3-7 pero sin el contexto específico de aplicación web; el NGFW integra funciones de firewall tradicional, IPS y control de aplicaciones en un solo dispositivo.
- D) El WAF, el IPS y el NGFW son funcionalmente equivalentes cuando se despliegan en modo inline y con las mismas reglas de detección: la única diferencia es el fabricante (el término WAF es de Imperva, IPS de Cisco, NGFW de Palo Alto).

---

### 17. Una startup despliega su aplicación en un proveedor de nube pública utilizando Kubernetes gestionado (managed Kubernetes, modelo PaaS). La aplicación almacena datos de clientes en una base de datos gestionada por el proveedor (DBaaS). Según el modelo de responsabilidad compartida, ¿cuál de las siguientes obligaciones de seguridad recae EXCLUSIVAMENTE sobre la startup y NO sobre el proveedor cloud?

- A) Aplicar los parches de seguridad al sistema operativo de los nodos worker del clúster Kubernetes y al motor de la base de datos.
- B) Proteger físicamente los centros de datos contra accesos no autorizados, desastres naturales y fallos de suministro eléctrico.
- C) Configurar las políticas de red (Network Policies) de Kubernetes para restringir el tráfico entre pods, implementar RBAC para el acceso al clúster, y cifrar los datos sensibles a nivel de aplicación antes de insertarlos en la base de datos.
- D) Mantener actualizado el plano de control de Kubernetes (API server, etcd, scheduler) y garantizar el cifrado de los datos en reposo en los volúmenes de almacenamiento subyacentes a la base de datos.

---

### 18. Comparando una DMZ tradicional (basada en dos firewalls físicos con subred intermedia) con una arquitectura de microsegmentación basada en software (Zero Trust), ¿cuál de las siguientes afirmaciones es correcta?

- A) En una DMZ tradicional, el tráfico entre dos servidores ubicados dentro de la misma DMZ no pasa por ningún firewall, por lo que un atacante que comprometa uno de ellos puede comunicarse libremente con el otro sin ser detectado; la microsegmentación permite definir políticas de filtrado incluso entre cargas de trabajo adyacentes dentro del mismo segmento lógico.
- B) La DMZ tradicional es inherentemente más segura que la microsegmentación porque utiliza dos firewalls físicos de fabricantes distintos (defensa en diversidad), mientras que la microsegmentación depende de un único proveedor de software.
- C) La microsegmentación solo es aplicable en entornos de nube pública (AWS, Azure, GCP) y no puede implementarse en centros de datos on-premise con infraestructura física tradicional.
- D) En una DMZ tradicional, todo el tráfico: incluyendo el tráfico entre Internet y la DMZ, y entre la DMZ y la intranet: es inspeccionado por un único firewall que aplica las mismas reglas a todos los flujos, simplificando la gestión.

---

## UA 5. INSTRUMENTOS PARA LA GESTIÓN DE LA SEGURIDAD (3 preguntas)

### 19. En el Sistema de Valor del Servicio (SVS) de ITIL v4, la Cadena de Valor del Servicio (Service Value Chain) define seis actividades interconectadas. ¿Cuál de las siguientes NO es una de esas seis actividades?

- A) Planificar (Plan): crear una comprensión compartida de la visión, estado actual y dirección de mejora de los cuatro ámbitos y productos/servicios de la organización.
- B) Diseñar y Transicionar (Design & Transition): asegurar que los productos y servicios satisfacen continuamente las expectativas de los stakeholders en cuanto a calidad, costes y tiempo de comercialización.
- C) Adquirir/Construir (Obtain/Build): asegurar que los componentes del servicio están disponibles cuando y donde se necesitan, y cumplen las especificaciones acordadas.
- D) Certificar/Auditar (Certify/Audit): verificar mediante auditorías externas que los servicios cumplen con los estándares ISO aplicables, como requisito obligatorio del SVS.

---

### 20. Una organización ha identificado un riesgo: un ataque ransomware podría cifrar sus servidores de producción. El impacto estimado es de 2 M€. La probabilidad anual se estima en un 10%. El coste de implantar un EDR avanzado con copias de seguridad inmutables asciende a 150.000 € anuales. La contratación de un ciberseguro cuesta 80.000 € anuales con una franquicia de 500.000 €. ¿Cuál es la MEJOR estrategia de tratamiento del riesgo desde un punto de vista estrictamente económico?

- A) Transferir el riesgo mediante el ciberseguro, porque 80.000 € < 150.000 € y el coste anual es menor.
- B) Eliminar el riesgo apagando los servidores de producción y externalizando el servicio a un proveedor SaaS, eliminando así por completo el vector de ataque ransomware sobre infraestructura propia.
- C) Mitigar el riesgo implantando el EDR y las copias inmutables, con un coste anual de 150.000 €, y asumir el riesgo residual: porque la pérdida esperada sin mitigación sería de 200.000 € (2 M€ × 10%) > 150.000 €, mientras que el seguro cubre el impacto pero no evita la interrupción del negocio ni el daño reputacional.
- D) Asumir el riesgo sin implantar ninguna medida, porque 200.000 € de pérdida esperada es un valor aceptable para una organización con una facturación anual de 50 M€.

---

### 21. En una auditoría de seguridad, el auditor recopila evidencias de distintos tipos. ¿Cuál de los siguientes tipos de evidencia se considera generalmente el MÁS FIABLE y con MAYOR peso probatorio en el contexto de una auditoría de cumplimiento del ENS?

- A) Evidencia testimonial: declaraciones juradas del CISO y del responsable de seguridad describiendo los controles implementados y su eficacia operativa durante el periodo auditado.
- B) Evidencia documental: políticas de seguridad firmadas por la dirección, actas de reuniones del comité de seguridad y certificados de formación del personal.
- C) Evidencia analítica: comparaciones del gasto en seguridad del ejercicio actual con ejercicios anteriores, ratios de incidentes por empleado y benchmarks sectoriales de madurez.
- D) Evidencia física y de inspección directa: observación in situ por parte del auditor de las configuraciones reales de los firewalls, registros de logs en tiempo real, y demostraciones prácticas de los controles en funcionamiento.

---

## UA 6. LEGISLACIÓN Y NORMATIVA (4 preguntas)

### 22. La Directiva NIS2 (UE 2022/2555) introduce cambios significativos respecto a la NIS original en cuanto a los plazos de notificación de incidentes. ¿Cuál de las siguientes describe correctamente el nuevo esquema de notificación?

- A) Alerta temprana en 24 horas desde la detección, notificación formal en 72 horas, informe final en 1 mes desde la notificación formal: constituyendo una notificación en tres fases con obligaciones crecientes de detalle.
- B) Alerta temprana en 12 horas, notificación formal en 24 horas e informe final en 72 horas: un esquema muy comprimido que obliga a las entidades a automatizar completamente la respuesta a incidentes.
- C) Únicamente se exige una notificación única en 72 horas que incluya simultáneamente la descripción del incidente, el impacto, las medidas adoptadas y las lecciones aprendidas, sin fases intermedias.
- D) NIS2 no modifica los plazos de notificación respecto a la NIS original, centrando sus novedades exclusivamente en la ampliación de sectores y en las sanciones a la alta dirección.

---

### 23. Según el artículo 37 del RGPD, la designación de un Delegado de Protección de Datos (DPD) es obligatoria cuando concurren determinados supuestos. Una empresa privada de 300 empleados desarrolla una aplicación móvil de salud que monitoriza constantes vitales (frecuencia cardíaca, nivel de glucosa) de 500.000 usuarios en toda la UE. ¿Está obligada a designar un DPD?

- A) No, porque es una empresa privada y el RGPD solo exige DPD para organismos y autoridades públicas, independientemente del volumen o naturaleza de los datos tratados.
- B) Sí, porque concurren al menos dos de los supuestos del artículo 37: el tratamiento a gran escala de categorías especiales de datos (datos de salud) y la observación habitual y sistemática de interesados a gran escala.
- C) No, porque con 300 empleados no alcanza el umbral mínimo de 500 empleados que establece el RGPD para la obligatoriedad del DPD en empresas privadas.
- D) Sí, pero solo si la autoridad de control del Estado miembro donde tiene su establecimiento principal lo exige expresamente mediante resolución motivada, ya que el RGPD delega en las autoridades nacionales la decisión final.

---

### 24. Respecto a las guías CCN-STIC, ¿cuál de las siguientes asociaciones entre la guía y su propósito es INCORRECTA?

- A) CCN-STIC 401: Glosario de términos y abreviaturas del Centro Criptológico Nacional.
- B) CCN-STIC 801: Esquema Nacional de Seguridad: responsabilidades y funciones.
- C) CCN-STIC 825: Guía de seguridad en servicios cloud para administraciones públicas.
- D) CCN-STIC 1401: Guía de aplicación del principio de transparencia en el tratamiento de datos personales según el RGPD para el Sector Público Estatal.

---

### 25. Una entidad local (ayuntamiento de 15.000 habitantes) gestiona un sistema de información que, en la dimensión de Disponibilidad, está categorizado como MEDIO porque una interrupción podría causar un perjuicio significativo a los ciudadanos. En las dimensiones de Confidencialidad e Integridad, el sistema está categorizado como BAJO. Según el Esquema Nacional de Seguridad (RD 311/2022), ¿qué categoría global tiene el sistema y qué mecanismo de verificación de la conformidad le corresponde?

- A) Categoría BAJO, porque la mayoría de las dimensiones (dos de tres) tienen esa categoría, y le corresponde autoevaluación cada 2 años.
- B) Categoría MEDIO, porque un sistema hereda la categoría más alta de entre todas las dimensiones de seguridad evaluadas. Al ser MEDIO en Disponibilidad, el sistema es globalmente MEDIO y requiere auditoría externa por entidad acreditada por ENAC cada 2 años.
- C) Categoría MEDIO, pero al tratarse de una entidad local con menos de 20.000 habitantes, el ENS exime de la obligación de auditoría y permite una autoevaluación voluntaria sin periodicidad fija.
- D) Categoría ALTO, porque toda entidad pública está obligada a tratar sus sistemas con la categoría máxima como garantía frente a los ciudadanos, independientemente del análisis de dimensiones.

---

---

## 📋 Soluciones

### 1. C: Implementar defensa en profundidad garantiza que un sistema es invulnerable

La defensa en profundidad es una estrategia de superposición de capas que **reduce** la probabilidad de éxito de un ataque, pero **NO garantiza invulnerabilidad**. Afirmar lo contrario es falso y peligroso: ningún sistema es 100 % seguro. La opción A describe correctamente el principio de capas múltiples. La opción B enumera correctamente los tres tipos de controles (físicos, técnicos, administrativos). La opción D es un ejemplo realista de defensa en profundidad bien implementada. La trampa está en la palabra "garantiza", que convierte una afirmación razonable en una falsedad absoluta. La seguridad plena es una utopía, y la defensa en profundidad mitiga el riesgo, no lo elimina por completo.

---

### 2. C: Principalmente la Confidencialidad, sin que se haya vulnerado la Integridad ni la Disponibilidad

El empleado **leyó** datos sin autorización: la lectura es un acceso no autorizado que vulnera la **Confidencialidad** (la información debe ser solo accesible por autorizados). Al no haber modificado ni borrado nada, la **Integridad** no se ha visto afectada (los datos siguen siendo fiables). La **Disponibilidad** tampoco se ha visto comprometida (los datos siguen estando accesibles para quien los necesita). La opción A es incorrecta porque el acceso no autorizado afecta a la Confidencialidad, no a la Disponibilidad. La B añade erróneamente Integridad. La D es incorrecta: aunque las credenciales sean legítimas, el acceso fue a datos para los que el empleado no tenía autorización, y esto no es un fallo de Autenticación (el empleado sí era quien decía ser) sino de autorización/confidencialidad.

---

### 3. C: La persona que solicita no es la que autoriza, y cada una tiene solo los permisos necesarios

La opción C ilustra perfectamente ambos principios: **segregación de funciones** (quien solicita ≠ quien autoriza: nadie puede completar una transacción en solitario) y **mínimo privilegio** (cada persona tiene solo los permisos estrictamente necesarios, no más). La opción A solo tiene registro a posteriori (el administrador sigue teniendo acceso root completo → sin mínimo privilegio). La opción B permite al desarrollador desplegar en producción (sin segregación de funciones con QA/operaciones). La opción D usa una cuenta compartida (viola tanto la segregación como el mínimo privilegio y la trazabilidad individual).

---

### 4. B: El atacante puede recuperar la subclave H de GHASH y forjar tags de autenticación

La consecuencia **específica** de AES-GCM ante nonce reuse es la recuperación de la subclave de autenticación **H**. Como GHASH es lineal en GF(2^128), dos mensajes con el mismo nonce permiten resolver ecuaciones que revelan H. Una vez conocido H, el atacante puede calcular el tag de autenticación correcto para **cualquier** texto cifrado arbitrario: la integridad del canal queda completamente rota. La opción A (XOR de textos claros) ocurre en todos los modos AEAD que usan modo contador (GCM, CCM, ChaCha20-Poly1305), no es específica de GCM. La opción C es falsa: el nonce reuse no revela la clave AES maestra. La opción D no es una consecuencia real significativa del nonce reuse.

---

### 5. C: El certificado sirve tanto del lado servidor (protegiendo la clave de sesión) como del lado cliente (autenticación mutua)

`Key Encipherment` permite que el titular reciba claves de sesión cifradas con su clave pública (función típica del servidor en el handshake TLS: el cliente cifra la pre-master secret con la clave pública del servidor). `TLS Web Client Authentication` permite que el certificado se presente como credencial de cliente (autenticación mutua). La combinación de ambos en un mismo certificado significa que puede usarse en ambos roles. La opción A es falsa: `Digital Signature` ya habilita firma de documentos. La opción B es falsa: la combinación de extensiones no es exclusiva de EV. La opción D es falsa: no hay requisito de HSM para combinar estas extensiones.

---

### 6. B: OCSP Stapling permite al servidor adjuntar una respuesta OCSP firmada con timestamp durante el handshake

**OCSP Stapling** es una optimización de privacidad: en lugar de que cada cliente pregunte a la CA "¿este certificado sigue siendo válido?" (revelando qué sitios visita), el propio servidor obtiene periódicamente una respuesta OCSP firmada por la CA y la adjunta durante el handshake TLS. El cliente verifica que la respuesta es reciente (timestamp) y está firmada por la CA. La opción A invierte CRL y OCSP: la CRL es una lista descargada periódicamente, OCSP es consulta en tiempo real. La opción C es falsa: ambos mecanismos tienen ventana de vulnerabilidad (la CRL se publica periódicamente, OCSP puede cachearse). La opción D es falsa: ni CRL ni OCSP son obligatorios en ninguna versión de TLS.

---

### 7. A: Un PRNG correctamente sembrado produce números indistinguibles de un TRNG y es seguro para generar claves

Un **CSPRNG** (Cryptographically Secure Pseudo-Random Number Generator) como el que implementa `/dev/urandom`, debidamente sembrado con entropía suficiente, genera secuencias indistinguibles de aleatoriedad verdadera y es perfectamente válido para claves criptográficas. La opción B es un mito: `/dev/urandom` es criptográficamente seguro en Linux moderno; `/dev/random` bloquea innecesariamente y no es mejor. La opción C es falsa: los CSPRNG deben ser resombrados periódicamente para garantizar forward/backward secrecy. La opción D es falsa: FIPS 140-3 acepta CSPRNG sembrados con entropía hardware; los QRNG no son la única fuente aceptable.

---

### 8. A: 256 bits ECC ≈ 128 bits simétrico; 512 bits ECC ≈ 256 bits simétrico

La seguridad de las curvas elípticas escala aproximadamente como **la mitad del tamaño de clave comparado con el nivel simétrico** (debido a que el mejor ataque conocido: Rho de Pollard: requiere O(2^(n/2))). Así, ECC-256 ≈ AES-128 y ECC-512 ≈ AES-256. La opción B es absurda: 256 bits ECC no equivalen a 256 bits RSA; RSA requiere ~3072 bits para igualar 128 bits simétricos. La opción C es incorrecta: P-521 (521 bits) proporciona ~260 bits de seguridad simétrica, no exactamente 256. La opción D es falsa: la seguridad de ECC NO escala linealmente sino con O(2^(n/2)).

---

### 9. B: La sal evita rainbow tables y ataques de diccionario en contraseñas; el nonce garantiza unicidad del cifrado

La **sal** y el **nonce** se almacenan ambos en texto claro junto al resultado. La sal se usa en hash de contraseñas para que dos usuarios con la misma contraseña tengan hashes diferentes y para forzar rainbow tables por usuario. El nonce (o IV) se usa en cifrado para garantizar que dos mensajes idénticos con la misma clave produzcan textos cifrados diferentes. La opción A es falsa: la sal no es secreta: si lo fuera sería pimienta (pepper). La opción C es falsa: no son intercambiables, tienen propósitos distintos. La opción D es falsa: la sal no tiene tamaño fijo (aunque se recomienda ≥16 bytes), y el nonce en GCM recomendado es 96 bits (12 bytes).

---

### 10. B: Colisión: 2^(n/2) por la paradoja del cumpleaños; preimagen: 2^n

Esta es la distinción fundamental. La resistencia a **colisiones** se ve afectada por la **paradoja del cumpleaños**: en un espacio de 2^n valores, solo se necesitan aproximadamente 2^(n/2) intentos para encontrar dos que coincidan (no uno que coincida con otro específico, sino dos cualesquiera). En cambio, la **resistencia a preimagen** (dado H, encontrar M tal que hash(M)=H) y a **segunda preimagen** (dado M1, encontrar M2≠M1 con mismo hash) requieren aproximadamente 2^n operaciones. Esta es la razón por la que SHA-256 tiene 128 bits de seguridad contra colisiones pero 256 bits contra preimagen. La opción A intercambia los valores. C y D son incorrectas.

---

### 11. A: C2 ⊕ C1 ⊕ P1 = P2

En un cifrador de flujo: C1 = P1 ⊕ K y C2 = P2 ⊕ K (misma K por reutilización). Entonces C1 ⊕ C2 = P1 ⊕ K ⊕ P2 ⊕ K = P1 ⊕ P2 (el keystream se cancela). Si conocemos P1: C2 ⊕ C1 ⊕ P1 = C2 ⊕ (P1 ⊕ P2) ⊕ P1 = C2 ⊕ P2 = P2 ⊕ K ⊕ P2 = K: y luego K ⊕ C2 = P2. Más directamente: C1 ⊕ C2 = P1 ⊕ P2 → P2 = P1 ⊕ C1 ⊕ C2. La opción B usa multiplicación que no es relevante para XOR de flujo. La opción C omite P1 incorrectamente. La opción D es falsa porque solo dos textos cifrados son suficientes si se conoce parcialmente P1.

---

### 12. B: Ataque de tipo supply chain en la cadena de suministro

El ataque descrito es el paradigma del **supply chain attack**: comprometer un eslabón de la cadena de suministro de software (el proveedor de la librería de autenticación) para que el código malicioso se distribuya a todos los clientes que utilizan ese componente. El ejemplo real: SolarWinds (2020). La opción A es incorrecta (watering hole compromete un sitio web que las víctimas visitan, no una librería de software). La opción C es absurda (DDoS busca interrumpir el servicio, no acceder con cuentas legítimas). La opción D es especulativa y no clasifica el ataque: incluso si el vector inicial fue phishing, la clasificación principal es supply chain.

---

### 13. B: CVSS v4.0 elimina Scope binario e introduce métricas separadas para Vulnerable System y Subsequent System

Uno de los cambios estructurales de CVSS v4.0 es eliminar la problemática métrica binaria Scope (Changed/Unchanged) de v3.x y sustituirla por métricas de impacto independientes para el **Vulnerable System** (el sistema que contiene la vulnerabilidad) y el **Subsequent System** (sistemas afectados tras un cambio de alcance). Esto permite evaluar impactos de confidencialidad, integridad y disponibilidad por separado en ambos sistemas. La opción A es falsa porque Scope se elimina, no se mantiene. La opción C es falsa porque no se prescinde de la distinción, sino que se refina. La opción D es falsa: "Attack Chain Length" no existe en CVSS v4.0.

---

### 14. D: Grupo APT patrocinado por un Estado-nación

La pregunta pide identificar el perfil que NO se define por su motivación principal sino por su relación de patrocinio. El **hacktivista** (A) se define por motivación ideológica. El **insider malicioso** (B) se define por motivación (rencor, lucro). El **cracker** (C) se define por motivación maliciosa. El **APT patrocinado por un Estado-nación** (D) se define por quién lo patrocina y para qué fines estratégicos: los miembros individuales pueden tener motivaciones variadas (patriotismo, dinero, coerción), pero es el patrocinio estatal lo que define al grupo como APT y determina sus recursos, persistencia y objetivos.

---

### 15. C: Arquitectura descentralizada P2P sin puntos únicos de fallo

Una botnet P2P donde cada nodo actúa como par en una red superpuesta es extremadamente difícil de desmantelar porque **no existen puntos únicos de fallo**: no hay servidores C2 centrales que puedan ser confiscados o desconectados. Para desmantelarla, las fuerzas de seguridad necesitan comprometer una mayoría significativa de los nodos o infiltrar un mensaje de "desinfección" en el protocolo P2P. La opción A (único servidor) tiene punto único. La B (mismo dominio) también: basta confiscar el dominio. La D (DGA) es más resistente que las anteriores, pero sigue siendo centralizada en su lógica: el tráfico fluye a servidores identificables.

---

### 16. C: WAF (capa 7, contexto de app web), IPS (capas 3-7, sin contexto de app), NGFW (firewall + IPS + control de apps integrado)

El WAF analiza el tráfico HTTP/HTTPS en capa 7 con reglas específicas de aplicación web (OWASP CRS, inyección SQL, XSS). El IPS inspecciona tráfico en capas 3 a 7 pero con firmas genéricas de ataques de red, no con conocimiento del contexto de una aplicación web concreta. El NGFW unifica firewall de red, IPS y control de aplicaciones en un dispositivo. La opción A invierte las capas incorrectamente. La B es falsa porque los NGFW modernos también trabajan en capa 7. La D es falsa: no son equivalentes; cada uno tiene capacidades y ámbito distintos.

---

### 17. C: La startup debe configurar Network Policies, RBAC y cifrar datos sensibles a nivel de aplicación

En un modelo **PaaS** con Kubernetes gestionado, el proveedor gestiona el plano de control y los nodos worker, pero la **configuración de seguridad del clúster** recae en el cliente. Las Network Policies, el RBAC, la configuración de los pods, y especialmente el **cifrado a nivel de aplicación** de los datos antes de insertarlos en la base de datos son responsabilidad exclusiva de la startup. La opción A (parches de SO de nodos y motor BD) recae en el proveedor en PaaS/DBaaS. La opción B (seguridad física del datacenter) siempre es responsabilidad del proveedor. La opción D (plano de control de Kubernetes, cifrado en reposo de volúmenes) recae en el proveedor en managed Kubernetes.

---

### 18. A: En DMZ tradicional, el tráfico entre servidores dentro de la misma DMZ no pasa por firewall; la microsegmentación permite filtrar incluso entre cargas adyacentes

Esta es la limitación fundamental de la DMZ tradicional: una vez dentro de la subred DMZ, el tráfico **este-oeste** (entre servidores dentro de la misma DMZ) no atraviesa ningún firewall y, por tanto, no es inspeccionado ni filtrado. Un atacante que comprometa el servidor web puede escanear y atacar al servidor de aplicaciones en la misma DMZ sin obstáculos. La microsegmentación resuelve esto permitiendo políticas de firewall entre cada carga de trabajo individual, independientemente de su ubicación de red. La opción B es falsa: la microsegmentación puede complementarse con defensa en diversidad. La opción C es falsa: la microsegmentación es factible on-premise con soluciones como VMware NSX. La opción D describe una arquitectura incorrecta (DMZ típica usa dos firewalls).

---

### 19. D: Certificar/Auditar (Certify/Audit) NO es una actividad de la Cadena de Valor de ITIL v4

Las seis actividades de la Service Value Chain de ITIL v4 son: **Planificar** (Plan), **Mejorar** (Improve), **Involucrar** (Engage), **Diseñar y Transicionar** (Design & Transition), **Adquirir/Construir** (Obtain/Build) y **Entregar y Soportar** (Deliver & Support). "Certificar/Auditar" NO es una de ellas: es un concepto ajeno a la cadena de valor. Las opciones A, B y C describen correctamente tres de las seis actividades reales (Plan, Design & Transition, Obtain/Build). La trampa está en que D suena plausible en un contexto de cumplimiento normativo, pero no forma parte del modelo ITIL v4.

---

### 20. C: Mitigar con EDR + copias inmutables (150 k€) y asumir el residual, porque la pérdida esperada (200 k€) supera el coste de mitigación

Desde el punto de vista económico: **pérdida esperada sin mitigación** = 2 M€ × 10 % = 200.000 €/año. El coste de mitigación es 150.000 €/año < 200.000 € → **conviene mitigar**. El seguro (A) cuesta 80.000 € pero la franquicia de 500.000 € significa que el primer medio millón lo paga la organización; además, el seguro no cubre daños reputacionales ni la interrupción del negocio. La opción B (eliminar) puede no ser viable si los servidores son necesarios. La opción D (asumir) es incorrecta porque 200.000 € de pérdida esperada > 150.000 € de mitigación. La mejor estrategia es mitigar con EDR+copias y asumir el riesgo residual.

---

### 21. D: Evidencia física y de inspección directa: observación in situ de configuraciones, logs y demostraciones prácticas

En auditoría, la evidencia **más fiable** es la obtenida directamente por el auditor mediante inspección ocular y comprobación práctica. Ver las configuraciones reales en los dispositivos, los logs generándose en tiempo real y los controles en funcionamiento tiene más peso que lo que alguien declara (testimonial), lo que está documentado (papel que puede no reflejar la realidad) o lo que se infiere de ratios (analítica). Según la jerarquía de evidencias de auditoría (ISACA, ISO 19011), la inspección directa es el nivel más alto de fiabilidad, seguida de la evidencia documental externa, la documental interna y finalmente la testimonial.

---

### 22. A: Alerta temprana en 24 h, notificación formal en 72 h, informe final en 1 mes: tres fases

NIS2 establece un sistema de notificación en **tres fases**: (1) **alerta temprana** en 24 horas desde la detección con información mínima, (2) **notificación formal** en 72 horas con una evaluación inicial del incidente, su gravedad e impacto, y (3) **informe final detallado** en el plazo de 1 mes desde la notificación formal, incluyendo una descripción exhaustiva, el tipo de incidente, las medidas aplicadas y, si procede, las lecciones aprendidas. La opción B invierte erróneamente plazos (12/24/72 h no es correcto). La opción C ignora el sistema de fases. La opción D es falsa.

---

### 23. B: Sí, porque concurren al menos dos supuestos: categorías especiales de datos (salud) y observación sistemática a gran escala

La empresa trata **datos de salud** (constantes vitales, nivel de glucosa), que son categorías especiales de datos (art. 9 RGPD), y lo hace **a gran escala** (500.000 usuarios) con **observación habitual y sistemática**. Esto activa dos de los tres supuestos del artículo 37: tratamiento a gran escala de categorías especiales y observación sistemática a gran escala. La opción A es falsa: las empresas privadas también están obligadas cuando concurren los supuestos. La opción C es falsa: el RGPD no establece un umbral de número de empleados. La opción D es falsa: la obligación deriva directamente del RGPD, no de una resolución de la autoridad nacional.

---

### 24. C: CCN-STIC 825: Guía de seguridad en servicios cloud para administraciones públicas

La guía **CCN-STIC 825** no existe con ese propósito concreto. Las guías de la serie 800 están relacionadas con el ENS, pero la 825 no corresponde a la descripción indicada. Las guías CCN-STIC sobre cloud son las de la serie 800 (ej: CCN-STIC 823 sobre cloud). La opción A es correcta: la CCN-STIC 401 es efectivamente el glosario del CCN. La opción B es correcta: la 801 aborda responsabilidades y funciones en el ENS. La opción D es correcta: la 1401 aborda transparencia y RGPD en el sector público estatal. La opción C es la única incorrecta por no corresponder la numeración al propósito descrito.

---

### 25. B: Categoría MEDIO (hereda la más alta entre dimensiones) y requiere auditoría externa por ENAC cada 2 años

Según el ENS (RD 311/2022, art. 43), la categoría global del sistema es la **más alta** de entre todas las dimensiones de seguridad evaluadas (Confidencialidad, Integridad, Disponibilidad, Autenticidad y Trazabilidad). Si Disponibilidad es MEDIO, el sistema es globalmente MEDIO. Los sistemas de categoría MEDIA requieren **auditoría externa por entidad acreditada por ENAC** cada 2 años. La opción A es falsa porque la categoría no se determina por mayoría. La opción C es falsa: los ayuntamientos están obligados igual que el resto de AAPP, sin exención por tamaño. La opción D es falsa: no todo sistema público es ALTO por defecto; la categorización depende del análisis de dimensiones.

---

> 📚 [← README](../README.md) | [← Simulacro 02](02-casos-practicos.md)
