# Examen 01 — Teoría General

> 📚 [← README](../README.md) | [Simulacro 02 →](02-casos-practicos.md)

---

**Asignatura:** Seguridad de la Información — ULPGC
**Nivel:** FÁCIL/MEDIO (repaso general)
**Preguntas:** 25 tipo test (4 opciones)
**Temas:** UA1–UA6 (Conceptos, Criptografía, Amenazas, Defensa, Gestión, Legislación)

---

## UA 1 — Conceptos Fundamentales (6 preguntas)

### 1. ¿Cuál de las siguientes afirmaciones sobre la Seguridad de la Información es FALSA?

- A) Protege la información con independencia del medio físico donde se almacene
- B) Se limita exclusivamente a proteger los datos dentro de los sistemas informáticos de la organización
- C) Incluye entre sus dimensiones la Disponibilidad, Integridad y Confidencialidad
- D) Considera el No Repudio y la Autenticación como dimensiones adicionales a las tres clásicas

### 2. Un empleado borra accidentalmente la base de datos de clientes y no existen copias de seguridad. ¿Qué dimensión de la seguridad se ha visto comprometida PRINCIPALMENTE?

- A) Confidencialidad
- B) Integridad
- C) Disponibilidad
- D) No Repudio

### 3. ¿En qué se diferencia la Seguridad Informática de la Seguridad de la Información?

- A) La Seguridad Informática protege hardware; la Seguridad de la Información protege software
- B) La Seguridad Informática se centra en el procesamiento de datos en sistemas informáticos; la Seguridad de la Información abarca cualquier medio físico (papel, digital, verbal)
- C) Son términos sinónimos sin diferencia conceptual
- D) La Seguridad Informática es más amplia que la Seguridad de la Información

### 4. Según el temario, ¿cuál de las siguientes NO es una característica exigible a una Política de Seguridad?

- A) Inteligible y comprensible para todos los implicados
- B) De obligado cumplimiento con mecanismos de auditoría
- C) Secreta y de acceso restringido solo a la dirección
- D) Mejorable mediante mecanismos de autoevaluación y actualización

### 5. Para acceder a su banca online, un usuario introduce una contraseña (algo que sabe) y el banco le envía un código de un solo uso a su teléfono móvil (algo que tiene). ¿Qué tipo de autenticación está utilizando?

- A) Autenticación simple por contraseña
- B) Autenticación de doble factor (2FA)
- C) Autenticación biométrica
- D) Autenticación basada únicamente en posesión

### 6. ¿Qué relación describe correctamente la cadena vulnerabilidad → amenaza → riesgo → incidente?

- A) Una vulnerabilidad es una amenaza que se ha materializado, generando un incidente
- B) Una amenaza explota una vulnerabilidad; el riesgo es la probabilidad de que eso ocurra ponderada por el impacto; el incidente es la materialización del riesgo
- C) Riesgo y vulnerabilidad son sinónimos; la amenaza es el resultado de ambos
- D) La amenaza genera el riesgo, que a su vez crea la vulnerabilidad y desencadena el incidente

---

## UA 2 — Criptografía (7 preguntas)

### 7. ¿Qué efecto visual se produciría al cifrar una imagen fotográfica con AES en modo ECB?

- A) La imagen cifrada sería completamente irreconocible y sin patrones
- B) La imagen cifrada conservaría siluetas y patrones reconocibles porque bloques idénticos de color producen bloques cifrados idénticos
- C) El cifrado fallaría porque ECB no admite archivos de imagen
- D) La imagen resultante ocuparía el doble de espacio

### 8. ¿Por qué en la práctica se utiliza casi siempre un sistema de cifrado híbrido (asimétrico + simétrico) en lugar de cifrar todo con RSA?

- A) Porque RSA es menos seguro que AES para archivos grandes
- B) Porque el cifrado asimétrico es varios órdenes de magnitud más lento que el simétrico para grandes volúmenes de datos
- C) Porque la legislación obliga a combinar ambos tipos de cifrado
- D) Porque el cifrado simétrico no puede garantizar la confidencialidad por sí solo

### 9. ¿Cuál de las siguientes afirmaciones sobre las funciones de resumen (hash) es FALSA?

- A) Producen una salida de longitud fija independientemente del tamaño de la entrada
- B) Son unidireccionales: es computacionalmente inviable reconstruir la entrada a partir del hash
- C) Es factible encontrar dos mensajes distintos que produzcan el mismo hash en SHA-256 con los recursos computacionales actuales
- D) Un cambio mínimo en el mensaje de entrada produce un hash completamente distinto (efecto avalancha)

### 10. ¿Qué propiedad NO proporciona por sí misma una firma digital?

- A) Autenticación del origen del mensaje
- B) Integridad del contenido firmado
- C) No repudio del emisor
- D) Confidencialidad del mensaje transmitido

### 11. ¿En qué se diferencian los problemas matemáticos sobre los que se sustentan RSA y ElGamal?

- A) RSA se basa en la factorización de números enteros grandes; ElGamal en el problema del logaritmo discreto
- B) RSA se basa en el logaritmo discreto; ElGamal en la factorización
- C) Ambos se basan exclusivamente en la factorización de números primos
- D) Ambos se basan exclusivamente en el problema del logaritmo discreto

### 12. Si la clave privada de una Autoridad de Certificación (CA) raíz es comprometida por un atacante, ¿qué consecuencia inmediata se produce?

- A) Solo se ven afectados los certificados emitidos después del compromiso
- B) Todos los certificados firmados por esa CA dejan de ser confiables, ya que el atacante puede emitir certificados falsos para cualquier dominio
- C) La CA debe renovar únicamente su certificado raíz sin afectar a los certificados de los usuarios
- D) No hay consecuencias porque los certificados se validan con la clave pública, no con la privada

### 13. ¿Qué propiedad diferencia el modo CTR (Counter) del modo OFB (Output Feedback)?

- A) CTR permite acceso aleatorio y es paralelizable; OFB es inherentemente secuencial
- B) CTR no requiere IV; OFB sí lo necesita
- C) OFB es un cifrador de flujo; CTR sigue siendo un cifrador de bloque
- D) No existen diferencias significativas entre ambos modos

---

## UA 3 — Amenazas a los Sistemas (4 preguntas)

### 14. Un atacante envía un correo electrónico haciéndose pasar por el servicio de soporte técnico de la universidad, solicitando a los estudiantes que "verifiquen sus credenciales" mediante un enlace que conduce a una web falsa idéntica a la oficial. ¿Qué tipo de ataque describe este escenario?

- A) Pharming
- B) Phishing
- C) Ataque DDoS
- D) Spoofing de DNS

### 15. ¿Cuál es la diferencia principal entre el spyware y el adware?

- A) El spyware muestra publicidad no deseada; el adware roba información personal
- B) El spyware recopila información del usuario sin su consentimiento; el adware muestra publicidad, frecuentemente combinada con recolección de datos de navegación
- C) Ambos son el mismo tipo de malware con denominaciones distintas
- D) El spyware es siempre ilegal; el adware es siempre legal

### 16. ¿Cuál de las siguientes afirmaciones sobre los troyanos (troyan horses) es FALSA?

- A) Se camuflan como software legítimo para engañar al usuario y que los ejecute
- B) Pueden instalar puertas traseras (backdoors) que permiten el control remoto del sistema
- C) Se propagan automáticamente a través de la red sin necesidad de intervención del usuario
- D) Pueden llegar al sistema como archivo adjunto en un mensaje de correo electrónico

### 17. ¿Qué es una botnet?

- A) Un software antivirus que protege simultáneamente múltiples equipos en una red
- B) Una red de equipos infectados y controlados remotamente por un atacante para ejecutar actividades maliciosas coordinadas
- C) Una red privada virtual utilizada para proteger las comunicaciones internas de una organización
- D) Un protocolo estándar de encriptación para comunicaciones entre servidores

---

## UA 4 — Mecanismos de Defensa (4 preguntas)

### 18. ¿Cuál de las siguientes medidas NO se considera una buena práctica de seguridad en redes WiFi domésticas?

- A) Desactivar el protocolo WPS del router
- B) Utilizar cifrado WPA2 o WPA3 con una contraseña robusta
- C) Ocultar el SSID como medida principal de protección frente a intrusos
- D) Cambiar la contraseña de administración del router que viene por defecto

### 19. ¿Cuál es la diferencia fundamental entre un IDS (Sistema de Detección de Intrusiones) y un IPS (Sistema de Prevención de Intrusiones)?

- A) No hay diferencia práctica; realizan la misma función
- B) El IDS monitoriza el tráfico y genera alertas; el IPS puede bloquear activamente el tráfico malicioso detectado
- C) El IPS se utiliza en redes cableadas y el IDS exclusivamente en redes WiFi
- D) El IDS protege contra malware y el IPS contra accesos no autorizados

### 20. ¿Qué ventaja introduce WPA3 frente a WPA2 en la seguridad de redes WiFi?

- A) Mayor velocidad de transmisión de datos
- B) El protocolo SAE (Simultaneous Authentication of Equals) que protege frente a ataques de diccionario offline sobre la contraseña
- C) Compatibilidad total con dispositivos que solo soportan WEP
- D) Eliminación de la necesidad de utilizar cualquier tipo de contraseña

### 21. ¿Cuál es la función principal de un firewall en una red corporativa?

- A) Acelerar el tráfico de red mediante técnicas de caché
- B) Cifrar automáticamente todas las comunicaciones que atraviesan la red
- C) Filtrar el tráfico de red según reglas predefinidas, separando redes o equipos con distintos niveles de confianza
- D) Detectar y eliminar virus en los archivos que se transmiten por la red

---

## UA 5 — Gestión de la Seguridad y Legislación (4 preguntas)

### 22. Según ITIL, ¿cuál de las siguientes NO es una etapa del Ciclo de Vida del Servicio?

- A) Estrategia del Servicio
- B) Operación del Servicio
- C) Auditoría del Servicio
- D) Mejora Continua del Servicio

### 23. Una entidad financiera contrata una póliza de seguro que cubre las pérdidas económicas derivadas de un ciberataque. Según la gestión de riesgos, ¿qué estrategia está aplicando?

- A) Mitigación del riesgo
- B) Eliminación del riesgo
- C) Transferencia del riesgo
- D) Asunción del riesgo

### 24. ¿En qué se diferencia un Plan Director de Seguridad de un Plan de Respuesta ante Incidentes?

- A) Son documentos equivalentes con denominaciones intercambiables
- B) El Plan Director define la estrategia global de seguridad TIC a largo plazo; el Plan de Respuesta detalla las acciones operativas ante eventos adversos concretos
- C) El Plan Director es obligatorio por ley y el Plan de Respuesta es siempre voluntario
- D) El Plan Director aplica solo a Administraciones Públicas; el Plan de Respuesta a empresas privadas

### 25. ¿Qué normativa europea complementó y reforzó el marco de protección de datos en España, dando lugar a la actual LOPDGDD que sustituyó a la anterior LOPD?

- A) La Directiva NIS sobre seguridad de redes y sistemas
- B) El Reglamento General de Protección de Datos (RGPD / GDPR)
- C) El Esquema Nacional de Seguridad (ENS)
- D) La Ley de Servicios de la Sociedad de la Información y Comercio Electrónico (LSSI-CE)

---

## 📋 Soluciones

| # | Resp. | Explicación breve |
|---|:-----:|-------------------|
| **1** | **B** | La Seguridad de la Información NO se limita a sistemas informáticos; protege la información en cualquier medio físico (papel, digital, verbal). Esa restricción define a la Seguridad Informática, no a la SI. |
| **2** | **C** | La pérdida de la base de datos implica que la información ya no está accesible cuando se necesita: fallo de Disponibilidad. No se ha accedido sin permiso (no es Confidencialidad) ni se ha alterado subrepticiamente (no es Integridad). |
| **3** | **B** | La Seguridad Informática se circunscribe al procesamiento de datos dentro de sistemas informáticos. La Seguridad de la Información amplía el alcance a cualquier soporte. La opción A es incorrecta; C y D invierten o falsean la relación. |
| **4** | **C** | Las características son: Abarcable, Inteligible, de Obligado cumplimiento, Asequible y Mejorable. Una política debe ser conocida por todos los implicados; mantenerla secreta contradice su propósito de guiar el comportamiento organizacional. |
| **5** | **B** | Combina dos factores de autenticación distintos: conocimiento (contraseña) y posesión (móvil). Esto constituye autenticación de doble factor (2FA), el estándar actual en banca y servicios críticos. |
| **6** | **B** | La amenaza explota la vulnerabilidad (debilidad). El riesgo es la probabilidad × impacto de que esto ocurra. El incidente es cuando el riesgo se materializa. A y D invierten la causalidad; C los confunde. |
| **7** | **B** | ECB cifra cada bloque de forma independiente. Bloques idénticos de texto claro generan bloques cifrados idénticos, revelando patrones de la imagen original (el clásico "pingüino de ECB"). |
| **8** | **B** | El cifrado asimétrico (RSA) es ~1000 veces más lento que el simétrico (AES). Lo práctico es usar RSA/ECDH solo para intercambiar una clave de sesión AES y luego cifrar el grueso de datos con AES. |
| **9** | **C** | SHA-256 ofrece resistencia a colisiones: no es factible encontrar dos mensajes distintos con el mismo hash usando la tecnología actual. Si se pudiera, el algoritmo estaría criptográficamente roto. |
| **10** | **D** | La firma digital garantiza autenticación, integridad y no repudio, pero NO confidencialidad: el mensaje viaja en claro (o puede hacerlo). Para confidencialidad se requiere cifrado adicional. |
| **11** | **A** | RSA descansa sobre la dificultad de factorizar el producto de dos primos grandes. ElGamal se apoya en la dificultad de calcular logaritmos discretos en un grupo finito. Ambos son asimétricos pero con fundamentos matemáticos distintos. |
| **12** | **B** | La clave privada de la CA firma todos los certificados que emite. Si se compromete, el atacante puede generar certificados falsos para cualquier dominio, destruyendo la confianza en toda la jerarquía PKI de esa CA. |
| **13** | **A** | CTR cifra un contador incrementado para cada bloque, permitiendo procesar bloques en paralelo y acceder aleatoriamente. OFB realimenta la salida anterior, siendo secuencial por naturaleza. Ambos transforman el cifrador de bloque en flujo. |
| **14** | **B** | El phishing utiliza ingeniería social (correo fraudulento) para engañar a la víctima y que entregue sus credenciales en una web falsa. Se diferencia del pharming, que redirige mediante envenenamiento DNS sin intervención del usuario. |
| **15** | **B** | El spyware recopila sigilosamente información del usuario (pulsaciones, hábitos, credenciales). El adware muestra publicidad invasiva, a menudo rastreando la navegación. No son lo mismo (C) ni sus definiciones están invertidas (A). |
| **16** | **C** | Esa afirmación describe a los gusanos (worms), no a los troyanos. Los troyanos requieren que el usuario los ejecute voluntariamente al creer que es software legítimo. No se propagan automáticamente. |
| **17** | **B** | Una botnet es una red de dispositivos comprometidos (bots) controlados remotamente por un atacante (botmaster) para lanzar ataques DDoS, enviar spam o distribuir malware de forma coordinada. |
| **18** | **C** | Ocultar el SSID es "seguridad por oscuridad": el nombre de red se transmite en claro en múltiples tramas de gestión y es trivial de descubrir con un sniffer. No aporta protección real. Las otras opciones sí son buenas prácticas. |
| **19** | **B** | El IDS es un sistema pasivo que monitoriza y alerta. El IPS es activo: además de detectar, puede bloquear el tráfico malicioso en tiempo real. La ubicación en la red (inline vs span) refleja esta diferencia. |
| **20** | **B** | WPA3 introduce SAE (basado en Dragonfly), que sustituye al PSK de 4 vías de WPA2. SAE protege contra ataques de diccionario offline incluso si la contraseña es débil, proporcionando forward secrecy para la autenticación. |
| **21** | **C** | El firewall aplica políticas de filtrado de tráfico (por IP, puerto, protocolo, aplicación) entre zonas de confianza (ej: Internet ↔ DMZ ↔ Intranet). No acelera tráfico (A), no cifra (B) y no analiza virus (D, eso es un antivirus/UTM). |
| **22** | **C** | Las 5 etapas del Ciclo de Vida del Servicio de ITIL son: Estrategia, Diseño, Transición, Operación y Mejora Continua. "Auditoría del Servicio" no es una etapa; la evaluación y verificación se integran en la Mejora Continua. |
| **23** | **C** | Contratar un seguro traslada el impacto económico del riesgo a un tercero (la aseguradora) a cambio de una prima. Esto es Transferencia del riesgo. No se reduce la probabilidad (Mitigación), no se elimina la actividad (Eliminación) ni se acepta sin más (Asunción). |
| **24** | **B** | El Plan Director establece el marco estratégico, objetivos, inversiones y hoja de ruta plurianual de la seguridad TIC. El Plan de Respuesta a Incidentes es táctico-operativo: define quién, cómo y cuándo actuar ante un incidente concreto. |
| **25** | **B** | El RGPD (Reglamento UE 2016/679) armonizó la protección de datos en la UE con aplicación directa desde mayo de 2018. España lo complementó con la LOPDGDD (Ley Orgánica 3/2018), que sustituyó a la anterior LOPD de 1999. |

---

> **Fin del examen.** Revisa tus respuestas y compara con las soluciones. Los conceptos aquí evaluados son fundamentales y tienen alta probabilidad de aparecer en el examen oficial.
