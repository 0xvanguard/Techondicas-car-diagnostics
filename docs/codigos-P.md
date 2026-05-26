# Catálogo Técnico de Códigos DTC — Categoría P (Powertrain)

> **Documento normativo INNV-DT-002**
> **Versión:** 1.0
> **Estándar de referencia:** SAE J2012 / ISO 15031-6
> **Clasificación:** Catálogo técnico de aplicación general
> **Audiencia:** Talleres certificados, técnicos automotrices, peritos

---

## Índice

1. [Objetivo](#1-objetivo)
2. [Alcance](#2-alcance)
3. [Estructura del código P](#3-estructura-del-código-p)
4. [Convenciones de bancos y sensores](#4-convenciones-de-bancos-y-sensores)
5. [Tabla maestra de los 50 códigos P más frecuentes](#5-tabla-maestra-de-los-50-códigos-p-más-frecuentes)
6. [Notas sobre variaciones por fabricante (OEM)](#6-notas-sobre-variaciones-por-fabricante-oem)
7. [Procedimiento de uso de la tabla](#7-procedimiento-de-uso-de-la-tabla)
8. [Bibliografía técnica](#8-bibliografía-técnica)

---

## 1. Objetivo

Proveer un catálogo técnico de referencia rápida con los **50 códigos
DTC de la categoría Powertrain (letra P)** de mayor incidencia en el
parque vehicular latinoamericano, con descripción literal SAE, causa
probable validada y solución básica orientativa.

## 2. Alcance

- Aplica exclusivamente a códigos genéricos **P0xxx** y **P2xxx**
  definidos por SAE J2012.
- Los códigos **P1xxx** y **P3xxx** son específicos del fabricante y
  **no se incluyen** en esta tabla genérica.
- La columna *"Solución básica"* es **orientativa**. La reparación
  definitiva debe basarse en el manual de servicio del fabricante y en
  el procedimiento detallado del directorio `fixes/`.

> ⚠️ **ADVERTENCIA**
> La presencia de un DTC **no implica** falla del componente nombrado:
> indica que la ECU detectó una condición fuera del rango esperado en
> el circuito o subsistema asociado. Antes de reemplazar piezas,
> verifique cableado, conectores, masa y alimentación.

## 3. Estructura del código P

```
P 0 4 2 0
│ │ │ └─┴── Identificador específico
│ │ └────── Subsistema (ver tabla 3.1)
│ └──────── 0 = genérico SAE | 1 = OEM
└────────── P = Powertrain
```

### Tabla 3.1 — Asignación de subsistema (tercer dígito)

| Dígito | Subsistema |
|---|---|
| 0, 1, 2 | Sistema de combustible y aire |
| 3 | Sistema de encendido / fallos de encendido (misfire) |
| 4 | Control auxiliar de emisiones (EVAP, EGR, catalizador) |
| 5 | Control de velocidad y ralentí |
| 6 | Sistemas de salida del computador (PCM, comunicación interna) |
| 7, 8, 9 | Transmisión |

## 4. Convenciones de bancos y sensores

Los DTC referidos a sensores múltiples utilizan la siguiente nomenclatura:

- **Banco 1 (Bank 1):** banco de cilindros que contiene el cilindro #1.
- **Banco 2 (Bank 2):** banco opuesto en motores en V o bóxer.
- **Sensor 1 (Sensor 1):** sensor de oxígeno **antes** del catalizador
  (upstream / aguas arriba).
- **Sensor 2 (Sensor 2):** sensor de oxígeno **después** del catalizador
  (downstream / aguas abajo).

> 📋 **NOTA TÉCNICA:** En motores en línea (L4, L5, L6) solo existe
> Banco 1. Cualquier DTC referido a Banco 2 en estos motores indica
> error de configuración del escáner o codificación incorrecta de la
> ECU.

## 5. Tabla maestra de los 50 códigos P más frecuentes

| # | Código | Descripción SAE J2012 | Causa probable | Solución básica |
|---|---|---|---|---|
| 1 | **P0010** | Circuito del actuador de posición del árbol de levas "A" (Banco 1) | Solenoide VVT abierto/corto, cableado dañado, presión de aceite baja | Verificar resistencia del solenoide VVT (típ. 6–13 Ω), revisar arnés y nivel/calidad de aceite |
| 2 | **P0011** | Posición del árbol de levas "A" — sincronización adelantada (Banco 1) | Solenoide VVT atascado, malla del filtro VVT obstruida, aceite contaminado | Limpiar/reemplazar solenoide y filtro VVT; cambio de aceite con viscosidad correcta |
| 3 | **P0014** | Posición del árbol de levas "B" — sincronización adelantada (Banco 1) | Mismo que P0011 aplicado al árbol de escape | Procedimiento equivalente al P0011 sobre lado escape |
| 4 | **P0016** | Correlación posición cigüeñal/árbol de levas (Banco 1, Sensor A) | Cadena/correa de distribución estirada, tensor desgastado, sensor CMP/CKP defectuoso | Inspeccionar marcas de distribución y holgura de cadena; reemplazar componentes desgastados |
| 5 | **P0030** | Circuito de control del calefactor del sensor HO₂S (Banco 1, Sensor 1) | Calefactor del sensor O₂ abierto, fusible quemado, cableado | Medir resistencia del calefactor (típ. 2–14 Ω); verificar 12 V y masa |
| 6 | **P0101** | Rango/desempeño del sensor MAF | MAF contaminado, fugas de admisión post-MAF, filtro de aire saturado | Limpiar MAF con limpiador específico; revisar mangueras y abrazaderas |
| 7 | **P0102** | Circuito MAF — entrada baja | MAF desconectado, cable de señal cortado, sensor dañado | Verificar conector y tensión de referencia (5 V); medir señal a varios regímenes |
| 8 | **P0103** | Circuito MAF — entrada alta | Cortocircuito a 12 V en señal, MAF defectuoso | Inspeccionar arnés y reemplazar sensor si pruebas eléctricas son correctas |
| 9 | **P0106** | Rango/desempeño del sensor MAP / Presión barométrica | Manguera de vacío rota, MAP obstruido, sensor desviado | Probar MAP con vacuómetro; comparar con presión barométrica al KOEO |
| 10 | **P0107** | Circuito MAP — entrada baja | Sensor sin alimentación de 5 V, cable de señal cortado | Verificar conector y referencia de 5 V desde la ECU |
| 11 | **P0108** | Circuito MAP — entrada alta | Manguera de vacío desconectada, cortocircuito en señal | Reconectar manguera; comprobar continuidad del arnés |
| 12 | **P0112** | Circuito IAT — entrada baja | Cortocircuito a masa en sensor IAT, sensor defectuoso | Medir resistencia del IAT a temperatura ambiente (típ. 2–3 kΩ a 20 °C) |
| 13 | **P0113** | Circuito IAT — entrada alta | Cable abierto, sensor desconectado | Reconectar y verificar continuidad del arnés |
| 14 | **P0117** | Circuito ECT — entrada baja | Cortocircuito a masa en sensor ECT | Medir resistencia ECT (típ. 2.5 kΩ a 20 °C; 300 Ω a 80 °C) |
| 15 | **P0118** | Circuito ECT — entrada alta | Sensor abierto, conector corroído | Reemplazar sensor ECT y limpiar conector |
| 16 | **P0121** | Rango/desempeño del sensor TPS "A" | TPS desgastado, ajuste mecánico incorrecto | Verificar curva de tensión TPS (0.5–4.5 V) en barrido del pedal |
| 17 | **P0128** | Temperatura del refrigerante por debajo de la regulación del termostato | Termostato abierto permanentemente, ECT desviado | Reemplazar termostato; verificar lectura ECT contra termómetro infrarrojo |
| 18 | **P0131** | Circuito sensor O₂ — tensión baja (Banco 1, Sensor 1) | Mezcla pobre, fuga de admisión, fuga de escape pre-sensor, sensor agotado | Inspeccionar fugas; medir tensión del sensor en operación (debe oscilar 0.1–0.9 V) |
| 19 | **P0132** | Circuito sensor O₂ — tensión alta (Banco 1, Sensor 1) | Mezcla rica, inyector con fuga, presión de combustible alta | Verificar presión de combustible y estanqueidad de inyectores |
| 20 | **P0133** | Sensor O₂ — respuesta lenta (Banco 1, Sensor 1) | Sensor envejecido, contaminación por silicona/plomo | Reemplazar sensor O₂ con repuesto original o equivalente certificado |
| 21 | **P0135** | Circuito calefactor sensor O₂ (Banco 1, Sensor 1) | Calefactor abierto, relé defectuoso | Medir resistencia del calefactor; verificar relé de control |
| 22 | **P0141** | Circuito calefactor sensor O₂ (Banco 1, Sensor 2) | Equivalente al P0135 en sensor downstream | Procedimiento eléctrico idéntico al P0135 |
| 23 | **P0171** | Sistema demasiado pobre (Banco 1) | Fuga de admisión, MAF sucio, presión de combustible baja, inyector obstruido | Inspeccionar fugas con humo; medir presión de combustible y LTFT |
| 24 | **P0172** | Sistema demasiado rico (Banco 1) | Filtro de aire obstruido, inyector con fuga, presión de combustible alta | Verificar regulador de presión y estanqueidad de inyectores |
| 25 | **P0174** | Sistema demasiado pobre (Banco 2) | Idem P0171 en banco opuesto (motores V/bóxer) | Mismo procedimiento aplicado al banco 2 |
| 26 | **P0201** | Circuito de inyector abierto — Cilindro 1 | Bobina del inyector abierta, arnés cortado, driver de la ECU dañado | Medir resistencia del inyector (típ. 12–16 Ω); verificar pulso con osciloscopio |
| 27 | **P0300** | Fallo de encendido aleatorio/múltiple en cilindros | Bobinas, bujías, baja compresión, fugas de vacío, combustible deficiente | Lectura de Modo 06; rotar bobinas/bujías; prueba de compresión |
| 28 | **P0301** | Fallo de encendido — Cilindro 1 | Bujía, bobina o inyector del cilindro 1 | Sustituir bujía y rotar bobina al cilindro 2 para confirmar |
| 29 | **P0302** | Fallo de encendido — Cilindro 2 | Idem cilindro 2 | Procedimiento equivalente |
| 30 | **P0303** | Fallo de encendido — Cilindro 3 | Idem cilindro 3 | Procedimiento equivalente |
| 31 | **P0304** | Fallo de encendido — Cilindro 4 | Idem cilindro 4 | Procedimiento equivalente |
| 32 | **P0325** | Circuito sensor de detonación (Knock) 1 — Banco 1 | Sensor knock defectuoso, par de apriete incorrecto, arnés | Verificar par de apriete del sensor (típ. 20–25 Nm) y continuidad |
| 33 | **P0335** | Circuito sensor posición de cigüeñal (CKP) "A" | Sensor CKP dañado, holgura excesiva, rueda fónica con dientes rotos | Medir entrehierro y resistencia del sensor; inspeccionar rueda dentada |
| 34 | **P0340** | Circuito sensor posición de árbol de levas (CMP) "A" | Sensor CMP dañado, distribución desplazada | Verificar señal con osciloscopio sincronizada con CKP |
| 35 | **P0401** | Sistema EGR — flujo insuficiente | Válvula EGR carbonizada, conducto obstruido, sensor DPFE | Limpiar válvula y galerías; verificar sensor de presión diferencial |
| 36 | **P0420** | Eficiencia del catalizador por debajo del umbral (Banco 1) | Catalizador deteriorado, fuga de escape, sensor O₂ posterior degradado | Comparar señales O₂ pre y post-cat; descartar fugas antes del catalizador |
| 37 | **P0430** | Eficiencia del catalizador por debajo del umbral (Banco 2) | Idem P0420 en banco 2 | Procedimiento equivalente al P0420 |
| 38 | **P0440** | Mal funcionamiento general del sistema EVAP | Tapón de combustible flojo o defectuoso, mangueras EVAP, válvula purga | Apretar tapón; prueba de fuga con humo en sistema EVAP |
| 39 | **P0442** | Fuga pequeña detectada en sistema EVAP | Tapón de combustible, sello de mangueras, válvula de ventilación | Reemplazar tapón con norma OEM; prueba de humo |
| 40 | **P0446** | Circuito de control del venteo EVAP | Válvula de venteo (vent valve) atascada, arnés roto | Probar accionamiento bidireccional; reemplazar válvula |
| 41 | **P0455** | Fuga grande detectada en sistema EVAP | Tapón ausente o muy dañado, manguera desconectada | Inspección visual; instalar tapón correcto |
| 42 | **P0456** | Fuga muy pequeña detectada en sistema EVAP | Sello del tapón, microfisuras en mangueras | Prueba de humo a baja presión (<1 psi) |
| 43 | **P0500** | Mal funcionamiento del sensor de velocidad del vehículo (VSS) | Sensor VSS dañado, ABS reportando datos inválidos al PCM | Verificar señal VSS y comunicación con módulo ABS |
| 44 | **P0506** | Sistema de control de ralentí — RPM más bajas de lo esperado | Cuerpo de aceleración sucio, fuga de aire, IAC obstruido | Limpieza de cuerpo de aceleración y reaprendizaje de ralentí |
| 45 | **P0507** | Sistema de control de ralentí — RPM más altas de lo esperado | Fuga de vacío, válvula PCV defectuosa, IAC pegado abierto | Inspeccionar mangueras de vacío y PCV |
| 46 | **P0521** | Rango/desempeño del sensor de presión de aceite del motor | Sensor desviado, presión de aceite real fuera de rango | Verificar presión real con manómetro mecánico antes de reemplazar sensor |
| 47 | **P0606** | Procesador del módulo de control (PCM) | Falla interna del PCM, alimentación inestable | Verificar tensión de batería y masas; reflasheo o reemplazo del PCM |
| 48 | **P0700** | Solicitud de iluminación de MIL desde el módulo TCM | Falla en transmisión — códigos secundarios en TCM | Leer DTC del TCM para identificar la causa raíz |
| 49 | **P0741** | Desempeño del circuito del embrague del convertidor de torque | Solenoide TCC defectuoso, fluido ATF degradado, bomba de aceite | Cambio de ATF y filtro; pruebas de presión hidráulica |
| 50 | **P2002** | Eficiencia del filtro de partículas diésel (DPF) — Banco 1 | DPF saturado, sensor de presión diferencial dañado, regeneraciones fallidas | Forzar regeneración; verificar sensor diferencial; en último caso, sustituir DPF |

## 6. Notas sobre variaciones por fabricante (OEM)

> 📋 **NOTA TÉCNICA — VARIACIONES OEM CONOCIDAS**
>
> - **Toyota / Lexus:** El P0420 frecuentemente se presenta sin pérdida
>   real de eficiencia del catalizador en motores 1MZ-FE y 2GR-FE; se
>   recomienda verificar TSB del fabricante antes de reemplazar el
>   convertidor catalítico.
> - **General Motors:** P0300 y P030x en motores LS pueden originarse
>   por desincronización del sensor CKP que requiere el procedimiento
>   *Crankshaft Position System Variation Learn*.
> - **Volkswagen / Audi (grupo VAG):** P0171/P0174 son típicos por
>   degradación de la PCV y mangueras de admisión secundarias en motores
>   2.0 TSI EA888.
> - **Ford:** El P0171/P0174 en motores Triton y EcoBoost suele
>   asociarse a fuga del múltiple de admisión plástico.
> - **Nissan:** El P0420 y P0430 en motores VQ35DE pueden requerir
>   actualización de software de la ECU antes del reemplazo de
>   componentes.
> - **Hyundai / Kia:** El P0011 en motores Theta II GDI a menudo se
>   asocia con consumo excesivo de aceite cubierto por campañas de
>   garantía extendida del fabricante.

> ⚠️ **ADVERTENCIA**
> Los códigos de la franja **P1xxx** no aparecen en este catálogo
> porque su definición depende exclusivamente del fabricante. Para
> esos códigos consulte la base de datos OEM correspondiente.

## 7. Procedimiento de uso de la tabla

1. Realice el escaneo conforme al procedimiento `docs/como-escanear.md`.
2. Localice el código en la columna **Código** de la tabla.
3. Confirme que el contexto del **Freeze Frame** y los **datos en
   vivo** sean coherentes con la **causa probable** indicada.
4. Aplique la **solución básica** únicamente cuando las pruebas
   eléctricas y mecánicas previas la respalden.
5. Para procedimientos detallados con valores específicos, par de
   apriete, especificaciones eléctricas y diagramas, consulte el
   archivo correspondiente en `fixes/<código>.md`.
6. Borre los DTC con **Modo 04** y ejecute el ciclo de manejo de
   validación. Verifique en **Modo 0A** que no quedan códigos
   permanentes.

> ⚠️ **ADVERTENCIA — TRABAJO EN ALTA PRESIÓN**
> Procedimientos sobre sistemas de inyección directa (GDI),
> common-rail diésel, sistemas EVAP presurizados o transmisiones
> automáticas modernas requieren **equipo de taller especializado**
> (manómetros de alta presión, máquinas de humo, herramientas de
> calibración). No improvise con instrumentos de uso general.

## 8. Bibliografía técnica

1. SAE International. *J2012: Diagnostic Trouble Code Definitions*.
   Warrendale, PA, 2016.
2. ISO. *ISO 15031-6: Road vehicles — Communication between vehicle
   and external equipment for emissions-related diagnostics — Part 6:
   Diagnostic trouble code definitions*. Geneva, 2015.
3. SAE International. *J1979: E/E Diagnostic Test Modes*. Warrendale,
   PA, 2017.
4. U.S. Environmental Protection Agency. *On-Board Diagnostics
   (OBD-II) Regulations Reference Guide*. Washington D.C., 2020.
5. CARB (California Air Resources Board). *OBD II Regulation, Title
   13, California Code of Regulations, Section 1968.2*. Sacramento,
   2022.
6. Bosch GmbH. *Automotive Handbook*. 11.ª edición. Plochingen, 2022.
7. Denton, T. *Advanced Automotive Fault Diagnosis*. 5.ª edición.
   Routledge, 2020.

---

> **Documento elaborado por:** Instituto Nacional de Normalización
> Vehicular (INNV) — Dirección de Documentación Técnica.
> **Próxima revisión obligatoria:** 24 meses a partir de la fecha de
> publicación.
