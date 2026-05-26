# Catálogo Técnico de Códigos DTC — Categoría C (Chassis)

> **Documento normativo INNV-DT-004**
> **Versión:** 1.0
> **Estándar de referencia:** SAE J2012 / ISO 15031-6
> **Clasificación:** Catálogo técnico de aplicación general
> **Audiencia:** Talleres certificados, técnicos automotrices, peritos

---

## Índice

1. [Objetivo](#1-objetivo)
2. [Alcance](#2-alcance)
3. [Estructura del código C](#3-estructura-del-código-c)
4. [Subsistemas cubiertos](#4-subsistemas-cubiertos)
5. [Tabla maestra de los 50 códigos C más frecuentes](#5-tabla-maestra-de-los-50-códigos-c-más-frecuentes)
6. [Variaciones por fabricante (OEM)](#6-variaciones-por-fabricante-oem)
7. [Procedimiento de uso de la tabla](#7-procedimiento-de-uso-de-la-tabla)
8. [Bibliografía técnica](#8-bibliografía-técnica)

---

## 1. Objetivo

Proveer un catálogo técnico de referencia rápida con los **50 códigos
DTC de la categoría Chassis (letra C)** más relevantes para el
diagnóstico del sistema antibloqueo (ABS), control electrónico de
estabilidad (ESC/ESP), distribución electrónica de frenado (EBD),
control de tracción (TCS), suspensión y dirección asistida, conforme
al estándar **SAE J2012**.

## 2. Alcance

- Aplica al rango definido por SAE como genérico: **C0xxx** y **C3xxx**.
- Incluye códigos **C1xxx/C2xxx** ampliamente documentados en bases
  de datos OEM, marcados explícitamente como **específicos del
  fabricante**.
- La columna *"Solución básica"* es **orientativa**.

> ⚠️ **ADVERTENCIA CRÍTICA — SISTEMA DE FRENADO**
> Una falla en cualquiera de los subsistemas de chasis puede
> comprometer la **distancia y estabilidad de frenado**. Mientras un
> código DTC de la franja C esté activo:
>
> - Reduzca la velocidad y conduzca con precaución.
> - **No active el control de crucero adaptativo ni asistencias
>   ADAS** que dependan del módulo afectado.
> - Si el testigo del freno principal (rojo) se enciende junto con el
>   ABS, **detenga el vehículo de forma segura** y solicite asistencia
>   mecánica.

## 3. Estructura del código C

```
C 0 0 3 5
│ │ │ └─┴── Identificador específico
│ │ └────── Subsistema (ver tabla 4.1)
│ └──────── 0 = genérico SAE | 1 = OEM | 2 = OEM | 3 = SAE reservado
└────────── C = Chassis
```

## 4. Subsistemas cubiertos

### Tabla 4.1 — Asignación funcional aproximada en C0xxx

| Rango | Subsistema |
|---|---|
| C0020–C0099 | Solenoides hidráulicos del ABS |
| C0100–C0199 | Bomba, relé y circuitos hidráulicos |
| C0200–C0299 | Sensores de velocidad de rueda (WSS) |
| C0300–C0399 | Tracción 4WD, transferencia |
| C0400–C0499 | Sistemas de suspensión activa/neumática |
| C0500–C0599 | Sistema de frenos electrónico — fallas globales |
| C0700–C0799 | Sensores de dirección, ángulo de volante |
| C0800–C0899 | Alimentación y masas del módulo |
| C0900–C0999 | Comunicación interna del módulo de frenos |

> 📋 **NOTA TÉCNICA:** El módulo electrónico de control del freno
> (EBCM/ABS Module) requiere alimentación principal robusta. Caídas
> de tensión por debajo de 9 V durante el arranque pueden generar
> falsos positivos en C0800/C0900. Verifique la batería antes de
> reemplazar componentes.

## 5. Tabla maestra de los 50 códigos C más frecuentes

> **Leyenda de origen:**
> 🅢 = Genérico SAE J2012 (C0xxx / C3xxx) · 🅞 = Específico OEM (C1xxx / C2xxx)

| # | Código | Origen | Descripción | Causa probable | Solución básica |
|---|---|---|---|---|---|
| 1 | **C0020** | 🅢 | Circuito de control del motor de la bomba ABS | Bomba ABS quemada, relé defectuoso | Verificar resistencia del motor; reemplazar motor de bomba o módulo HCU |
| 2 | **C0035** | 🅢 | Circuito del sensor de velocidad rueda delantera izquierda | Sensor WSS contaminado, anillo magnético dañado, arnés roto | Limpiar sensor; verificar anillo (tone ring) y entrehierro |
| 3 | **C0040** | 🅢 | Circuito del sensor de velocidad rueda delantera derecha | Idem C0035 lado derecho | Procedimiento equivalente |
| 4 | **C0041** | 🅢 | Sensor de velocidad rueda delantera derecha — rango/desempeño | Sensor desviado, lectura inconsistente con WSS opuesto | Comparar señales en datos en vivo a 30/60 km/h |
| 5 | **C0045** | 🅢 | Circuito del sensor de velocidad rueda trasera izquierda | Sensor trasero contaminado o cableado | Limpieza; verificar arnés trasero |
| 6 | **C0046** | 🅢 | Sensor velocidad rueda trasera izquierda — rango/desempeño | Lectura errática | Verificar tone ring y rodamiento |
| 7 | **C0050** | 🅢 | Circuito del sensor de velocidad rueda trasera derecha | Sensor o cableado | Procedimiento equivalente al C0045 |
| 8 | **C0051** | 🅢 | Sensor velocidad rueda trasera derecha — rango/desempeño | Lectura errática | Verificar tone ring y rodamiento |
| 9 | **C0055** | 🅢 | Circuito del sensor de velocidad de rueda trasera (eje) | Aplicable a sistemas con un solo sensor de eje trasero | Verificar sensor en cárter del diferencial |
| 10 | **C0060** | 🅢 | Solenoide ABS #1 delantero izquierdo | Bobina del solenoide en HCU | Diagnóstico bidireccional con escáner; reemplazar HCU si abierto |
| 11 | **C0065** | 🅢 | Solenoide ABS #2 delantero izquierdo | Idem C0060 etapa de alivio | Idem C0060 |
| 12 | **C0070** | 🅢 | Solenoide ABS #1 delantero derecho | Solenoide HCU lado derecho | Diagnóstico bidireccional |
| 13 | **C0075** | 🅢 | Solenoide ABS #2 delantero derecho | Idem C0070 etapa de alivio | Idem C0070 |
| 14 | **C0080** | 🅢 | Solenoide ABS #1 trasero izquierdo | Solenoide HCU trasero | Diagnóstico bidireccional |
| 15 | **C0085** | 🅢 | Solenoide ABS #2 trasero izquierdo | Idem C0080 etapa de alivio | Idem C0080 |
| 16 | **C0090** | 🅢 | Solenoide ABS #1 trasero derecho | Solenoide HCU trasero derecho | Diagnóstico bidireccional |
| 17 | **C0095** | 🅢 | Solenoide ABS #2 trasero derecho | Idem C0090 etapa de alivio | Idem C0090 |
| 18 | **C0110** | 🅢 | Falla del circuito del motor de la bomba | Motor bomba abierto/atascado, relé | Test bidireccional de bomba; verificar relé |
| 19 | **C0121** | 🅢 | Circuito del relé de válvulas | Relé de válvulas, alimentación principal | Verificar fusible de potencia y relé |
| 20 | **C0131** | 🅢 | Falla del circuito de presión hidráulica | Sensor de presión interno HCU | Reemplazar sensor o HCU según OEM |
| 21 | **C0141** | 🅢 | Coherencia del sensor de velocidad delantera derecha | Diferencia anómala entre WSS izq/der | Verificar circunferencia/tamaño de neumáticos y tone ring |
| 22 | **C0161** | 🅢 | Circuito del switch de luz de freno (ABS/TCS) | Switch del pedal de freno | Reemplazar switch; ajustar posición |
| 23 | **C0186** | 🅢 | Circuito del sensor de aceleración lateral | Sensor lateral en consola/centro de gravedad | Verificar conector y nivelación; recalibrar |
| 24 | **C0196** | 🅢 | Circuito del sensor de yaw rate (giro) | Sensor de yaw — comúnmente integrado con lateral G | Recalibrar sensor (Zero-Point Calibration) |
| 25 | **C0200** | 🅢 | Falla del circuito de velocidad rueda delantera derecha | Variante OEM del C0040 | Procedimiento equivalente al C0040 |
| 26 | **C0210** | 🅢 | Falla del circuito de velocidad rueda delantera izquierda | Variante OEM del C0035 | Procedimiento equivalente al C0035 |
| 27 | **C0221** | 🅢 | Señal del sensor delantero derecho ausente | Sensor desconectado, anillo dañado | Inspección física del sensor y rotor |
| 28 | **C0235** | 🅢 | Falla del circuito de velocidad de rueda trasera | Sensor trasero | Verificar continuidad |
| 29 | **C0245** | 🅢 | Error de frecuencia del sensor de velocidad de rueda | Anillo magnético excéntrico o dañado | Reemplazar tone ring; verificar holgura del rodamiento |
| 30 | **C0265** | 🅢 | Circuito del relé del EBCM | Relé principal del módulo de frenos | Reemplazar relé principal del EBCM |
| 31 | **C0267** | 🅢 | Circuito del motor de la bomba — abierto | Conexión interna del motor | Reemplazar HCU completo |
| 32 | **C0271** | 🅢 | Desempeño interno del EBCM | Falla interna del módulo | Reflasheo o reemplazo del EBCM |
| 33 | **C0273** | 🅢 | Pérdida de comunicación del EBCM | Bus CAN, alimentación del módulo | Verificar CAN y masas; ver `docs/codigos-U.md` |
| 34 | **C0277** | 🅢 | Circuito del switch de luces de freno | Switch defectuoso, ajuste | Reemplazar switch; calibrar |
| 35 | **C0281** | 🅢 | Circuito del switch de freno (entrada al módulo) | Idem C0277 con cableado al módulo | Verificar continuidad al módulo |
| 36 | **C0288** | 🅢 | Problema hidráulico del sistema de frenos | Aire en el sistema, fuga, bomba degradada | Sangrado del sistema; prueba de presión |
| 37 | **C0292** | 🅢 | Falla de comunicación reportada por el PCM | PCM no responde al EBCM por CAN | Diagnóstico de red CAN |
| 38 | **C0300** | 🅢 | Motor de tracción 4WD/AWD | Actuador 4WD, encoder | Verificar accionamiento del transfer case |
| 39 | **C0327** | 🅢 | Circuito del motor del codificador (encoder 4WD) | Encoder del transfer case | Reemplazar encoder; recalibrar |
| 40 | **C0455** | 🅢 | Sensor de altura del vehículo (suspensión activa) | Sensor de altura desacoplado o roto | Inspeccionar varillaje del sensor; recalibrar altura |
| 41 | **C0550** | 🅢 | Falla de hardware de la ECU | EBCM dañado | Reemplazo del módulo |
| 42 | **C0561** | 🅢 | Sistema deshabilitado — información almacenada | Otro DTC primario está deshabilitando ABS/ESC | Resolver el DTC raíz indicado por el escáner |
| 43 | **C0710** | 🅢 | Señal del sensor de posición de la dirección (SAS) | SAS desviado, recalibración pendiente | Recalibrar sensor de ángulo de dirección |
| 44 | **C0800** | 🅢 | Tensión de alimentación (batería) fuera de rango | Batería baja, alternador, masa pobre | Verificar tensión durante arranque y marcha |
| 45 | **C0896** | 🅢 | Circuito de tensión del sistema | Caídas de tensión repetitivas | Inspeccionar masas del módulo |
| 46 | **C0900** | 🅢 | Bus de comunicación serial | CAN del chasis | Diagnóstico CAN — ver `codigos-U.md` |
| 47 | **C0902** | 🅢 | Bus de comunicación serial — apagado | Bus en estado *off* | Inspeccionar resistencias terminales 60 Ω del CAN |
| 48 | **C1095** | 🅞 | Falla del motor de la bomba (Toyota común) | Bomba ABS Toyota — fallo de masa o motor | Verificar masa principal del actuador |
| 49 | **C1201** | 🅞 | Sistema ECM/PCM falla (Toyota — VSC desactivado) | Falla del control del motor afecta VSC | Diagnosticar primero códigos P; VSC depende del motor |
| 50 | **C1241** | 🅞 | Tensión de alimentación baja (Toyota/Lexus) | Batería o alternador | Verificar sistema de carga |

## 6. Variaciones por fabricante (OEM)

> 📋 **NOTA TÉCNICA — INTERPRETACIÓN OEM**
>
> El rango **C1xxx/C2xxx** está reservado a definiciones específicas
> del fabricante. Ejemplos relevantes:
>
> - **Toyota / Lexus:** uso intensivo del rango C1xxx para ABS/VSC
>   en plataformas Denso. Procedimientos de calibración del sensor
>   yaw/G y SAS son obligatorios tras reemplazo de batería en
>   muchos modelos.
> - **General Motors:** códigos C0xxx mayormente alineados con SAE,
>   pero el procedimiento de *Brake Bleed* automático del HCU
>   requiere Tech 2 / GDS2.
> - **Ford / Lincoln:** documentación FDRS; calibración del SAS
>   obligatoria tras alineación.
> - **Stellantis (Chrysler/Jeep):** uso de C2xxx para sistemas ESP
>   y AWD propios.
> - **Grupo VAG (VW/Audi/Seat/Skoda):** *Basic Settings* del módulo
>   ABS y calibración G/yaw mediante VCDS/ODIS son habituales.
> - **BMW / Mercedes-Benz:** sistemas DSC/ESP propios con
>   diagnóstico vía ISTA/XENTRY; equivalencias a SAE solo
>   orientativas.
> - **Hyundai / Kia:** plataformas Mando con códigos C1xxx
>   documentados en GDS.
> - **Nissan / Infiniti:** códigos C1xxx para VDC y 4WD
>   documentados en CONSULT-III.

> ⚠️ **ADVERTENCIA — CALIBRACIONES OBLIGATORIAS**
> Tras cualquiera de las siguientes intervenciones, el módulo de
> chasis **debe recalibrarse** con escáner OEM o equivalente
> certificado:
>
> - Reemplazo del sensor de ángulo de dirección (SAS).
> - Reemplazo del sensor de yaw / aceleración lateral.
> - Reemplazo del módulo EBCM/ABS.
> - Alineación de dirección.
> - Reemplazo de neumáticos con dimensión distinta a la de fábrica.
> - Reemplazo de cualquier sensor WSS o tone ring.

## 7. Procedimiento de uso de la tabla

1. Realice el escaneo conforme a [`docs/como-escanear.md`](como-escanear.md).
2. Si el código es **C0xxx**, búsquelo en la tabla maestra.
3. Si el código es **C1xxx/C2xxx**, consulte la base OEM de la marca.
4. Antes de reemplazar componentes hidráulicos:
   - Verifique nivel y estado del líquido de frenos (DOT 3/4/5.1
     según especificación del fabricante).
   - Inspeccione visualmente fugas, mangueras y pinzas.
   - Confirme tensión de batería ≥ 12.4 V en reposo.
5. Use el modo bidireccional del escáner para activar bomba y
   solenoides individualmente antes de condenar el HCU.
6. Después de la reparación: borrar DTC, ejecutar **sangrado
   automático** del HCU (si lo requiere), recalibrar SAS y yaw,
   verificar con un ciclo de manejo a velocidades menores y mayores
   de 25 km/h (umbral típico de activación del sistema).

> ⚠️ **ADVERTENCIA — REPARACIONES NO AUTORIZADAS PARA USUARIO GENERAL**
> Los siguientes procedimientos requieren equipo de taller
> especializado:
>
> - Reemplazo y programación del módulo EBCM/ABS.
> - Sangrado automático del HCU (presurización electrónica).
> - Calibración del sensor de ángulo de dirección y yaw.
> - Reemplazo del actuador hidráulico completo (HCU).
> - Reparación de líneas de freno bajo presión.

## 8. Bibliografía técnica

1. SAE International. *J2012: Diagnostic Trouble Code Definitions*.
   Warrendale, PA, 2016.
2. ISO. *ISO 15031-6: Road vehicles — Communication between vehicle
   and external equipment for emissions-related diagnostics — Part 6:
   Diagnostic trouble code definitions*. Geneva, 2015.
3. ISO. *ISO 26262: Road vehicles — Functional safety*. Geneva, 2018.
4. SAE International. *J2399: Adaptive Cruise Control Operating
   Characteristics and User Interface*. Warrendale, PA, 2014.
5. Bosch GmbH. *Driving-Safety Systems*. 3.ª edición. Plochingen, 2019.
6. NHTSA. *FMVSS No. 126 — Electronic Stability Control Systems*.
   Washington D.C., 2007.

---

> **Documento elaborado por:** Instituto Nacional de Normalización
> Vehicular (INNV) — Dirección de Documentación Técnica.
> **Próxima revisión obligatoria:** 24 meses a partir de la fecha de
> publicación.
