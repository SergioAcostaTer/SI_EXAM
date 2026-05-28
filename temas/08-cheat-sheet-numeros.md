> **Navegacion:**
> - [← README](../README.md)
> - [T1: Conceptos](01-conceptos-fundamentales.md)
> - [T2: Criptografia](02-criptografia-fundamentos.md)
> - [T3: Amenazas](03-amenazas-sistemas.md)
> - [T4: Defensa](04-mecanismos-defensa.md)
> - [T5: Gestion](05-gestion-seguridad.md)
> - [T6: Legislacion](06-legislacion-normativa.md)
> - [📖 GLOSARIO](../GLOSARIO.md)

# Chuleta Numerica - Seguridad de la Informacion

> TODOS los datos numericos, fechas, tamanios y tiempos que aparecen en preguntas de examen.

---

## 🔐 Criptografía y Tamaños

### Cifrado Simétrico — Tamaños de Clave y Bloque

| Concepto | Dato | Notas |
|---|---|---|
| **AES — Tamaño de BLOQUE** | **128 bits (16 bytes)** | SIEMPRE 128 bits, independientemente de la clave |
| **AES — Tamaños de CLAVE** | 128, 192 o 256 bits | De ahí AES-128, AES-192, AES-256 |
| **DES — Tamaño de BLOQUE** | 64 bits | Bloque fijo |
| **DES — Tamaño de CLAVE efectiva** | **56 bits** | El resto son bits de paridad |
| **Triple DES (3DES) — Clave efectiva** | 112 o 168 bits | 2 claves (112) o 3 claves (168) |
| **RC4 — Cifrador de flujo** | N/A | Tamaño cifrado = **IDÉNTICO** al original |
| **IDEA** | Bloque 64 bits, clave 128 bits | Cifrador de bloque |
| **RC2** | Bloque 64 bits | Cifrador de bloque |
| **Camellia** | Bloque 128 bits | Cifrador de bloque (alternativa a AES) |

### Cifrado Asimétrico — Tamaños de Clave

| Concepto | Dato | Notas |
|---|---|---|
| **RSA mínimo recomendado** | **2048 bits** | Basado en factorización de números grandes |
| **RSA tamaños típicos** | 1024, 2048, 4096, 8192 bits | 1024 ya no es seguro |
| **Curvas Elípticas (ECC)** | 200–800 bits | Equivalente a RSA de mucho mayor tamaño |
| **Limitación asimétrico** | Datos ≤ tamaño de clave | RSA-2048 solo cifra ~256 bytes directamente |

### Funciones de Resumen (Hash)

| Algoritmo | Tamaño de salida | Estado |
|---|---|---|
| **MD5** | 128 bits (16 bytes) | ❌ ROTO — no usar |
| **SHA-1** | 160 bits (20 bytes) | ❌ ROTO — no usar |
| **SHA-256** | 256 bits (32 bytes) | ✅ Seguro |
| **SHA-512** | 512 bits (64 bytes) | ✅ Seguro |
| **Whirlpool** | 512 bits | ✅ Seguro |
| **SHA-3** | Variable (basado en Keccak) | ✅ Más reciente |

### OpenSSL — Tamaños al Cifrar

| Escenario | Tamaño resultante |
|---|---|
| **AES con contraseña** | `original + 16 bytes (cabecera) + padding hasta múltiplo de 16` |
| **Cabecera OpenSSL** | 16 bytes: 8 `"Salted__"` + 8 salt aleatoria |
| **RC4 (clave + IV)** | **IDÉNTICO** al original |
| **RC4 con contraseña** | `original + 16 bytes (cabecera)` |
| **AES sin contraseña (clave+IV)** | `original + padding hasta múltiplo de 16` |

### Derivación de Claves en OpenSSL

| Concepto | Mecanismo |
|---|---|
| Derivación desde contraseña | Función de **resumen (hash)** iterada (PBKDF2 con SHA-256) |
| NO se usa | Un cifrador (ni bloque, ni flujo, ni asimétrico) |

---

## ⚖️ Legislación y Tiempos

### Plazos Clave

| Concepto | Plazo / Dato |
|---|---|
| **Notificación Brechas de Seguridad (RGPD)** | Máximo **72 horas** a la AEPD |
| **Multas RGPD** | Hasta **20.000.000 €** o **4%** de la facturación global anual (lo que sea MAYOR) |
| **Auditoría ENS Categoría Básica** | **Autoevaluación** cada **2 años** |
| **Auditoría ENS Categoría Media y Alta** | **Auditoría externa** (entidad acreditada ENAC) cada **2 años** |

### Fechas — Normativa Española y Europea

| Norma | Fecha | Título / Descripción |
|---|---|---|
| **LORTAD** | **1992** | Ley Orgánica de Regulación del Tratamiento Automatizado de Datos |
| **LOPD** | **Ley Orgánica 15/1999** (13 diciembre) | Ley Orgánica de Protección de Datos |
| **LSSI-CE** | **Ley 34/2002** (11 julio) | Ley de Servicios de la Sociedad de la Información y Comercio Electrónico |
| **Ley Firma Electrónica** | **Ley 59/2003** (19 diciembre) | Ley de Firma Electrónica |
| **RD 1720/2007** | **21 diciembre** | Reglamento de desarrollo LOPD |
| **Ley Acceso Electrónico** | **Ley 11/2007** (22 junio) | Acceso electrónico de los ciudadanos a los servicios públicos |
| **RD 3/2010 ENS** | **8 enero** | Esquema Nacional de Seguridad |
| **Ley PIC** | **Ley 8/2011** (28 abril) | Protección de Infraestructuras Críticas |
| **Ley General Telecomunicaciones** | **Ley 9/2014** (9 mayo) | Ley General de Telecomunicaciones |
| **RD 951/2015** | **23 octubre** | Modificación del ENS |
| **RGPD** | **Reglamento UE 2016/679** (27 abril 2016) | Reglamento General de Protección de Datos |
| **Directiva NIS** | **(UE) 2016/1148** (6 julio 2016) | Directiva de Seguridad de Redes y Sistemas de Información |
| **LOPDyGDD** | **Ley Orgánica 3/2018** (5 diciembre) | Sustituye a LOPD — adapta RGPD a España |
| **RD-Ley 12/2018** | **7 septiembre** | Trasposición Directiva NIS |

### Leyes Generales de Procedimiento

| Norma | Fecha |
|---|---|
| **Ley 39/2015** | 1 octubre | Procedimiento Administrativo Común |
| **Ley 40/2015** | 1 octubre | Régimen Jurídico del Sector Público |

### Tabla Cronológica de Fechas (Resumen Ordenado)

| Año | Norma | Fecha exacta |
|---|---|---|
| 1992 | LORTAD | — |
| 1999 | LOPD (LO 15/1999) | 13 diciembre |
| 2002 | LSSI-CE (Ley 34/2002) | 11 julio |
| 2003 | Ley Firma Electrónica (Ley 59/2003) | 19 diciembre |
| 2007 | Ley Acceso Electrónico (Ley 11/2007) | 22 junio |
| 2007 | RD 1720/2007 (desarrollo LOPD) | 21 diciembre |
| 2010 | RD 3/2010 (ENS) | 8 enero |
| 2011 | Ley PIC (Ley 8/2011) | 28 abril |
| 2014 | Ley Telecom. (Ley 9/2014) | 9 mayo |
| 2015 | RD 951/2015 (modif. ENS) | 23 octubre |
| 2016 | RGPD (Reglamento UE 2016/679) | 27 abril |
| 2016 | Directiva NIS (UE 2016/1148) | 6 julio |
| 2018 | LOPDyGDD (LO 3/2018) | 5 diciembre |
| 2018 | RD-Ley 12/2018 (NIS) | 7 septiembre |

---

## 🌐 Redes y Protocolos

### WiFi — Evolución

| Protocolo | Año | Seguridad | Clave |
|---|---|---|---|
| **WEP** | 1999 | ❌ ROTO, obsoleto | RC4 |
| **WPA** | 2003 | Mejoras sobre WEP | TKIP + RC4 |
| **WPA2** | 2004 | ✅ Seguro | AES-CCMP |
| **WPA3** | 2018 | ✅ Más reciente | SAE (Simultaneous Authentication of Equals) |

### Ataque WPS

| Concepto | Dato |
|---|---|
| PIN WPS | **8 dígitos** |
| Intentos para romperlo | Solo **~11.000** (por diseño del protocolo) |

### Rangos IP Privadas (RFC 1918)

| Rango CIDR | Desde | Hasta |
|---|---|---|
| **10.0.0.0/8** | 10.0.0.0 | 10.255.255.255 |
| **172.16.0.0/12** | 172.16.0.0 | 172.31.255.255 |
| **192.168.0.0/16** | 192.168.0.0 | 192.168.255.255 |

### Identificación Rápida — ¿Privada o Pública?

| IP | ¿Privada? | Motivo |
|---|---|---|
| 10.1.1.1 | ✅ Sí | Rango 10.0.0.0/8 |
| 172.26.0.1 | ✅ Sí | Rango 172.16.0.0/12 (172.16–172.31) |
| 192.168.1.1 | ✅ Sí | Rango 192.168.0.0/16 |
| 11.1.1.1 | ❌ NO | Fuera de los rangos privados → PÚBLICA |

### Otros

| Concepto | Dato |
|---|---|
| ADSL | Asymmetric Digital Subscriber Line (Asíncrona) |

---

## 📊 Gestión de Seguridad

### ITIL — Números Clave

| Versión | Año | Estructura |
|---|---|---|
| **ITIL V2** | — | **7 libros** |
| **ITIL V3** | 2008 | **5 libros**, **5 etapas** del Ciclo de Vida |
| **ITIL V4** | 2019 | Basado en Industria 4.0 |

### Ciclo de Vida ITIL V3 — 5 Etapas

| # | Etapa |
|---|---|
| 1 | Estrategia del Servicio |
| 2 | Diseño del Servicio |
| 3 | Transición del Servicio |
| 4 | Operación del Servicio |
| 5 | Mejora Continua del Servicio |

### Ciclo PDCA (Deming) — 4 Etapas

| # | Etapa | Inglés |
|---|---|---|
| 1 | Planificar | Plan |
| 2 | Hacer | Do |
| 3 | Revisar / Verificar | Check |
| 4 | Actuar | Act |

### ISO 27001 / 27002

| Concepto | Dato |
|---|---|
| **ISO 27002** | **11 capítulos**, **39 categorías** de seguridad, **133 controles** |
| **ISO 27002 — Certificable** | ❌ NO certificable |
| **ISO 27001** | ✅ Certificable, **5 aspectos fundamentales** en cuerpo principal |

### Tratamiento del Riesgo — 4 Opciones

| # | Opción |
|---|---|
| 1 | **Mitigar** (reducir) |
| 2 | **Asumir** (aceptar) |
| 3 | **Transferir** (ej: seguro) |
| 4 | **Eliminar** (evitar) |

### Tipos de Riesgo

| # | Tipo |
|---|---|
| 1 | Riesgos **Conocidos** |
| 2 | Riesgos **Desconocidos** |

### Metodologías de Análisis de Riesgos

| Metodología | Nº de Fases / Libros |
|---|---|
| **MAGERIT III** | **3 libros**: Método, Catálogo de Elementos, Guías Técnicas |
| **CRAMM** | **3 fases** |
| **EBIOS** | **5 fases** |

### Dimensiones de la Seguridad — 5

| # | Dimensión |
|---|---|
| 1 | **Disponibilidad** |
| 2 | **Integridad** |
| 3 | **Confidencialidad** |
| 4 | **Autenticación** |
| 5 | **No Repudio** |

### Factores de Autenticación — 3

| # | Factor | "Algo que..." |
|---|---|---|
| 1 | **Conocimiento** | ...se SABE (contraseña, PIN) |
| 2 | **Posesión** | ...se TIENE (token, móvil, tarjeta) |
| 3 | **Existencia** | ...se ES (huella, iris, rasgos faciales) |

### SGSI — Niveles de Documentación

| # | Nivel |
|---|---|
| 1 | Políticas |
| 2 | Procedimientos |
| 3 | Instrucciones |
| 4 | Registros |

### Auditoría ENS — CCN-STIC 802

| Concepto | Dato |
|---|---|
| **Tipos de dictamen** | **3 tipos**: Conforme, Conforme con deficiencias, No conforme |
| **Formas de auditoría** | **3**: Alrededor del ordenador, A través del ordenador, Con el ordenador |

### Pentesting — 3 Formas

| # | Forma |
|---|---|
| 1 | **Caja blanca** (white box) — se conoce el sistema |
| 2 | **Caja negra** (black box) — sin información previa |
| 3 | **Caja gris** (grey box) — información parcial |

### Preguntas Clave del Análisis de Seguridad — 4

| # | Pregunta |
|---|---|
| 1 | **Qué** proteger |
| 2 | **Contra quién** |
| 3 | **Cómo** |
| 4 | **Hasta dónde** |

---

## 🔴 Tabla Resumen: "¿Qué número va con qué?"

| Número | ¿Con qué va? | Detalle |
|---|---|---|
| **128** | AES — tamaño de BLOQUE | Siempre 128 bits (16 bytes) |
| **128/192/256** | AES — tamaños de CLAVE | NO confundir con tamaño de bloque |
| **56** | DES — clave efectiva | Bloque de 64 bits pero clave de 56 |
| **112/168** | Triple DES — clave efectiva | 2 o 3 claves DES |
| **16** | Cabecera OpenSSL | 8 "Salted__" + 8 salt |
| **16** | Tamaño bloque AES (bytes) | Múltiplo para padding |
| **160** | SHA-1 | 20 bytes — ROTO |
| **256** | SHA-256 | 32 bytes — Seguro |
| **512** | SHA-512 / Whirlpool | 64 bytes — Seguro |
| **128** | MD5 | 16 bytes — ROTO |
| **2048** | RSA mínimo recomendado | 1024 inseguro, 4096 alta seguridad |
| **72** | Brechas RGPD — horas | Máximo para notificar a AEPD |
| **20M / 4%** | Multas RGPD | Lo que sea MAYOR |
| **2** | Auditoría ENS | Cada 2 años (básica y media/alta) |
| **5** | Dimensiones seguridad | Disponibilidad, Integridad, Confidencialidad, Autenticación, No Repudio |
| **5** | Etapas ITIL V3 | Estrategia, Diseño, Transición, Operación, Mejora Continua |
| **5** | Etapas PDCA | Planificar, Hacer, Revisar, Actuar (4 realmente) |
| **4** | Opciones riesgo | Mitigar, Asumir, Transferir, Eliminar |
| **3** | Factores autenticación | Conocimiento, Posesión, Existencia |
| **3** | Formas pentesting | Caja blanca, negra, gris |
| **3** | Tipos dictamen auditoría | Conforme, Conforme con def., No conforme |
| **3** | Libros MAGERIT III | Método, Catálogo, Guías Técnicas |
| **3** | Fases CRAMM | — |
| **11** | Capítulos ISO 27002 | Con 39 categorías y 133 controles |
| **133** | Controles ISO 27002 | — |
| **7** | Libros ITIL V2 | — |
| **~11.000** | Intentos fuerza bruta WPS | PIN de 8 dígitos |
| **8** | Dígitos PIN WPS | — |
| **200-800** | bits ECC | Equivalente a RSA mucho mayor |

---

## 🔴 Preguntas Trampa Frecuentes

> ⚠️ Números que la gente CONFUNDE en el examen.

| ❌ Confusión común | ✅ Realidad |
|---|---|
| "AES-256 usa bloques de 256 bits" | **FALSO** — AES-256 = clave de 256 bits, pero el **BLOQUE es SIEMPRE 128 bits** (16 bytes) |
| "RC4 añade padding como AES" | **FALSO** — RC4 es cifrador de **FLUJO**: tamaño cifrado = **IDÉNTICO** al original |
| "AES con contraseña solo añade 16 bytes" | **FALSO** — Añade 16 bytes de cabecera **+ padding** hasta múltiplo de 16 bytes |
| "AES con clave+IV solo añade cabecera" | **FALSO** — Con clave+IV NO hay cabecera, pero **sí hay padding** hasta múltiplo de 16 |
| "SHA-1 produce 256 bits" | **FALSO** — SHA-1 produce **160 bits** (20 bytes). SHA-**256** produce 256 bits |
| "MD5 produce 256 bits" | **FALSO** — MD5 produce **128 bits** (16 bytes) |
| "RSA mínimo seguro es 1024 bits" | **FALSO** — El mínimo recomendado actual es **2048 bits**. 1024 ya no es seguro |
| "DES tiene clave de 64 bits" | **FALSO** — DES usa bloque de 64 bits, pero la **clave efectiva es de 56 bits** (8 bits son de paridad) |
| "ITIL V3 tiene 7 libros" | **FALSO** — ITIL **V2** tiene 7 libros. ITIL **V3** tiene **5 libros** y 5 etapas |
| "El ciclo PDCA tiene 5 etapas" | **FALSO** — PDCA tiene **4 etapas** (Plan, Do, Check, Act) |
| "ISO 27002 es certificable" | **FALSO** — Solo **ISO 27001** es certificable. ISO 27002 es una guía de buenas prácticas |
| "MAGERIT tiene 5 fases" | **FALSO** — MAGERIT III tiene **3 libros**. **EBIOS** tiene 5 fases |
| "Las multas RGPD son 20 millones o 2%" | **FALSO** — Son **20 millones € o el 4%** (lo que sea mayor) |
| "172.16.0.0/12 va de 172.16 a 172.32" | **FALSO** — Va de **172.16.0.0 a 172.31.255.255** (32 - 16 = 16 bloques /24) |

---

## 📋 Checklist Mental — Tamaños en Orden

```
MD5     = 128 bits  (16 bytes)  ❌ ROTO
AES-128 = 128 bits  (16 bytes)  clave
AES-192 = 192 bits               clave
SHA-1   = 160 bits  (20 bytes)  ❌ ROTO
AES-256 = 256 bits               clave
SHA-256 = 256 bits  (32 bytes)  ✅
RSA min = 2048 bits               recomendado
SHA-512 = 512 bits  (64 bytes)  ✅
Whirlp. = 512 bits               ✅
```

---

> 📚 **Navegación:** [← README](../README.md) | [📋 Temario](README.md) | [T1](01-conceptos-fundamentales.md) | [T2](02-criptografia-fundamentos.md) | [T3](03-amenazas-sistemas.md) | [T4](04-mecanismos-defensa.md) | [T5](05-gestion-seguridad.md) | [T6](06-legislacion-normativa.md) | [📖 GLOSARIO](../GLOSARIO.md)
