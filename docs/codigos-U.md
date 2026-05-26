# Catálogo Técnico de Códigos DTC — Categoría U (Network / CAN Bus)

> **Documento normativo INNV-DT-005**
> **Versión:** 1.0
> **Estándar de referencia:** SAE J2012 / ISO 15031-6 / ISO 11898 / ISO 15765-4
> **Clasificación:** Catálogo técnico de aplicación general
> **Audiencia:** Talleres certificados, técnicos automotrices, peritos de redes vehiculares

---

## Índice

1. [Objetivo](#1-objetivo)
2. [Alcance](#2-alcance)
3. [Estructura del código U](#3-estructura-del-código-u)
4. [Topologías de red más frecuentes](#4-topologías-de-red-más-frecuentes)
5. [Subsistemas cubiertos](#5-subsistemas-cubiertos)
6. [Tabla maestra de los 50 códigos U más frecuentes](#6-tabla-maestra-de-los-50-códigos-u-más-frecuentes)
7. [Variaciones por fabricante (OEM)](#7-variaciones-por-fabricante-oem)
8. [Procedimiento de diagnóstico de red CAN](#8-procedimiento-de-diagnóstico-de-red-can)
9. [Bibliografía técnica](#9-bibliografía-técnica)

---

## 1. Objetivo

Proveer un catálogo técnico de referencia rápida con los **50 códigos
DTC de la categoría Network (letra U)** más relevantes para el
diagnóstico de las redes de comunicación vehicular: **CAN** (alta,
media y baja velocidad), **CAN FD**, **LIN**, **FlexRay** y, en
plataformas modernas, **Automotive Ethernet**.

## 2. Alcance

- Aplica al rango definido por SAE como genérico: **U0xxx** y **U3xxx**.
- Incluye una selección representativa de códigos **U1xxx/U2xxx**
  ampliamente documentados en bases de datos OEM, marcados
  explícitamente como **específicos del fabricante**.
- La columna *"Solución básica"* es **orientativa**.

> ⚠️ **ADVERTENCIA — IMPACTO TRANSVERSAL**
> Un fallo en la red de comunicación rara vez es local: un único
> cortocircuito o un módulo "ruidoso" puede generar **decenas de
> códigos U** simultáneos en múltiples ECU. Antes de reemplazar
> componentes:
>
> 1. Identifique el **módulo "fuente"** (el que sale primero del bus
>    o el más cercano al fallo eléctrico).
> 2. Recuerde que un código `U0100` *en el TCM* no significa que la
>    ECM esté dañada: significa que el TCM dejó de "oír" a la ECM.
> 3. Diagnostique siempre **del bus físico hacia los módulos**, nunca
>    al revés.

## 3. Estructura del código U

```
U 0 1 0 0
│ │ │ └─┴── Identificador específico (módulo/función afectada)
│ │ └────── Subsistema (ver tabla 5.1)
│ └──────── 0 = genérico SAE | 1 = OEM | 2 = OEM | 3 = SAE reservado
└────────── U = Network (red de comunicación)
```

## 4. Topologías de red más frecuentes

| Red | Velocidad típica | Pines DLC | Aplicación |
|---|---|---|---|
| HS-CAN (High-Speed CAN) | 500 kbit/s (hasta 1 Mbit/s) | 6 (CAN-H), 14 (CAN-L) | Powertrain, ABS, SRS, gateway |
| MS-CAN (Medium-Speed CAN) | 125–250 kbit/s | Variable según OEM | Confort, climatización, instrumentación |
| LS-CAN (Low-Speed CAN, "Single-Wire") | 33.33 kbit/s | Variable | Body control, accesorios no críticos |
| CAN FD (CAN with Flexible Data-rate) | Hasta 5 Mbit/s | Variable | Vehículos premium ≥ 2018 |
| LIN (Local Interconnect Network) | 19.2 kbit/s | Maestro/esclavo en arnés local | Sensores y actuadores simples |
| FlexRay | 10 Mbit/s | Cableado dedicado | X-by-wire, suspensión activa premium |
| Automotive Ethernet (100BASE-T1) | 100 Mbit/s a 1 Gbit/s | Par trenzado dedicado | ADAS, cámaras, infotainment moderno |

> ▪ **NOTA TÉCNICA — RESISTENCIAS TERMINALES**
> En un bus HS-CAN saludable, la medición de resistencia entre
> CAN-H (pin 6) y CAN-L (pin 14) **con la batería desconectada** debe
> arrojar aproximadamente **60 Ω** (paralelo de dos resistencias
> terminales de 120 Ω). Una lectura de **120 Ω** indica una
> resistencia faltante; **40 Ω** o menos indica un cortocircuito en
> el bus o una tercera resistencia mal instalada.

## 5. Subsistemas cubiertos

### Tabla 5.1 — Asignación funcional aproximada en U0xxx

| Rango | Subsistema |
|---|---|
| U0001–U0099 | Buses de comunicación (CAN HS, MS, LS) — capa física |
| U0100–U0299 | *Lost Communication With...* — pérdida de comunicación con un módulo específico |
| U0300–U0399 | Incompatibilidad de software entre módulos |
| U0400–U0599 | *Invalid Data Received From...* — datos no válidos desde un módulo |
| U0600–U0799 | Otros — diagnóstico de gateway y enrutamiento |

## 6. Tabla maestra de los 50 códigos U más frecuentes

> **Leyenda de origen:**
> 🅢 = Genérico SAE J2012 (U0xxx / U3xxx) · 🅞 = Específico OEM (U1xxx / U2xxx)

| # | Código | Origen | Descripción | Causa probable | Solución básica |
|---|---|---|---|---|---|
| 1 | **U0001** | 🅢 | Bus de comunicación CAN de alta velocidad | Cableado CAN cortado/cortocircuitado, módulo "ruidoso", resistencia terminal faltante | Medir 60 Ω entre CAN-H y CAN-L con batería desconectada |
| 2 | **U0002** | 🅢 | Bus HS-CAN — desempeño | Tasa de errores elevada, EMI, módulo intermitente | Capturar tráfico con osciloscopio (forma de onda 0–5 V) |
| 3 | **U0003** | 🅢 | Bus HS-CAN abierto | Cable CAN-H o CAN-L cortado | Continuidad pin a pin desde DLC a cada módulo |
| 4 | **U0004** | 🅢 | Bus HS-CAN (+) baja tensión | Cortocircuito CAN-H a masa | Inspección física del arnés; aislar tramo |
| 5 | **U0005** | 🅢 | Bus HS-CAN (+) alta tensión | Cortocircuito CAN-H a 12 V | Inspeccionar daño en arnés contra estructura/calor |
| 6 | **U0007** | 🅢 | Bus HS-CAN (-) baja tensión | Cortocircuito CAN-L a masa | Idem U0004 lado CAN-L |
| 7 | **U0010** | 🅢 | Bus de comunicación CAN de velocidad media | Cableado MS-CAN, módulo de confort | Verificar topología MS-CAN del modelo |
| 8 | **U0019** | 🅢 | Bus de comunicación CAN de baja velocidad | Cableado LS-CAN (single-wire) | Verificar masa de referencia del LS-CAN |
| 9 | **U0028** | 🅢 | Bus de comunicación del vehículo "A" | Bus designado "A" en topología multi-bus | Identificar bus "A" en diagrama OEM |
| 10 | **U0073** | 🅢 | Bus de comunicación A del módulo de control — apagado (*Bus Off*) | Módulo en estado *Bus Off* por exceso de errores TX | Identificar módulo fuente; revisar resistencias terminales |
| 11 | **U0074** | 🅢 | Bus de comunicación B del módulo de control — apagado | Idem U0073 sobre bus secundario | Idem U0073 |
| 12 | **U0100** | 🅢 | Pérdida de comunicación con ECM/PCM "A" | ECM sin alimentación, fusible, falla de la ECM, cable CAN al ECM | Verificar 12 V y masa del ECM; medir CAN en conector de la ECM |
| 13 | **U0101** | 🅢 | Pérdida de comunicación con TCM | TCM sin alimentación, conexión CAN | Verificar arnés del TCM; alimentación y masa |
| 14 | **U0102** | 🅢 | Pérdida de comunicación con módulo de transferencia (4WD) | Transfer case control module | Verificar alimentación del módulo 4WD |
| 15 | **U0103** | 🅢 | Pérdida de comunicación con módulo de cambio de marchas | Gear shift module (en transmisiones shift-by-wire) | Verificar conector del selector electrónico |
| 16 | **U0104** | 🅢 | Pérdida de comunicación con módulo de control de crucero | Cruise control module | Si está integrado a la ECM, ver U0100 |
| 17 | **U0105** | 🅢 | Pérdida de comunicación con módulo del inyector | Driver de inyectores externo (algunos diésel) | Verificar arnés y alimentación del módulo |
| 18 | **U0109** | 🅢 | Pérdida de comunicación con módulo de la bomba de combustible | Fuel pump driver module | Verificar arnés bajo el vehículo, masa del FPDM |
| 19 | **U0121** | 🅢 | Pérdida de comunicación con módulo ABS | EBCM sin comunicación CAN | Ver `docs/codigos-C.md`; verificar alimentación del EBCM |
| 20 | **U0122** | 🅢 | Pérdida de comunicación con módulo de dinámica vehicular | Vehicle dynamics control module (ESC/yaw) | Verificar conector del módulo ESC |
| 21 | **U0125** | 🅢 | Pérdida de comunicación con módulo de aceleración multiaxial | Sensor de aceleración multi-eje | Verificar conector y alimentación |
| 22 | **U0126** | 🅢 | Pérdida de comunicación con módulo del sensor de ángulo de dirección | Sensor SAS | Verificar conector del SAS bajo volante |
| 23 | **U0140** | 🅢 | Pérdida de comunicación con módulo BCM | BCM sin alimentación o sin CAN | Verificar fusibles y alimentación del BCM |
| 24 | **U0141** | 🅢 | Pérdida de comunicación con BCM "A" | Variante OEM del U0140 cuando hay múltiples BCM | Idem U0140 |
| 25 | **U0146** | 🅢 | Pérdida de comunicación con gateway "A" | Módulo gateway central | Crítico — el gateway es el corazón de la red multi-bus |
| 26 | **U0151** | 🅢 | Pérdida de comunicación con módulo SRS | SDM sin comunicación | Ver `docs/codigos-B.md`; verificar SDM |
| 27 | **U0155** | 🅢 | Pérdida de comunicación con cluster de instrumentos | Cluster sin alimentación o CAN | Verificar fusibles del IPC |
| 28 | **U0159** | 🅢 | Pérdida de comunicación con módulo de asistencia de estacionamiento | Park Assist | Verificar arnés en parachoques |
| 29 | **U0164** | 🅢 | Pérdida de comunicación con módulo HVAC | Control de climatización | Verificar alimentación del HVAC |
| 30 | **U0167** | 🅢 | Pérdida de comunicación con módulo inmovilizador | Antena del inmovilizador, transponder | Reprogramar llave si aplica |
| 31 | **U0184** | 🅢 | Pérdida de comunicación con radio | Radio/cabezal de infotainment | Verificar alimentación del cabezal |
| 32 | **U0186** | 🅢 | Pérdida de comunicación con amplificador de audio | Amplificador externo | Verificar fusible del amp |
| 33 | **U0194** | 🅢 | Pérdida de comunicación con computadora personal/cabezal | Cabezal de infotainment | Reset del cabezal |
| 34 | **U0197** | 🅢 | Pérdida de comunicación con módulo de telefonía | Bluetooth/módulo de telefonía | Verificar fusible y antena |
| 35 | **U0199** | 🅢 | Pérdida de comunicación con módulo de control de puerta "A" | Door control module conductor | Verificar conector en parante de puerta |
| 36 | **U0212** | 🅢 | Pérdida de comunicación con módulo de columna de dirección | SCCM (steering column control module) | Verificar conector bajo columna |
| 37 | **U0214** | 🅢 | Pérdida de comunicación con accionamiento remoto (RKE) | Receptor de llave remota | Verificar antena del receptor |
| 38 | **U0235** | 🅢 | Pérdida de comunicación con sensor frontal de crucero adaptativo | Radar/sensor ACC | Verificar alimentación del radar y limpieza del emblema |
| 39 | **U0244** | 🅢 | Pérdida de comunicación con módulo de techo solar | Sunroof control module | Verificar conector en techo |
| 40 | **U0252** | 🅢 | Pérdida de comunicación con módulo de nivelación de faros | Headlamp leveling module | Verificar conector |
| 41 | **U0300** | 🅢 | Incompatibilidad de software interno entre módulos | Versiones de firmware no coherentes tras reflasheo parcial | Reflasheo completo a versiones compatibles |
| 42 | **U0301** | 🅢 | Incompatibilidad de software con ECM/PCM "A" | Idem U0300, pareja ECM/otro módulo | Reflasheo coherente |
| 43 | **U0401** | 🅢 | Datos no válidos recibidos desde ECM/PCM "A" | El ECM envía datos fuera de rango por sensor desviado | Diagnosticar primero códigos P |
| 44 | **U0402** | 🅢 | Datos no válidos recibidos desde TCM | TCM envía datos fuera de rango | Diagnosticar TCM (ver U0101 y P0700) |
| 45 | **U0415** | 🅢 | Datos no válidos recibidos desde módulo de control de velocidad | Cruise control envía datos inconsistentes | Verificar sensores de pedal y velocidad |
| 46 | **U0416** | 🅢 | Datos no válidos recibidos desde módulo de dinámica vehicular | ESC/yaw envía datos fuera de rango | Recalibrar yaw/SAS; ver `docs/codigos-C.md` |
| 47 | **U0422** | 🅢 | Datos no válidos recibidos desde BCM | BCM con sensor o entrada fallida | Diagnosticar entradas del BCM |
| 48 | **U0428** | 🅢 | Datos no válidos recibidos desde sensor de ángulo de dirección | SAS sin recalibrar tras alineación o reemplazo | Recalibrar SAS |
| 49 | **U1064** | 🅞 | Pérdida de comunicación BCM (Ford común) | Variante Ford de U0140 | Aplicar procedimiento de U0140 |
| 50 | **U2008** | 🅞 | Información del módulo de audio no válida (GM) | Cabezal/amp envía datos fuera de rango | Reset del cabezal; reflasheo si persiste |

## 7. Variaciones por fabricante (OEM)

> ▪ **NOTA TÉCNICA — INTERPRETACIÓN OEM**
>
> El rango **U1xxx/U2xxx** está reservado a definiciones específicas
> del fabricante. Los códigos U-genéricos (U0xxx) están en general
> bien estandarizados, pero la **topología física** de la red varía
> ampliamente:
>
> - **Ford / Lincoln:** uso clásico de HS-CAN + MS-CAN; algunos
>   modelos modernos incorporan **Ethernet** para ADAS. Diagnóstico
>   con FDRS.
> - **General Motors:** GMLAN HS (500 kbit/s), GMLAN MS (95 kbit/s)
>   y SW-LAN (33.33 kbit/s). Diagnóstico con GDS2/Tech 2.
> - **Stellantis:** múltiples buses CAN-C (alta) y CAN-IHS
>   (interior); diagnóstico con wiTECH.
> - **Toyota / Lexus:** uso de gateway central; diagnóstico con
>   Techstream. Es habitual que reflasheos parciales generen U0300.
> - **Honda / Acura:** F-CAN y B-CAN. Diagnóstico con HDS.
> - **Nissan / Infiniti:** CAN-C y CAN-B. Diagnóstico con CONSULT-III.
> - **Hyundai / Kia:** CAN principal y CAN de carrocería. GDS.
> - **Grupo VAG:** topología compleja con gateway, MOST (audio),
>   FlexRay en modelos premium y Ethernet en plataformas MEB y MQB
>   modernas. Diagnóstico con VCDS/ODIS.
> - **BMW / MINI:** PT-CAN, K-CAN, FlexRay y ahora Ethernet en
>   plataformas G/I. ISTA es obligatoria.
> - **Mercedes-Benz:** CAN-C, CAN-B, CAN-D, MOST, FlexRay, Ethernet.
>   XENTRY para diagnóstico.

## 8. Procedimiento de diagnóstico de red CAN

### Paso 1 — Inventario de DTC

Lea **todos los módulos** del vehículo (no solo la ECM). Una sola
falla física en el bus puede aparecer reportada por 5–15 módulos
simultáneamente.

### Paso 2 — Identificación del módulo fuente

Aplique la regla de inferencia inversa:

- Si **todos** los módulos reportan U0100 (lost comm with ECM),
  probablemente la **ECM** es el módulo afectado físicamente.
- Si **solo un módulo** reporta U0xxx contra otro específico, el
  problema está en el cableado entre ambos o en el módulo
  reportante.

### Paso 3 — Verificación física del bus (HS-CAN)

> ⚠️ **ADVERTENCIA — RIESGO ELÉCTRICO**
> Las mediciones de tensión deben hacerse con encendido, pero la
> medición de resistencia **siempre con batería desconectada** para
> no dañar el multímetro ni los módulos.

| Medición | Procedimiento | Valor esperado |
|---|---|---|
| Resistencia de bus | Multímetro entre pin 6 y pin 14 del DLC, batería desconectada | ≈ 60 Ω |
| Tensión CAN-H (reposo) | Pin 6 del DLC vs. masa, KOEO | ≈ 2.5 V |
| Tensión CAN-L (reposo) | Pin 14 del DLC vs. masa, KOEO | ≈ 2.5 V |
| Diferencial CAN-H − CAN-L (reposo) | — | 0 V |
| Diferencial CAN-H − CAN-L (transmisión bit dominante) | Con osciloscopio | 2 V |

### Paso 4 — Aislamiento del módulo conflictivo

Si la resistencia es ≈ 60 Ω y aún hay códigos U:

1. Desconecte un módulo a la vez (empezando por los menos críticos:
   radio, HVAC, módulos de confort).
2. Tras cada desconexión, lea el bus y verifique si los códigos U
   desaparecen.
3. El módulo cuya desconexión "limpia" el bus es el **módulo
   ruidoso**.

### Paso 5 — Inspección de gateway y resistencias terminales

En topologías multi-bus, el **módulo gateway** es el punto único de
falla. Verifique:

- Alimentación principal del gateway.
- Estado de las resistencias terminales (típicamente integradas en
  ECM y en uno de los módulos del extremo del bus).

### Paso 6 — Validación post-reparación

Después de reparar:

1. Borre todos los DTC de todos los módulos (no solo de la ECM).
2. Apague el vehículo y espere 5 minutos para que todos los módulos
   entren en modo *sleep*.
3. Encienda y verifique en al menos un ciclo KOEO + KOER + 5 minutos
   de marcha.
4. Confirme que el **Modo `0x0A`** (DTC permanentes) no contiene
   códigos U residuales.

> ⚠️ **ADVERTENCIA — REPARACIONES NO AUTORIZADAS PARA USUARIO GENERAL**
> Los siguientes procedimientos requieren equipo de taller
> especializado:
>
> - Reflasheo de módulos para resolver U0300 / U0301.
> - Reemplazo y configuración del módulo gateway.
> - Diagnóstico con osciloscopio automotriz multicanal.
> - Reparación de tramos críticos del arnés CAN bajo el vehículo o
>   detrás del tablero.
> - Diagnóstico de buses FlexRay y Ethernet, que requieren
>   herramientas de captura específicas (CANoe, Vehicle Spy, etc.).

## 9. Bibliografía técnica

1. SAE International. *J2012: Diagnostic Trouble Code Definitions*.
   Warrendale, PA, 2016.
2. ISO. *ISO 15031-6: Road vehicles — Communication between vehicle
   and external equipment for emissions-related diagnostics — Part 6:
   Diagnostic trouble code definitions*. Geneva, 2015.
3. ISO. *ISO 11898-1: Road vehicles — Controller area network (CAN) —
   Part 1: Data link layer and physical signalling*. Geneva, 2015.
4. ISO. *ISO 11898-2: Road vehicles — Controller area network (CAN) —
   Part 2: High-speed medium access unit*. Geneva, 2016.
5. ISO. *ISO 15765-2: Road vehicles — Diagnostic communication over
   Controller Area Network (DoCAN) — Part 2: Transport protocol and
   network layer services*. Geneva, 2016.
6. ISO. *ISO 17987 (series): Road vehicles — Local Interconnect
   Network (LIN)*. Geneva, 2016.
7. ISO. *ISO 17458 (series): Road vehicles — FlexRay communications
   system*. Geneva, 2013.
8. IEEE. *IEEE 802.3bw — 100BASE-T1 Automotive Ethernet*. New York,
   2015.
9. SAE International. *J1939 (series): Serial Control and
   Communications Heavy Duty Vehicle Network*. Warrendale, PA. (No
   aplica a vehículos OBD-II ligeros; referencia para distinción).
10. Bosch GmbH. *CAN Specification 2.0*. Stuttgart, 1991 (vigente).

---

> **Documento elaborado por:** Instituto Nacional de Normalización
> Vehicular (INNV) — Dirección de Documentación Técnica.
> **Próxima revisión obligatoria:** 24 meses a partir de la fecha de
> publicación.
