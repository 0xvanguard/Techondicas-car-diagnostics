# Comparativa Técnica de Escáneres OBD-II

> **Documento normativo INNV-DT-006**
> **Versión:** 1.0
> **Estándar de referencia:** SAE J1979 / ISO 15031-5 / ISO 15765-4
> **Clasificación:** Guía técnica de selección de equipo
> **Audiencia:** Talleres, centros de inspección técnica, técnicos
> independientes, estudiantes, autoridades de tránsito

---

## Índice

1. [Objetivo](#1-objetivo)
2. [Alcance](#2-alcance)
3. [Criterios de evaluación INNV](#3-criterios-de-evaluación-innv)
4. [Niveles de capacidad de los escáneres](#4-niveles-de-capacidad-de-los-escáneres)
5. [Comparativa de modelos representativos](#5-comparativa-de-modelos-representativos)
6. [Recomendación INNV por perfil de usuario](#6-recomendación-innv-por-perfil-de-usuario)
7. [Requisitos mínimos para uso oficial](#7-requisitos-mínimos-para-uso-oficial)
8. [Advertencias y limitaciones](#8-advertencias-y-limitaciones)
9. [Bibliografía técnica](#9-bibliografía-técnica)

---

## 1. Objetivo

Establecer los criterios técnicos uniformes para la **selección,
adquisición y verificación** de escáneres OBD-II destinados al
diagnóstico electrónico vehicular, y proveer una comparativa
representativa de modelos disponibles en el mercado latinoamericano
clasificados por nivel de capacidad.

## 2. Alcance

- Aplica a escáneres compatibles con vehículos OBD-II ligeros
  (≤ 3 856 kg PBV) que cumplan **SAE J1962** (conector DLC),
  **SAE J1979 / ISO 15031-5** (modos de servicio) y, para vehículos
  modernos, **ISO 15765-4** (CAN).
- No cubre equipos exclusivos para vehículos pesados (SAE J1939) ni
  herramientas de osciloscopio automotriz, las cuales son
  complementarias.
- La columna de **precio aproximado** es referencial: varía por país,
  por importador y por fluctuación cambiaria. Verifique siempre con
  proveedores autorizados.

## 3. Criterios de evaluación INNV

Cada escáner será evaluado contra **diez criterios técnicos
verificables**:

| # | Criterio | Verificación |
|---|---|---|
| 1 | **Cumplimiento SAE J1979 / ISO 15031-5** | Etiquetado o ficha técnica del fabricante; certificación escrita |
| 2 | **Modos OBD-II soportados** | Mínimo `0x01`, `0x03`, `0x04`, `0x07`. Recomendado `0x02`, `0x06`, `0x09`, `0x0A` |
| 3 | **Lectura de Freeze Frame (Modo `0x02`)** | Test directo en vehículo con DTC simulado |
| 4 | **Monitores de Readiness (Modo `0x01` PID `0x01`)** | Visualización del estado de los 9 monitores |
| 5 | **PIDs en vivo simultáneos** | Cantidad de PIDs graficables a la vez (mínimo 4 recomendado) |
| 6 | **Cobertura de protocolos** | ISO 9141-2, ISO 14230-4, SAE J1850 PWM/VPW, ISO 15765-4 (CAN) |
| 7 | **Cobertura OEM básica** | Acceso a códigos `P1xxx`, `B1xxx`, `C1xxx`, `U1xxx` de marcas principales |
| 8 | **Sistemas no-motor** | Acceso a ABS, SRS, TCM, BCM, HVAC, inmovilizador |
| 9 | **Funciones bidireccionales** | Activación de actuadores (bomba ABS, válvulas EVAP, inyectores, EGR) |
| 10 | **Conectividad y actualizaciones** | USB / Bluetooth / Wi-Fi; vigencia y costo de las actualizaciones |

> ▪ **NOTA TÉCNICA — IDIOMA Y SOPORTE**
> Para uso en países hispanohablantes, INNV recomienda exigir
> adicionalmente:
>
> - Interfaz de usuario en **español** (verificar versión real, no
>   solo "soporte multiidioma" del catálogo).
> - Manual de operación en español.
> - Soporte técnico con respuesta documentada en español.
> - Disponibilidad de repuestos del cable OBD-II en mercado local.

## 4. Niveles de capacidad de los escáneres

Para evitar comparaciones injustas entre equipos de propósitos
distintos, INNV clasifica los escáneres en **cuatro niveles**:

### Nivel 1 — Lectores básicos

- Lectura/borrado de DTC genéricos.
- PIDs en vivo limitados.
- Sin acceso a sistemas distintos del motor.
- Uso típico: usuario particular informado, prediagnóstico antes de
  ir al taller.

### Nivel 2 — Escáneres genéricos avanzados

- Modos OBD-II completos (01–0A).
- Freeze Frame, Readiness, gráficas en vivo.
- Lectura de DTC genéricos en ABS y SRS de algunas marcas.
- Sin funciones bidireccionales completas.
- Uso típico: técnico independiente, talleres pequeños.

### Nivel 3 — Escáneres profesionales multi-marca

- Cobertura amplia de OEM en motor, transmisión, ABS, SRS, BCM.
- Funciones bidireccionales (activación de actuadores).
- Adaptaciones y reseteo de servicio.
- Codificación limitada.
- Uso típico: talleres profesionales multi-marca, centros de
  inspección.

### Nivel 4 — Equipo OEM o grado fábrica

- Cobertura completa de la marca específica.
- Programación y reflasheo de módulos.
- Codificación y configuración AsBuilt.
- Uso típico: concesionarios autorizados, talleres especializados de
  marca.

## 5. Comparativa de modelos representativos

> ⚠️ **AVISO**
> La siguiente tabla es **representativa, no exhaustiva**. Los
> modelos cambian frecuentemente. Verifique especificaciones
> actualizadas con el fabricante antes de la compra.

| # | Modelo | Nivel | Conectividad | Precio aprox. (USD) | Pros | Contras |
|---|---|---|---|---|---|---|
| 1 | **ELM327 Bluetooth/USB (clones genéricos)** | 1 | Bluetooth, USB, Wi-Fi | 10 – 25 | Económico, integración con apps móviles (Torque, Car Scanner ELM OBD2), portátil | Calidad muy variable; muchos clones no implementan todos los modos; sin soporte oficial; firmware no auditable |
| 2 | **OBDLink MX+ / OBDLink LX** | 1+ | Bluetooth | 70 – 140 | Firmware oficial (ScanTool/OBDLink), implementación completa de modos, soporte Android/iOS, baja latencia | Requiere app de terceros para funciones avanzadas; sin pantalla propia |
| 3 | **Foxwell NT301** | 2 | USB (PC) + pantalla propia | 60 – 90 | Modos 01–0A completos, Freeze Frame, Readiness, I/M monitor, multilenguaje | Solo motor (sin ABS/SRS); sin bidireccional; cobertura OEM limitada |
| 4 | **Autel AutoLink AL519 / AL539** | 2 | USB + pantalla propia | 60 – 100 | Modos 01–0A, listo para inspección de emisiones, lectura de DTC en español, multilenguaje | Solo motor; sin bidireccional |
| 5 | **Innova 5610 / 5310** | 2 | USB + pantalla propia | 200 – 320 | ABS y SRS para marcas principales (GM, Ford, Toyota, Honda, Chrysler), reset de aceite | Cobertura OEM más limitada que Launch/Autel; sin bidireccional avanzado |
| 6 | **Launch CRP123E / CRP129E** | 2–3 | Wi-Fi + pantalla propia | 130 – 250 | Motor + transmisión + ABS + SRS, actualización gratuita Wi-Fi (modelos E), buen soporte multimarca | Bidireccional limitado; cobertura OEM media |
| 7 | **Autel MaxiCOM MK808 / MK808S** | 3 | Wi-Fi + pantalla táctil Android | 350 – 500 | Todos los sistemas, 30+ funciones de servicio (EPB, SAS, BMS, DPF), cobertura OEM amplia, bidireccional | Sin programación de módulos (no codifica); actualizaciones anuales con costo |
| 8 | **Launch X431 V / X431 PRO3S+** | 3 | Wi-Fi/Bluetooth + tablet Android | 700 – 1 200 | Bidireccional completo, codificación básica, ECU coding en marcas selectas, gran cobertura OEM | Curva de aprendizaje; suscripción anual de actualizaciones |
| 9 | **Autel MaxiSys MS906 Pro / MS909** | 3–4 | Wi-Fi/Bluetooth + tablet Android | 1 100 – 2 500 | Bidireccional total, codificación, programación J2534, ADAS, topología CAN | Costo elevado; suscripción anual obligatoria para mantener cobertura |
| 10 | **VCDS (Ross-Tech) — Cable HEX-V2** | 4 (VAG) | USB + PC Windows | 250 – 450 | Equivalente a herramienta de fábrica para grupo VAG (VW/Audi/Seat/Skoda), interfaz en español, sin suscripción | Solo grupo VAG; otras marcas no soportadas |
| 11 | **Bosch ADS 625 / KTS 560 / KTS 590** | 4 | Wi-Fi/Bluetooth | 2 500 – 5 000 | Grado taller industrial, integración con base de datos ESI[tronic], multimarca avanzado | Inversión elevada; requiere infraestructura de taller |
| 12 | **Equipo OEM original** (Tech 2 / GDS2 — GM, IDS/FDRS — Ford, Techstream — Toyota, wiTECH — Stellantis, ISTA — BMW, XENTRY — Mercedes-Benz, CONSULT-III — Nissan) | 4 | USB / Wi-Fi (según marca) | 500 – 8 000+ | Cobertura completa de la marca, programación oficial, codificación, actualizaciones del fabricante | Cobertura limitada a una sola marca; licenciamiento OEM frecuentemente requerido |

> ▪ **NOTA TÉCNICA — CLONES VS. ORIGINALES**
> Existen clones no autorizados de la mayoría de los equipos de
> nivel 3 y 4. INNV **desaconseja** su uso por:
>
> - Incumplimiento de normativa de propiedad intelectual.
> - Riesgo de daño a módulos del vehículo durante reflasheos.
> - Sin soporte técnico ni actualizaciones legítimas.
> - Posible bloqueo permanente del equipo si el fabricante detecta
>   firmware no autorizado.

## 6. Recomendación INNV por perfil de usuario

### 6.1 Usuario particular / propietario informado

- **Mínimo aceptable:** Nivel 1 (ELM327 con app *Torque Pro* o *Car
  Scanner ELM OBD2*).
- **Recomendado:** **OBDLink MX+** o **Foxwell NT301**.
- **Uso esperado:** lectura de DTC antes de visitar el taller,
  monitoreo de PIDs (consumo, ECT, RPM, ajustes de combustible).
- **No comprar** equipos de nivel 3 si no se tiene la formación
  técnica para interpretar funciones bidireccionales.

### 6.2 Estudiante de mecánica automotriz

- **Mínimo aceptable:** **Foxwell NT301** o **Autel AL519**.
- **Recomendado:** **Launch CRP123E** o **CRP129E**.
- **Uso esperado:** práctica con todos los modos OBD-II, lectura de
  Freeze Frame, interpretación de Readiness Monitors.

### 6.3 Técnico independiente / taller pequeño multimarca

- **Mínimo aceptable:** **Launch CRP129E** o **Innova 5610**.
- **Recomendado:** **Autel MaxiCOM MK808S** o **Launch X431 V**.
- **Uso esperado:** diagnóstico completo de motor + ABS + SRS +
  transmisión, funciones de servicio (reset EPB, SAS, BMS, DPF,
  oil reset), bidireccional para validar fallas antes de cambiar
  componentes.

### 6.4 Taller especializado / centro de inspección técnico-mecánica

- **Mínimo aceptable:** **Autel MaxiSys MS906 Pro** o **Launch
  X431 PRO3S+**.
- **Recomendado:** **Autel MaxiSys MS909** + equipo OEM de las
  marcas más frecuentes en su mercado local + osciloscopio
  automotriz.
- **Uso esperado:** programación J2534, codificación, ADAS,
  diagnóstico de redes CAN/CAN FD/Ethernet con osciloscopio.

### 6.5 Concesionario o taller autorizado de marca

- **Único aceptable:** Equipo **OEM original** de la marca, con
  suscripción al portal técnico del fabricante (TIS, FDRS, GDS2,
  Techstream, etc.).
- **Complemento recomendado:** un equipo de nivel 3–4 multimarca
  para diagnóstico de vehículos de cortesía o intercambio.

### 6.6 Autoridades de tránsito y centros de revisión técnica

- **Mínimo aceptable:** Equipo de **nivel 2** verificado contra los
  requisitos de la sección 7, con generación de **reporte impreso o
  digital firmado** que incluya VIN, lista de DTC y estado de
  monitores de Readiness.
- **Recomendado:** Equipo de **nivel 3** con función específica de
  emisiones (*OBD-II Smog Check / I/M Readiness*), trazabilidad de
  operador y archivo histórico.

## 7. Requisitos mínimos para uso oficial

INNV recomienda que toda autoridad regulatoria que adopte el OBD-II
como medio de inspección oficial exija a los escáneres:

1. ✅ Cumplimiento documentado de **SAE J1979** y **ISO 15765-4**.
2. ✅ Soporte completo de los modos `0x01`, `0x02`, `0x03`, `0x04`,
   `0x07`, `0x09` y `0x0A`.
3. ✅ Capacidad de generar un **reporte estandarizado** que incluya:
   - VIN del vehículo (Modo `0x09` PID `0x02`).
   - CALID y CVN (Modo `0x09` PIDs `0x04` y `0x06`).
   - Listado completo de DTC confirmados y permanentes.
   - Estado de los 9 monitores de Readiness.
   - Fecha, hora y ID del operador.
4. ✅ Trazabilidad de actualizaciones de firmware con número de
   versión visible.
5. ✅ Calibración o verificación periódica documentada.
6. ✅ Imposibilidad técnica de **borrar DTC** durante una inspección
   oficial (modo de operación restringido).

> ▪ **NOTA TÉCNICA — REPORTE INMUTABLE**
> Para evidencia técnica con valor legal, el reporte debe generarse
> con marca temporal y, preferentemente, firma digital o hash que
> permita verificar que no fue modificado posteriormente.

## 8. Advertencias y limitaciones

> ⚠️ **ADVERTENCIA — CLONES Y EQUIPOS NO CERTIFICADOS**
> Un escáner barato no certificado puede:
>
> - Reportar DTC inexistentes o omitir DTC reales.
> - Aplicar voltajes incorrectos al bus CAN durante la
>   inicialización, dañando módulos.
> - Realizar borrados parciales que dejan códigos permanentes en
>   estado inconsistente.
> - Reflasheos fallidos que **inutilizan permanentemente** módulos
>   del vehículo (ECM, BCM, gateway).

> 🛑 **ADVERTENCIA CRÍTICA — VEHÍCULOS HÍBRIDOS Y ELÉCTRICOS**
> Algunos sistemas de gestión de la batería de tracción (BMS) y de
> la unidad de potencia (MGU/PCU) **no son accesibles** mediante
> OBD-II genérico. Requieren equipo OEM o de nivel 4 con cobertura
> específica. **No interactúe con módulos de alta tensión sin
> certificación HV: riesgo de lesión grave o muerte.**

> ⚠️ **ADVERTENCIA — CONEXIÓN PERMANENTE**
> Los escáneres tipo "dongle" Bluetooth/Wi-Fi conectados de forma
> permanente al DLC pueden:
>
> - Mantener módulos despiertos e impedir que el vehículo entre en
>   modo *sleep*, descargando la batería en pocos días.
> - Ser un vector de seguridad informática (acceso remoto al CAN).
>
> Desconecte el dongle cuando no esté en uso activo.

## 9. Bibliografía técnica

1. SAE International. *J1979: E/E Diagnostic Test Modes*.
   Warrendale, PA, 2017.
2. SAE International. *J1962: Diagnostic Connector*. Warrendale,
   PA, 2016.
3. SAE International. *J2534: Recommended Practice for Pass-Thru
   Vehicle Programming*. Warrendale, PA, 2019.
4. ISO. *ISO 15031-5: Emissions-related diagnostic services*.
   Geneva, 2015.
5. ISO. *ISO 15765-4: Diagnostics on CAN — Part 4: Requirements
   for emissions-related systems*. Geneva, 2021.
6. CARB (California Air Resources Board). *OBD II Regulation,
   Title 13 CCR §1968.2*. Sacramento, 2022.
7. EPA. *Inspection/Maintenance (I/M) Program Requirements — 40
   CFR Part 51 Subpart S*. Washington D.C., 2021.
8. Ross-Tech LLC. *VCDS Reference Manual*. Lansdale, PA, 2024.
9. Bosch GmbH. *Automotive Diagnostic Equipment — Technical
   Reference*. Plochingen, 2022.

---

> **Documento elaborado por:** Instituto Nacional de Normalización
> Vehicular (INNV) — Dirección de Documentación Técnica.
> **Próxima revisión obligatoria:** 12 meses a partir de la fecha
> de publicación (frecuencia mayor por la rotación rápida del
> mercado de equipos).
