# Procedimiento Oficial para el Escaneo Electrónico Vehicular OBD-II

> **Documento normativo INNV-DT-001**
> **Versión:** 1.0
> **Clasificación:** Procedimiento técnico de aplicación general
> **Audiencia:** Talleres certificados, técnicos automotrices, usuarios calificados

---

## Índice

1. [Objetivo](#1-objetivo)
2. [Alcance](#2-alcance)
3. [Marco normativo y referencias](#3-marco-normativo-y-referencias)
4. [Definiciones y acrónimos](#4-definiciones-y-acrónimos)
5. [Equipo y herramientas requeridas](#5-equipo-y-herramientas-requeridas)
6. [Advertencias de seguridad](#6-advertencias-de-seguridad)
7. [Procedimiento de escaneo paso a paso](#7-procedimiento-de-escaneo-paso-a-paso)
8. [Interpretación inicial de resultados](#8-interpretación-inicial-de-resultados)
9. [Tabla de modos de servicio OBD-II (SAE J1979)](#9-tabla-de-modos-de-servicio-obd-ii-sae-j1979)
10. [Criterios de finalización del diagnóstico](#10-criterios-de-finalización-del-diagnóstico)
11. [Bibliografía técnica](#11-bibliografía-técnica)

---

## 1. Objetivo

Establecer el procedimiento normalizado para la lectura, interpretación y
documentación de datos electrónicos del sistema de diagnóstico a bordo
(OBD-II) en vehículos livianos con motor de combustión interna o híbrido,
fabricados a partir del año modelo en que el estándar OBD-II resultó
obligatorio en su jurisdicción (1996 en EE. UU.; 2001–2006 en Europa según
EOBD; años variables en países de América Latina).

## 2. Alcance

Este procedimiento aplica a:

- Vehículos de pasajeros y comerciales ligeros (≤ 3 856 kg PBV) equipados
  con conector estandarizado **DLC SAE J1962** (16 pines, trapezoidal).
- Sistemas de gestión electrónica del motor (ECM/PCM), transmisión (TCM),
  carrocería (BCM), chasis (ABS, SRS) y red de comunicación (CAN, K-Line,
  J1850).
- Lectura tanto de **DTC genéricos SAE** como de **DTC específicos del
  fabricante (OEM)**, cuando la herramienta lo permita.

Este procedimiento **no cubre**:

- Diagnóstico de vehículos pesados con conector SAE J1939 (9 pines).
- Reprogramación de módulos (flasheo), codificación de inmovilizadores ni
  procedimientos de calibración avanzada, los cuales requieren equipo
  autorizado por el fabricante.

## 3. Marco normativo y referencias

| Norma | Título | Aplicación |
|---|---|---|
| SAE J1962 | Diagnostic Connector | Conector físico DLC de 16 pines |
| SAE J1979 | E/E Diagnostic Test Modes | Modos de servicio (01–0A) |
| SAE J2012 | Diagnostic Trouble Code Definitions | Codificación y descripción de DTC |
| ISO 15031-3 | Diagnostic connector and related electrical circuits | Equivalente internacional de J1962 |
| ISO 15031-5 | Emissions-related diagnostic services | Equivalente internacional de J1979 |
| ISO 15031-6 | Diagnostic trouble code definitions | Equivalente internacional de J2012 |
| ISO 14229 | Unified Diagnostic Services (UDS) | Diagnóstico avanzado sobre CAN |
| ISO 15765-4 | Diagnostics on CAN | Capa de transporte CAN para OBD-II |

## 4. Definiciones y acrónimos

- **DLC** (*Data Link Connector*): conector físico de diagnóstico.
- **DTC** (*Diagnostic Trouble Code*): código alfanumérico de cinco
  caracteres que identifica una falla detectada por la ECU.
- **ECU/ECM/PCM**: unidad de control electrónica del motor / módulo de
  control del tren motriz.
- **MIL** (*Malfunction Indicator Lamp*): testigo "Check Engine" en el
  tablero.
- **PID** (*Parameter Identifier*): identificador de parámetro en vivo
  (ejemplo: RPM, temperatura del refrigerante).
- **Freeze Frame**: captura instantánea de los parámetros del motor en el
  momento exacto en que se almacenó un DTC confirmado.
- **Readiness Monitor**: indicador de estado de los monitores internos
  (catalizador, EVAP, EGR, O₂, etc.).
- **VIN** (*Vehicle Identification Number*): número de chasis de 17
  caracteres conforme a ISO 3779.

## 5. Equipo y herramientas requeridas

### 5.1 Herramientas de escaneo

| Categoría | Ejemplos | Uso recomendado |
|---|---|---|
| Lector OBD-II básico | ELM327 (Bluetooth/Wi-Fi/USB) | Lectura/borrado de DTC genéricos, PID en vivo |
| Escáner intermedio | Autel AL519, Launch CR619, Foxwell NT301 | DTC genéricos + Freeze Frame + Readiness |
| Escáner profesional | Autel MaxiSys, Launch X431, Bosch KTS | DTC OEM, bidireccional, ABS/SRS, codificación |
| Equipo de fabricante | Tech 2 (GM), IDS (Ford), DRB-III (Chrysler), VCDS (VAG), Consult-III (Nissan) | Programación, adaptaciones, inmovilizador |

### 5.2 Herramientas auxiliares

- Multímetro digital con categoría CAT III mínimo 600 V.
- Osciloscopio automotriz de 2 canales (recomendado para señales CAN).
- Linterna LED y juego de pinzas/destornilladores aislados.
- Manual de servicio del fabricante para el modelo y año específicos.

## 6. Advertencias de seguridad

> ⚠️ **ADVERTENCIA — RIESGO ELÉCTRICO**
> Antes de conectar o desconectar el escáner, verifique que el encendido
> esté en posición **OFF**. La conexión bajo carga puede inducir picos de
> tensión en el bus CAN y dañar tanto la herramienta como módulos del
> vehículo.

> 🛑 **ADVERTENCIA CRÍTICA — VEHÍCULOS HÍBRIDOS Y ELÉCTRICOS**
> No manipule cableado naranja (alta tensión, hasta 650 V CC) sin
> certificación específica HV. El procedimiento aquí descrito se limita a
> la red de baja tensión (12 V) y al diagnóstico OBD-II. **Riesgo de
> lesión grave o muerte por contacto eléctrico.**

> 🛑 **ADVERTENCIA CRÍTICA — GASES DE ESCAPE**
> Si el procedimiento requiere motor encendido, opere el vehículo en un
> área ventilada o conecte un extractor de gases. La inhalación de monóxido
> de carbono (CO) es **letal**.

> ⚠️ **ADVERTENCIA — BORRADO DE DTC**
> El borrado prematuro de códigos elimina el Freeze Frame y reinicia los
> monitores de Readiness. No borre códigos antes de documentarlos ni antes
> de una inspección técnica vehicular oficial.

> ▪ **NOTA TÉCNICA**
> Algunos vehículos (en particular europeos y asiáticos posteriores a
> 2008) implementan **Security Access (ISO 14229)**. Funciones bidirec­
> cionales y borrado de ciertos códigos pueden requerir semilla/clave
> proporcionada por el fabricante.

## 7. Procedimiento de escaneo paso a paso

### Etapa A — Preparación del vehículo

**Paso 1.** Estacione el vehículo en superficie plana, aplique el freno
de estacionamiento y coloque la transmisión en **P** (automática) o
**Neutro** (manual).

**Paso 2.** Apague todos los accesorios eléctricos (radio, A/A,
luces, ventilador). Esto reduce el ruido en el bus CAN durante la lectura
de PID.

**Paso 3.** Verifique que la batería esté en buen estado:
- Tensión en reposo ≥ 12.4 V.
- Tensión con motor en marcha entre 13.8 V y 14.6 V.

> ▪ **NOTA TÉCNICA:** Una batería con tensión inferior a 11.5 V puede
> provocar lecturas erráticas o impedir la inicialización de la ECU.

**Paso 4.** Registre los datos básicos del vehículo:
- VIN (placa en el parabrisas o marco de puerta).
- Año modelo, marca y modelo.
- Lectura del odómetro.
- Motivo de consulta del usuario.

### Etapa B — Localización del conector DLC

**Paso 5.** Localice el conector **SAE J1962**. Por norma debe ubicarse
en un radio de 1 m del volante, sin requerir herramientas para acceder.
Posiciones más comunes:

| Posición | Frecuencia | Marcas representativas |
|---|---|---|
| Bajo el tablero, lado del conductor | ~70 % | GM, Ford, Toyota, Honda, Nissan |
| Detrás de tapa removible en consola | ~15 % | BMW, Mercedes-Benz, Audi |
| Bajo cenicero o portavasos | ~10 % | VW, Seat, Skoda |
| Compartimento de fusibles | ~5 % | Algunos modelos europeos |

### Etapa C — Conexión e inicialización

**Paso 6.** Inserte el conector del escáner en el DLC **con el encendido
en OFF**. Verifique alineación correcta de los 16 pines.

**Paso 7.** Gire la llave a posición **KOEO** (*Key On, Engine Off*).
El escáner debe encender al recibir 12 V por el pin 16.

**Paso 8.** En el escáner, seleccione el protocolo de comunicación.
Modernos vehículos lo detectan automáticamente. Protocolos posibles:

| Protocolo | Pines DLC activos | Vehículos típicos |
|---|---|---|
| ISO 9141-2 | 7, 15 | Asiáticos y europeos pre-2004 |
| ISO 14230-4 (KWP2000) | 7, 15 | Europeos 2003–2006 |
| SAE J1850 PWM | 2, 10 | Ford 1996–2003 |
| SAE J1850 VPW | 2 | GM 1996–2003 |
| ISO 15765-4 (CAN) | 6, 14 | Todos los vehículos OBD-II ≥ 2008 |

**Paso 9.** Confirme comunicación: el escáner debe mostrar datos del VIN
o equivalente (CALID/CVN) automáticamente.

### Etapa D — Lectura de DTC

**Paso 10.** Acceda al **Modo 03** (lectura de DTC confirmados). Anote
**cada código** con su descripción literal. Formato esperado: una letra
+ cuatro dígitos (ejemplo: `P0301`).

**Paso 11.** Acceda al **Modo 07** (DTC pendientes). Estos códigos
representan fallas detectadas en un solo ciclo de manejo y aún no han
encendido la MIL.

**Paso 12.** Acceda al **Modo 0A** (DTC permanentes, obligatorio en
vehículos ≥ 2010). Estos códigos solo se borran al cumplirse las
condiciones de auto-validación; no pueden borrarse manualmente.

**Paso 13.** Capture el **Freeze Frame** (Modo 02) asociado al primer
DTC confirmado. Registre como mínimo:
- RPM del motor.
- Velocidad del vehículo.
- Carga calculada (%).
- Temperatura del refrigerante (ECT).
- Presión del múltiple de admisión (MAP) o flujo MAF.
- Ajuste de combustible a corto y largo plazo (STFT/LTFT).

### Etapa E — Lectura de datos en vivo (PID)

**Paso 14.** Active el **Modo 01** y monitoree los siguientes PID
mínimos durante al menos 60 segundos en ralentí:

| PID | Descripción | Rango esperado en ralentí |
|---|---|---|
| 0x05 | Temperatura del refrigerante | 85–105 °C (motor caliente) |
| 0x0C | RPM del motor | 650–900 rpm |
| 0x0D | Velocidad del vehículo | 0 km/h |
| 0x0F | Temperatura del aire de admisión | Tamb +5 a +15 °C |
| 0x10 | Flujo de masa de aire (MAF) | 2–7 g/s (motor 2.0 L) |
| 0x11 | Posición del acelerador (TPS) | 12–18 % |
| 0x06 | Ajuste de combustible corto plazo | ±10 % |
| 0x07 | Ajuste de combustible largo plazo | ±10 % |
| 0x14–0x1B | Tensiones de sensores O₂ | 0.1–0.9 V oscilante |

> ▪ **NOTA TÉCNICA:** Valores de LTFT superiores a +10 % indican mezcla
> pobre persistente; valores inferiores a −10 % indican mezcla rica
> persistente. Use estos datos junto con los DTC para confirmar la
> hipótesis de falla.

### Etapa F — Verificación de monitores de Readiness

**Paso 15.** Acceda al **Modo 01 PID 0x01**. Verifique el estado de los
ocho monitores estandarizados:

1. Misfire (fallos de encendido)
2. Sistema de combustible
3. Componentes integrales (CCM)
4. Catalizador
5. Catalizador calentado
6. Sistema EVAP
7. Sistema de aire secundario
8. Sensores O₂ y calefactores
9. EGR / VVT

> ⚠️ **ADVERTENCIA:** Un vehículo con monitores incompletos
> ("Not Ready") generalmente **no aprueba la inspección técnica de
> emisiones**, incluso si no presenta DTC.

### Etapa G — Documentación y diagnóstico

**Paso 16.** Genere un reporte que incluya:
- Datos de identificación del vehículo (VIN, marca, modelo, año, km).
- Listado completo de DTC (confirmados, pendientes, permanentes).
- Freeze Frame de cada DTC.
- Estado de monitores de Readiness.
- Hallazgos en datos en vivo relevantes.
- Hipótesis diagnóstica priorizada.

**Paso 17.** Antes de borrar códigos, valide la hipótesis diagnóstica
contra el manual de servicio del fabricante y los procedimientos
descritos en el directorio `fixes/` de este repositorio.

**Paso 18.** Realice las pruebas físicas pertinentes (medición de
resistencias, presiones, señales con osciloscopio) según el DTC.

**Paso 19.** Ejecute la reparación y borre los DTC mediante el
**Modo 04**. Realice un ciclo de manejo según el patrón de manejo OBD-II
(*OBD Drive Cycle*) para validar que la falla no reaparece y que los
monitores se completan.

## 8. Interpretación inicial de resultados

La estructura de un DTC SAE J2012 es:

```
P 0 4 2 0
│ │ │ └─┴── Identificador específico de la falla
│ │ └────── Subsistema (combustible/aire, encendido, emisiones, etc.)
│ └──────── 0 = genérico SAE | 1 = específico OEM
└────────── Letra de sistema:
            P = Powertrain (motor/transmisión)
            B = Body (carrocería)
            C = Chassis (chasis)
            U = Network (comunicación CAN)
```

Para la interpretación detallada consulte:

- `docs/codigos-P.md` — Códigos Powertrain.
- `docs/codigos-B.md` — Códigos Body.
- `docs/codigos-C.md` — Códigos Chassis.
- `docs/codigos-U.md` — Códigos Network/CAN.

## 9. Tabla de modos de servicio OBD-II (SAE J1979)

| Modo | Función | Aplicación clínica |
|---|---|---|
| `0x01` | Datos en vivo (PID actuales) | Diagnóstico funcional |
| `0x02` | Freeze Frame | Contexto del DTC |
| `0x03` | DTC confirmados | Diagnóstico primario |
| `0x04` | Borrado de DTC y Freeze Frame | Posterior a reparación |
| `0x05` | Resultados de prueba de sensores O₂ (no CAN) | Diagnóstico de emisiones |
| `0x06` | Resultados de monitores no continuos | Catalizador, EVAP, EGR |
| `0x07` | DTC pendientes | Detección temprana |
| `0x08` | Control bidireccional (limitado) | Pruebas de actuadores |
| `0x09` | Información del vehículo (VIN, CALID, CVN) | Identificación y verificación de software |
| `0x0A` | DTC permanentes | Verificación post-reparación obligatoria |

## 10. Criterios de finalización del diagnóstico

Se considera completo el procedimiento cuando se cumplen **todas** las
siguientes condiciones:

1. ✅ Todos los DTC confirmados, pendientes y permanentes han sido
   documentados.
2. ✅ Los Freeze Frame asociados han sido capturados y archivados.
3. ✅ Los datos en vivo se han registrado en al menos un ciclo
   completo (KOEO + KOER + ralentí + carga).
4. ✅ El estado de los monitores de Readiness ha sido verificado.
5. ✅ Existe una hipótesis diagnóstica documentada o se ha
   referenciado el documento de reparación correspondiente
   (`fixes/<código>.md`).

## 11. Bibliografía técnica

1. SAE International. *J1962: Diagnostic Connector Equivalent to
   ISO/DIS 15031-3*. Warrendale, PA, 2016.
2. SAE International. *J1979: E/E Diagnostic Test Modes*. Warrendale,
   PA, 2017.
3. SAE International. *J2012: Diagnostic Trouble Code Definitions*.
   Warrendale, PA, 2016.
4. ISO. *ISO 15031-5: Road vehicles — Communication between vehicle
   and external equipment for emissions-related diagnostics — Part 5:
   Emissions-related diagnostic services*. Geneva, 2015.
5. ISO. *ISO 15765-4: Road vehicles — Diagnostic communication over
   Controller Area Network (DoCAN) — Part 4: Requirements for
   emissions-related systems*. Geneva, 2021.
6. ISO. *ISO 14229-1: Road vehicles — Unified diagnostic services
   (UDS) — Part 1: Application layer*. Geneva, 2020.
7. U.S. Environmental Protection Agency. *On-Board Diagnostics
   (OBD-II) Regulations Reference Guide*. Washington D.C., 2020.
8. CARB (California Air Resources Board). *OBD II Regulation, Title
   13, California Code of Regulations, Section 1968.2*. Sacramento,
   2022.

---

> **Documento elaborado por:** Instituto Nacional de Normalización
> Vehicular (INNV) — Dirección de Documentación Técnica.
> **Próxima revisión obligatoria:** 24 meses a partir de la fecha de
> publicación.
