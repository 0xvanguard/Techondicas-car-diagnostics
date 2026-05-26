# Procedimiento de Reparación — DTC U0100 (Lost Communication With ECM/PCM)

> **Documento normativo INNV-DT-012**
> **Versión:** 1.0
> **Estándar de referencia:** SAE J2012 / ISO 15031-6 / ISO 11898 / ISO 15765-4
> **Clasificación:** Procedimiento de reparación de aplicación general
> **Audiencia:** Talleres certificados, técnicos automotrices

---

## Índice

1. [Identificación del DTC](#1-identificación-del-dtc)
2. [Advertencias de seguridad](#2-advertencias-de-seguridad)
3. [Equipo y herramientas requeridas](#3-equipo-y-herramientas-requeridas)
4. [Causas probables (ordenadas por frecuencia)](#4-causas-probables-ordenadas-por-frecuencia)
5. [Procedimiento de diagnóstico](#5-procedimiento-de-diagnóstico)
6. [Procedimiento de reparación](#6-procedimiento-de-reparación)
7. [Validación post-reparación](#7-validación-post-reparación)
8. [Cuándo escalar a equipo especializado](#8-cuándo-escalar-a-equipo-especializado)
9. [Bibliografía técnica](#9-bibliografía-técnica)

---

## 1. Identificación del DTC

| Campo | Valor |
|---|---|
| **Código** | `U0100` |
| **Letra de sistema** | U (Network) |
| **Origen** | Genérico SAE J2012 |
| **Subsistema** | Bus de comunicación CAN — pérdida con módulo |
| **Descripción literal** | *Lost Communication With ECM/PCM "A"* |
| **Traducción técnica** | Pérdida de comunicación con el módulo de control del motor / tren motriz "A" |
| **Frecuencia INNV** | Alta — top 3 de códigos Network |
| **Síntomas asociados** | Vehículo no arranca o arranca con limitaciones; múltiples testigos en tablero (Check Engine, ABS, Tracción, Airbag); RPM y velocímetro a cero |

### Significado funcional

El DTC `U0100` lo emite **un módulo distinto al ECM** cuando deja
de recibir mensajes CAN del ECM dentro de un período esperado
(típicamente 100–500 ms). En una topología CAN típica, módulos como
TCM, EBCM, BCM, IPC y SDM esperan mensajes periódicos del ECM con
información crítica (velocidad, RPM, temperatura, posición del
acelerador, estado del freno).

> ▪ **NOTA TÉCNICA — INFERENCIA INVERSA**
>
> Si **muchos módulos** reportan `U0100` simultáneamente, la causa
> está en el **ECM o en el bus** que conecta al ECM, no en cada uno
> de los módulos reportantes.
>
> Si **un solo módulo** reporta `U0100`, la causa está en el
> cableado entre ese módulo y el bus, o en el módulo reportante.

## 2. Advertencias de seguridad

> ⚠️ **ADVERTENCIA — RIESGO ELÉCTRICO Y DE SEGURIDAD**
> Las mediciones de **resistencia** del bus CAN deben hacerse
> SIEMPRE con la **batería desconectada**:
>
> - Conectar un multímetro en escala de Ω a un bus CAN energizado
>   puede dañar el multímetro y los módulos.
> - Las mediciones de **tensión** se hacen con la batería conectada
>   pero con encendido en KOEO inicial.

> ⚠️ **ADVERTENCIA — RIESGO DE NO-ARRANQUE**
> Algunas pruebas requieren desconectar módulos. Tras desconectar
> el ECM o el gateway, el vehículo **puede no arrancar**. Asegúrese
> de:
>
> - Tener el vehículo en lugar accesible.
> - Disponer de batería externa por si fuera necesario.
> - Documentar todas las posiciones originales antes de
>   desconectar.

## 3. Equipo y herramientas requeridas

- Escáner OBD-II nivel 3 mínimo (con capacidad de leer **todos los
  módulos**, no solo el ECM).
- Multímetro digital con resolución de 0.1 Ω.
- **Osciloscopio automotriz** de 2 canales (recomendado para
  capturar señal CAN-H y CAN-L simultáneamente).
- Diagrama eléctrico OEM del vehículo (topología de buses).
- Terminal break-out o conector tipo "Y" para acceder a pines del
  CAN sin desconectar.
- Pinzas peacock o sondas back-probe para perforar mínimamente
  arneses.
- Repuesto de fusibles y relés para descartar.

## 4. Causas probables (ordenadas por frecuencia)

| # | Causa | Frecuencia | Costo |
|---|---|---|---|
| 1 | Fusible del ECM quemado | 25 % | Muy bajo |
| 2 | Conector del ECM flojo, oxidado o dañado | 18 % | Bajo |
| 3 | Falla de masa principal del ECM (cable de masa al chasis) | 15 % | Bajo |
| 4 | Cableado CAN-H o CAN-L cortado entre ECM y bus | 12 % | Medio |
| 5 | Cortocircuito del CAN-H o CAN-L a 12 V o masa | 10 % | Medio |
| 6 | Falla del relé principal del ECM | 8 % | Bajo |
| 7 | Resistencia terminal del ECM dañada (interna) | 5 % | Alto |
| 8 | Falla interna del ECM | 4 % | Muy alto |
| 9 | Falla del módulo gateway (en topologías multi-bus) | 2 % | Alto |
| 10 | Sobretensión por salto de batería incorrecto previo | 1 % | Variable |

## 5. Procedimiento de diagnóstico

### Paso 1 — Inventario completo de DTC

1. Conecte el escáner.
2. Lea **TODOS** los módulos del vehículo, no solo el ECM. Anote
   en tabla:

| Módulo | DTC reportados | ¿Reporta U0100? |
|---|---|---|
| ECM | | — |
| TCM | | |
| EBCM (ABS) | | |
| SDM (SRS) | | |
| BCM | | |
| IPC (cluster) | | |
| HVAC | | |
| Otros | | |

3. Si **el escáner no comunica con el ECM**, ese es el síntoma
   primario. Si comunica con el ECM pero otros módulos reportan
   `U0100`, el problema es entre el ECM y el bus, no en el ECM
   completo.

### Paso 2 — Verificación de alimentación y masa del ECM

> ▪ **NOTA TÉCNICA**
> Esta es la causa más común y más fácil de descartar. Hacerla
> SIEMPRE primero.

1. Localice los fusibles del ECM (módulo principal y relé). Suelen
   ser **2 a 4 fusibles** distintos:
   - Fusible de **memoria** (siempre +12 V).
   - Fusible de **encendido** (+12 V con llave en RUN).
   - Fusible de **inyectores/bobinas** alimentado por el relé del
     ECM.
2. Verifique con multímetro o probador:
   - Tensión en cada fusible con KOEO y KOER.
   - Que ningún fusible esté quemado.
3. Verifique las **masas del ECM**:
   - Localice los pernos de masa según diagrama OEM.
   - Mida con multímetro la **caída de tensión** entre el pin de
     masa del conector del ECM y el negativo de la batería.
   - Caída esperada: **< 0.1 V**. Caídas mayores indican masa
     pobre.

### Paso 3 — Verificación física del bus CAN HS

1. Apague el vehículo y **desconecte la batería**.
2. Espere 5 minutos para que módulos descarguen capacitores.
3. Mida resistencia entre **pin 6 (CAN-H)** y **pin 14 (CAN-L)**
   del conector DLC:

| Lectura | Diagnóstico |
|---|---|
| **≈ 60 Ω** | Bus físicamente OK (paralelo de dos resistencias terminales de 120 Ω) |
| **≈ 120 Ω** | Una resistencia terminal faltante o módulo desconectado |
| **≈ 40 Ω o menos** | Tercera resistencia o cortocircuito en el bus |
| **0 Ω** | Cortocircuito CAN-H ↔ CAN-L |
| **∞ (abierto)** | Ambos pines abiertos: bus completamente cortado |

4. Mida resistencia entre **CAN-H y masa** y entre **CAN-L y
   masa**:
   - Esperado: **alta resistencia (> 1 kΩ)**.
   - Resistencia baja: cortocircuito a masa.
5. Mida resistencia entre **CAN-H y +12 V** y entre **CAN-L y
   +12 V**:
   - Esperado: alta resistencia.
   - Resistencia baja: cortocircuito a +12 V.

### Paso 4 — Verificación de tensión del bus CAN HS

1. Reconecte la batería.
2. Encienda en KOEO (no arrancar).
3. Mida tensión entre cada pin del CAN y masa del chasis:

| Pin DLC | Estado del bus en reposo | Voltaje esperado |
|---|---|---|
| 6 (CAN-H) | Recesivo | ≈ 2.5 V |
| 14 (CAN-L) | Recesivo | ≈ 2.5 V |
| Diferencial (H−L) | Recesivo | ≈ 0 V |
| Diferencial (H−L) | Bit dominante (con osciloscopio) | ≈ 2 V |

4. Si las tensiones están desviadas (ej. CAN-H en 0 V o 12 V), hay
   cortocircuito o módulo defectuoso.

### Paso 5 — Captura con osciloscopio (recomendado)

1. Configure 2 canales:
   - CH1 → CAN-H (pin 6 DLC).
   - CH2 → CAN-L (pin 14 DLC).
   - Escala: 1 V/div, 50 µs/div.
2. Con KOEO o KOER, capture varias tramas.
3. **Bus saludable**:
   - CAN-H y CAN-L oscilan en **espejo** (señal diferencial).
   - Bit recesivo: ambos en ~2.5 V.
   - Bit dominante: CAN-H sube a ~3.5 V, CAN-L baja a ~1.5 V.
4. **Anomalías**:
   - Una sola línea oscila → la otra está cortada o cortocircuitada.
   - Tramas truncadas o con ruido excesivo → módulo "ruidoso" o
     EMI.

### Paso 6 — Aislamiento por desconexión progresiva

Si el bus está físicamente correcto pero hay códigos `U0100`:

1. Identifique todos los módulos del bus HS-CAN.
2. **Desconecte un módulo a la vez**, empezando por los menos
   críticos (radio, climate, módulos de confort).
3. Tras cada desconexión, lea los DTC y verifique si el `U0100`
   desaparece.
4. El módulo cuya desconexión "limpia" el bus es el **módulo
   ruidoso**.

> ▪ **NOTA TÉCNICA — REGLA DE INFERENCIA INVERSA**
>
> Si todos los módulos reportan `U0100`, mantenga conectado solo
> el ECM y desconecte los demás. Si el bus comunica entonces, vaya
> reconectando uno a uno hasta encontrar el módulo conflictivo.

### Paso 7 — Verificación del ECM mismo

Si el problema persiste y todos los signos apuntan al ECM:

1. Inspeccione físicamente el conector del ECM (ubicado típicamente
   en el compartimento del motor o detrás del tablero).
2. Verifique cada pin sin doblarlos: oxidación, retracción de pin,
   sello del conector.
3. Limpie con limpiador de contactos electrónicos.
4. Antes de reemplazar el ECM, **considere causas externas**:
   - Entrada de agua al compartimento donde está el ECM.
   - Daño por sobretensión por salto de batería con polaridad
     invertida o de vehículo de mayor tensión.

## 6. Procedimiento de reparación

### Caso A — Reemplazo de fusible o relé

1. Identifique el fusible o relé fallido.
2. Reemplace por **mismo amperaje y especificación** OEM. **Nunca**
   instalar de mayor amperaje: protege contra fallas mayores.
3. Si el fusible se quema repetidamente, hay un cortocircuito que
   debe resolverse antes de continuar.

### Caso B — Reparación de masa pobre

1. Localice el perno de masa del ECM según diagrama OEM.
2. Retire el perno.
3. Lije la zona de contacto eliminando óxido y pintura.
4. Aplique grasa anticorrosiva en el contacto.
5. Reinstale apretando al par OEM.
6. Verifique caída de tensión post-reparación: debe ser < 0.1 V.

### Caso C — Reparación de cableado CAN

1. Localice el tramo dañado con multímetro.
2. **Importante**: el cable CAN es de **par trenzado** con paso
   específico (~30 trenzas por metro). Al repararlo:
   - Mantenga el trenzado del cable.
   - Use **soldadura y termocontraíble**, no empalmes mecánicos.
   - Preserve la longitud lo más cercana posible a la original.
3. Verifique resistencia y tensiones tras la reparación.

### Caso D — Reemplazo del ECM

> ⚠️ **PROCEDIMIENTO MAYOR**
> El ECM es uno de los módulos más caros del vehículo y el
> reemplazo requiere:
>
> - **Programación con el VIN** del vehículo.
> - **Coincidencia de software** con el resto de módulos
>   (transmisión, ABS).
> - **Reseteo de adaptaciones** (idle learn, transmisión, sensores).
> - En vehículos con inmovilizador: **resincronización** con el
>   módulo de seguridad.
>
> Procedimiento exclusivo de **taller especializado** con escáner
> OEM o equivalente J2534.

### Caso E — Reemplazo de gateway

> ⚠️ **PROCEDIMIENTO MAYOR**
> El módulo gateway requiere también programación específica del
> fabricante. Igualmente, **taller especializado**.

## 7. Validación post-reparación

1. Reconecte la batería.
2. Espere 1 minuto sin tocar el vehículo (los módulos se
   inicializan).
3. Encienda en KOEO. Verifique:
   - El cluster muestra todos los testigos por unos segundos y
     se apagan.
   - El velocímetro y tacómetro responden.
4. Conecte el escáner. Lea TODOS los módulos:
   - No deben quedar códigos `U0100` activos.
   - El Modo `0x0A` (códigos permanentes) debe estar limpio.
5. Realice un ciclo de manejo de al menos 15 minutos combinando
   ralentí, ciudad y carretera.
6. Vuelva a leer todos los módulos: confirma que el problema no
   reaparece.

## 8. Cuándo escalar a equipo especializado

> ⚠️ **ESCALAR A TALLER ESPECIALIZADO SI:**
>
> - El ECM o gateway requiere reemplazo: **siempre** requiere
>   programación OEM.
> - El bus CAN tiene cortocircuito difícil de localizar: requiere
>   osciloscopio multicanal o herramientas tipo CANalyzer.
> - El vehículo es híbrido o eléctrico: la pérdida de comunicación
>   puede afectar el sistema de alta tensión y requiere
>   procedimientos específicos.
> - Hay códigos `U0300` (incompatibilidad de software): requiere
>   reflasheo coordinado.
> - El sistema es una topología compleja con múltiples buses (HS,
>   MS, LS, FlexRay, Ethernet) y se requiere análisis de tráfico
>   real con herramientas profesionales.
> - El vehículo no arranca y no comunica con NINGÚN módulo:
>   posible falla de gateway o alimentación principal.

## 9. Bibliografía técnica

1. SAE International. *J2012: Diagnostic Trouble Code Definitions*.
   Warrendale, PA, 2016.
2. ISO. *ISO 15031-6*. Geneva, 2015.
3. ISO. *ISO 11898-1: Road vehicles — Controller area network
   (CAN) — Part 1: Data link layer and physical signalling*.
   Geneva, 2015.
4. ISO. *ISO 15765-4: Diagnostics on CAN — Part 4: Requirements
   for emissions-related systems*. Geneva, 2021.
5. SAE International. *J2534: Recommended Practice for Pass-Thru
   Vehicle Programming*. Warrendale, PA, 2019.
6. Bosch GmbH. *CAN Specification 2.0*. Stuttgart, 1991 (vigente).

---

> Documento INNV-DT-012. Próxima revisión obligatoria: 24 meses.
