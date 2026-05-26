# Glosario Técnico Vehicular OBD-II

> **Documento normativo INNV-DT-027**
> **Versión:** 1.0
> **Estándar de referencia:** SAE J2012 / ISO 15031-6 / ISO 15765-4
> **Clasificación:** Glosario técnico de aplicación general
> **Audiencia:** Talleres certificados, técnicos automotrices,
> peritos, autoridades de tránsito, estudiantes

---

## Índice

1. [Objetivo](#1-objetivo)
2. [Alcance](#2-alcance)
3. [Convenciones](#3-convenciones)
4. [Acrónimos por categoría](#4-acrónimos-por-categoría)
   - [4.1 Módulos electrónicos de control](#41-módulos-electrónicos-de-control)
   - [4.2 OBD-II y diagnóstico](#42-obd-ii-y-diagnóstico)
   - [4.3 Sensores y actuadores del motor](#43-sensores-y-actuadores-del-motor)
   - [4.4 Sistema de frenos y chasis](#44-sistema-de-frenos-y-chasis)
   - [4.5 Sistemas SRS y sujeción](#45-sistemas-srs-y-sujeción)
   - [4.6 Redes de comunicación vehicular](#46-redes-de-comunicación-vehicular)
   - [4.7 Emisiones y control auxiliar](#47-emisiones-y-control-auxiliar)
   - [4.8 Estándares y entidades](#48-estándares-y-entidades)
5. [Términos clave (orden alfabético)](#5-términos-clave-orden-alfabético)
6. [Equivalencias inglés ↔ español](#6-equivalencias-inglés--español)
7. [Códigos de modos OBD-II (resumen)](#7-códigos-de-modos-obd-ii-resumen)
8. [Bibliografía técnica](#8-bibliografía-técnica)

---

## 1. Objetivo

Proveer un glosario técnico **único y consolidado** que sirva como
referencia transversal para todos los documentos INNV publicados en
este repositorio. Define con precisión los acrónimos, términos
técnicos y equivalencias inglés-español usados en la guía.

## 2. Alcance

- Cubre vocabulario de **OBD-II ligero** (≤ 3 856 kg PBV).
- Incluye terminología de motor de combustión interna (gasolina y
  diésel), transmisión automática, frenos, SRS, redes
  vehiculares y emisiones.
- **No cubre** terminología específica de vehículos comerciales
  pesados SAE J1939, motocicletas ni aeronáutica.

## 3. Convenciones

- **Ortografía técnica:** los acrónimos en mayúsculas se conservan
  como en SAE/ISO. Ejemplo: `ECM`, no `Ecm`.
- **Género gramatical:** los acrónimos de módulos electrónicos se
  tratan como **masculinos** ("el ECM", "el TCM", "el BCM"), por
  consistencia con la palabra subyacente *módulo*.
- **Idioma original:** se conserva el término inglés cuando es la
  forma normativa SAE; se acompaña de traducción técnica al
  español.

## 4. Acrónimos por categoría

### 4.1 Módulos electrónicos de control

| Acrónimo | Significado en inglés | Traducción técnica |
|---|---|---|
| **ABS** | *Anti-lock Braking System* | Sistema antibloqueo de frenos |
| **BCM** | *Body Control Module* | Módulo de control de carrocería |
| **EBCM** | *Electronic Brake Control Module* | Módulo electrónico de control de frenos |
| **ECM** | *Engine Control Module* | Módulo de control del motor |
| **ECU** | *Electronic Control Unit* | Unidad electrónica de control (genérico) |
| **HVAC** | *Heating, Ventilation, Air Conditioning* | Climatización y ventilación |
| **IPC** | *Instrument Panel Cluster* | Cluster del panel de instrumentos |
| **PCM** | *Powertrain Control Module* | Módulo de control del tren motriz (ECM + TCM combinados) |
| **PIM** | *Power Inverter Module* | Inversor de potencia (vehículos híbridos/eléctricos) |
| **SCCM** | *Steering Column Control Module* | Módulo de control de la columna de dirección |
| **SDM** | *Sensing and Diagnostic Module* | Módulo SRS / sistema de airbag |
| **TCM** | *Transmission Control Module* | Módulo de control de la transmisión |

### 4.2 OBD-II y diagnóstico

| Acrónimo | Significado en inglés | Traducción técnica |
|---|---|---|
| **CALID** | *Calibration Identifier* | Identificador de calibración del software |
| **CVN** | *Calibration Verification Number* | Número de verificación de calibración (hash) |
| **DLC** | *Data Link Connector* | Conector físico de diagnóstico (16 pines, SAE J1962) |
| **DTC** | *Diagnostic Trouble Code* | Código de avería de diagnóstico |
| **EOBD** | *European On-Board Diagnostics* | OBD europeo (≈ equivalente OBD-II) |
| **I/M** | *Inspection / Maintenance* | Inspección y mantenimiento (programa de emisiones) |
| **KOEO** | *Key On, Engine Off* | Llave en ON, motor apagado |
| **KOER** | *Key On, Engine Running* | Llave en ON, motor en marcha |
| **MIL** | *Malfunction Indicator Lamp* | Testigo de fallo del motor ("Check Engine") |
| **OBD** | *On-Board Diagnostics* | Diagnóstico a bordo |
| **PID** | *Parameter Identifier* | Identificador de parámetro en vivo |
| **VIN** | *Vehicle Identification Number* | Número de chasis (17 caracteres, ISO 3779) |

### 4.3 Sensores y actuadores del motor

| Acrónimo | Significado en inglés | Traducción técnica |
|---|---|---|
| **CKP** | *Crankshaft Position Sensor* | Sensor de posición del cigüeñal |
| **CMP** | *Camshaft Position Sensor* | Sensor de posición del árbol de levas |
| **COP** | *Coil-On-Plug* | Bobina sobre bujía (encendido individual) |
| **ECT** | *Engine Coolant Temperature* | Temperatura del refrigerante del motor |
| **EVAP** | *Evaporative Emission Control* | Control de emisiones evaporativas |
| **FPDM** | *Fuel Pump Driver Module* | Módulo controlador de bomba de combustible |
| **FTP** | *Fuel Tank Pressure (sensor)* | Sensor de presión del tanque de combustible |
| **GDI** | *Gasoline Direct Injection* | Inyección directa de gasolina |
| **HO2S** | *Heated Oxygen Sensor* | Sensor de oxígeno con calefactor |
| **IAC** | *Idle Air Control* | Control de aire de ralentí |
| **IAT** | *Intake Air Temperature* | Temperatura del aire de admisión |
| **LTFT** | *Long-Term Fuel Trim* | Ajuste de combustible a largo plazo |
| **MAF** | *Mass Air Flow* | Flujo másico de aire |
| **MAP** | *Manifold Absolute Pressure* | Presión absoluta del múltiple de admisión |
| **OCV** | *Oil Control Valve* | Válvula solenoide de control de aceite (VVT) |
| **PCV** | *Positive Crankcase Ventilation* | Ventilación positiva del cárter |
| **STFT** | *Short-Term Fuel Trim* | Ajuste de combustible a corto plazo |
| **TPS** | *Throttle Position Sensor* | Sensor de posición del acelerador |
| **VSS** | *Vehicle Speed Sensor* | Sensor de velocidad del vehículo |
| **VVT** | *Variable Valve Timing* | Sincronización variable de válvulas |
| **WOT** | *Wide Open Throttle* | Acelerador a fondo |

### 4.4 Sistema de frenos y chasis

| Acrónimo | Significado en inglés | Traducción técnica |
|---|---|---|
| **ADAS** | *Advanced Driver Assistance Systems* | Sistemas avanzados de asistencia al conductor |
| **BAS** | *Brake Assist System* | Asistente de frenado de emergencia |
| **EBD** | *Electronic Brakeforce Distribution* | Distribución electrónica de fuerza de frenado |
| **EPB** | *Electric Parking Brake* | Freno de estacionamiento eléctrico |
| **EPS** | *Electric Power Steering* | Dirección asistida eléctrica |
| **ESC / ESP** | *Electronic Stability Control / Programme* | Control electrónico de estabilidad |
| **HCU** | *Hydraulic Control Unit* | Unidad hidráulica de control (ABS) |
| **OCS** | *Occupant Classification System* | Sistema de clasificación de ocupante |
| **PPS** | *Passenger Presence Sensor* | Sensor de presencia del pasajero |
| **SAS** | *Steering Angle Sensor* | Sensor de ángulo de dirección |
| **TCC** | *Torque Converter Clutch* | Embrague del convertidor de torque |
| **TCS** | *Traction Control System* | Sistema de control de tracción |
| **VDC** | *Vehicle Dynamics Control* | Control dinámico del vehículo (Nissan) |
| **VSC** | *Vehicle Stability Control* | Control de estabilidad (Toyota) |
| **WSS** | *Wheel Speed Sensor* | Sensor de velocidad de rueda |

### 4.5 Sistemas SRS y sujeción

| Acrónimo | Significado en inglés | Traducción técnica |
|---|---|---|
| **OCS** | *Occupant Classification System* | Sistema de clasificación de ocupante (ya listado en 4.4) |
| **PPS** | *Passenger Presence Sensor* | Sensor de presencia del pasajero (ya listado en 4.4) |
| **PATS** | *Passive Anti-Theft System* | Sistema antirrobo pasivo (Ford) |
| **PASS-Lock** | (marca registrada GM) | Sistema antirrobo pasivo de GM |
| **SDM** | *Sensing and Diagnostic Module* | Módulo SRS (ya listado en 4.1) |
| **SkREEM/SKIM** | *Sentry Key Remote Entry Module* | Módulo de inmovilizador (Stellantis) |
| **SRS** | *Supplemental Restraint System* | Sistema suplementario de sujeción |
| **Squib** | (término técnico) | Escudete pirotécnico (carga eléctrica que despliega el airbag) |

### 4.6 Redes de comunicación vehicular

| Acrónimo | Significado en inglés | Traducción técnica |
|---|---|---|
| **CAN** | *Controller Area Network* | Red de área de controladores (par trenzado diferencial) |
| **CAN-H / CAN-L** | *CAN High / CAN Low* | Línea CAN positiva / negativa |
| **CAN FD** | *CAN with Flexible Data-rate* | CAN con velocidad de datos flexible |
| **DoCAN** | *Diagnostics over CAN* | Diagnóstico sobre CAN (ISO 15765) |
| **HS-CAN** | *High-Speed CAN* | CAN de alta velocidad (500 kbit/s típico) |
| **LIN** | *Local Interconnect Network* | Red de interconexión local (19.2 kbit/s) |
| **LS-CAN / SW-CAN** | *Low-Speed / Single-Wire CAN* | CAN de baja velocidad (33.33 kbit/s) |
| **MOST** | *Media Oriented Systems Transport* | Bus para audio/video premium |
| **MS-CAN** | *Medium-Speed CAN* | CAN de velocidad media (125–250 kbit/s) |
| **PT-CAN** | *Powertrain CAN* | CAN del tren motriz (BMW) |
| **UDS** | *Unified Diagnostic Services* | Servicios unificados de diagnóstico (ISO 14229) |

### 4.7 Emisiones y control auxiliar

| Acrónimo | Significado en inglés | Traducción técnica |
|---|---|---|
| **DPF** | *Diesel Particulate Filter* | Filtro de partículas diésel |
| **DPFE** | *Differential Pressure Feedback EGR* | Sensor de presión diferencial EGR |
| **EGR** | *Exhaust Gas Recirculation* | Recirculación de gases de escape |
| **NOx** | (compuesto químico) | Óxidos de nitrógeno |
| **SCR** | *Selective Catalytic Reduction* | Reducción catalítica selectiva (urea/AdBlue) |

### 4.8 Estándares y entidades

| Acrónimo | Significado |
|---|---|
| **CARB** | *California Air Resources Board* — autoridad ambiental de California, marca el estándar OBD-II más estricto. |
| **CCR** | *California Code of Regulations* — código regulatorio de California (referenciado como CCR §1968.2 para OBD II). |
| **EPA** | *U.S. Environmental Protection Agency* — autoridad ambiental federal de EE. UU. |
| **FMVSS** | *Federal Motor Vehicle Safety Standard* — estándar federal de seguridad vehicular (NHTSA). |
| **IEEE** | *Institute of Electrical and Electronics Engineers* — define IEEE 802.3bw (Automotive Ethernet). |
| **INNV** | *Instituto Nacional de Normalización Vehicular* — editor de esta guía. |
| **ISO** | *International Organization for Standardization* — define ISO 9141, 11898, 14229, 15031, 15765, 26021, 26262, etc. |
| **NHTSA** | *National Highway Traffic Safety Administration* — autoridad de seguridad vial de EE. UU. |
| **SAE** | *Society of Automotive Engineers* — define SAE J1850, J1939, J1962, J1979, J2012, J2284, J2399, J2534, etc. |
| **TSB** | *Technical Service Bulletin* — boletín técnico de servicio del fabricante. |

## 5. Términos clave (orden alfabético)

- **Ajuste de combustible** *(fuel trim)*: corrección porcentual
  que la ECM aplica al pulso de inyección para mantener mezcla
  estequiométrica. Existe a corto plazo (STFT) y largo plazo
  (LTFT).
- **Bus Off**: estado en el que un módulo CAN se desconecta del bus
  por exceso de errores TX (>256). Genera DTC `U0073`/`U0074`.
- **Calibración del SAS** *(Steering Angle Reset)*: procedimiento
  de aprendizaje del cero del sensor de ángulo de dirección.
  Requerido tras alineación, reemplazo de batería o intervención
  en columna.
- **Catalizador** *(catalytic converter)*: convertidor catalítico
  que transforma HC, CO y NOx en CO₂, H₂O y N₂.
- **Ciclo de manejo OBD** *(OBD Drive Cycle)*: secuencia de
  condiciones de operación que activa los monitores internos para
  validar reparación y completar Readiness.
- **Clockspring** *(spiral cable / coil spring)*: cinta conductora
  enrollada bajo el volante que mantiene continuidad eléctrica con
  los componentes giratorios (squib, controles del volante).
- **Driver de inyectores**: etapa de potencia integrada al ECM o
  externa (FPDM) que conmuta corriente al inyector.
- **DTC permanente**: código de avería que solo se borra al
  cumplirse las condiciones de auto-validación; no puede borrarse
  manualmente con `Modo 0x04`. Obligatorio en vehículos ≥ 2010.
- **DTC pendiente**: código detectado en un solo ciclo de manejo
  que aún no enciende la MIL. Requiere segundo ciclo confirmando
  para pasar a "confirmado".
- **DTC permanente vs confirmado vs pendiente**: jerarquía
  estandarizada por SAE J1979.
- **EONV** *(Engine Off Natural Vacuum)*: método de prueba EVAP
  que aprovecha la contracción térmica del aire en el tanque al
  apagar el motor.
- **Estequiometría / λ = 1**: relación aire/combustible ideal para
  combustión completa de gasolina (~14.7:1 en masa).
- **Freeze Frame**: captura instantánea de los PIDs del motor en el
  momento exacto en que se almacenó un DTC confirmado. Accesible
  por Modo `0x02`.
- **Gateway**: módulo que enruta mensajes entre buses distintos
  (HS-CAN, MS-CAN, FlexRay, Ethernet) en topologías multi-bus.
- **Inferencia inversa (regla de)**: si **muchos módulos**
  reportan pérdida de comunicación con un mismo módulo X, es
  probable que **X sea el módulo afectado físicamente**, no los
  reportantes.
- **Limp mode** *(modo de emergencia)*: estado del PCM/TCM que
  limita prestaciones (RPM, marchas, velocidad) para proteger
  componentes ante fallas detectadas.
- **Misfire (Type A vs Type B)**: fallo de encendido severo
  (Type A, MIL parpadea, riesgo de daño al catalizador) vs.
  moderado (Type B, MIL fija).
- **Modo bidireccional**: capacidad del escáner de **comandar
  actuadores** (no solo leer). Activación de bomba ABS, válvula
  EVAP, inyectores individuales, etc.
- **Monitor (no continuo)**: prueba interna que se ejecuta solo
  bajo condiciones específicas (catalizador, EVAP, EGR, sensor
  O₂). Resultados accesibles por Modo `0x06`.
- **Readiness Monitor**: estado de los monitores internos
  ("listo" o "no listo"). Visible vía Modo `0x01` PID `0x01`.
  Requerido completo para inspección técnica de emisiones.
- **Reflasheo**: reprogramación del firmware de un módulo (PCM,
  BCM, TCM, etc.) mediante escáner OEM o J2534.
- **Ruido del bus / módulo "ruidoso"**: módulo que genera errores
  CAN (frames inválidos, colisiones) que afectan a toda la red.
- **Squib**: véase 4.5.
- **Tone ring (rueda fónica / encoder ring)**: anillo magnético o
  metálico con dientes equiespaciados, fijo al cubo de la rueda,
  contra el cual el sensor WSS lee la velocidad.
- **TSB** *(Technical Service Bulletin)*: documento del fabricante
  que describe procedimientos para fallos conocidos y, en muchos
  casos, soluciones por reflasheo.
- **VVT (sincronización variable de válvulas)**: sistema que
  desplaza el árbol de levas para optimizar potencia, par y
  emisiones.
- **Watchdog**: temporizador interno del microcontrolador del ECM
  que reinicia el sistema si el firmware deja de responder. Su
  fallo genera `P0606`.
- **Zero Point Set**: alias de calibración del SAS o del sensor de
  yaw.

## 6. Equivalencias inglés ↔ español

Los términos siguientes se conservan en inglés en descripciones
verbatim SAE J2012 pero **se traducen** en prosa técnica:

| Inglés (forma normativa SAE) | Español (forma INNV en prosa) |
|---|---|
| *Air–fuel ratio* | Mezcla aire–combustible |
| *Bank 1 / Bank 2* | Banco 1 / Banco 2 |
| *Body Control Module* | Módulo de control de carrocería |
| *Cam timing* | Sincronización del árbol de levas |
| *Catalyst efficiency* | Eficiencia del catalizador |
| *Drive cycle* | Ciclo de manejo |
| *Driver "A" / "B"* | Etapa de potencia "A" / "B" |
| *Engine knock* | Detonación / cascabeleo |
| *Fuel trim* | Ajuste de combustible |
| *Idle* | Ralentí |
| *Limp mode* | Modo de emergencia / *limp mode* |
| *Misfire* | Fallo de encendido |
| *Open circuit* | Circuito abierto |
| *Pending DTC* | DTC pendiente |
| *Permanent DTC* | DTC permanente |
| *Range/performance* | Rango/desempeño |
| *Slipping* | Patinaje (transmisión) |
| *Smog Check* | Revisión técnica de emisiones |
| *Spark plug* | Bujía |
| *Tone ring* | Anillo dentado / encoder magnético |

> ▪ **NOTA TÉCNICA — REGLA DE CONSERVACIÓN**
> Cuando el documento INNV cite la **descripción literal SAE J2012**
> de un DTC, se conserva el término en inglés (entre comillas o en
> cursiva). En la **prosa explicativa** se prefiere la traducción
> técnica al español listada arriba.

## 7. Códigos de modos OBD-II (resumen)

| Modo | Función |
|---|---|
| `0x01` | Datos en vivo (PIDs actuales) |
| `0x02` | Freeze Frame |
| `0x03` | DTC confirmados |
| `0x04` | Borrado de DTC y Freeze Frame |
| `0x05` | Resultados de prueba de sensores O₂ (no CAN) |
| `0x06` | Resultados de monitores no continuos |
| `0x07` | DTC pendientes |
| `0x08` | Control bidireccional limitado |
| `0x09` | Información del vehículo (VIN, CALID, CVN) |
| `0x0A` | DTC permanentes |

> ▪ Para la tabla extendida de modos y PIDs comunes, ver
> `docs/como-escanear.md` sección 9.

## 8. Bibliografía técnica

1. SAE International. *J1979: E/E Diagnostic Test Modes*.
   Warrendale, PA, 2017.
2. SAE International. *J2012: Diagnostic Trouble Code Definitions*.
   Warrendale, PA, 2016.
3. ISO. *ISO 15031-5: Emissions-related diagnostic services*.
   Geneva, 2015.
4. ISO. *ISO 15031-6: Diagnostic trouble code definitions*.
   Geneva, 2015.
5. ISO. *ISO 14229-1: Unified Diagnostic Services (UDS)*.
   Geneva, 2020.
6. ISO. *ISO 11898-1: Road vehicles — Controller area network
   (CAN) — Part 1*. Geneva, 2015.
7. CARB. *OBD II Regulation, Title 13 CCR §1968.2*. Sacramento,
   2022.
8. EPA. *On-Board Diagnostics (OBD-II) Regulations Reference Guide*.
   Washington D.C., 2020.
9. Bosch GmbH. *Automotive Handbook*. 11.ª edición. Plochingen,
   2022.
10. Denton, T. *Advanced Automotive Fault Diagnosis*. 5.ª edición.
    Routledge, 2020.

---

> **Documento elaborado por:** Instituto Nacional de Normalización
> Vehicular (INNV) — Dirección de Documentación Técnica.
> **Próxima revisión obligatoria:** 24 meses a partir de la fecha
> de publicación.
