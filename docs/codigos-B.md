# Catálogo Técnico de Códigos DTC — Categoría B (Body)

> **Documento normativo INNV-DT-003**
> **Versión:** 1.0
> **Estándar de referencia:** SAE J2012 / ISO 15031-6
> **Clasificación:** Catálogo técnico de aplicación general
> **Audiencia:** Talleres certificados, técnicos automotrices, peritos

---

## Índice

1. [Objetivo](#1-objetivo)
2. [Alcance](#2-alcance)
3. [Estructura del código B](#3-estructura-del-código-b)
4. [Subsistemas cubiertos](#4-subsistemas-cubiertos)
5. [Tabla maestra de los 50 códigos B más frecuentes](#5-tabla-maestra-de-los-50-códigos-b-más-frecuentes)
6. [Variaciones por fabricante (OEM) en el rango B1xxx/B2xxx](#6-variaciones-por-fabricante-oem-en-el-rango-b1xxxb2xxx)
7. [Procedimiento de uso de la tabla](#7-procedimiento-de-uso-de-la-tabla)
8. [Bibliografía técnica](#8-bibliografía-técnica)

---

## 1. Objetivo

Proveer un catálogo técnico de referencia rápida con los **50 códigos
DTC de la categoría Body (letra B)** más relevantes para el
diagnóstico de sistemas de carrocería, sujeción suplementaria (SRS),
confort y control eléctrico vehicular, conforme al estándar
**SAE J2012**.

## 2. Alcance

- Aplica a los rangos definidos por SAE como genéricos: **B0xxx** y
  **B3xxx**.
- Incluye una selección representativa de códigos **B1xxx** y **B2xxx**
  ampliamente documentados en bases de datos OEM, marcados
  explícitamente como **específicos del fabricante**.
- La columna *"Solución básica"* es **orientativa**. Toda intervención
  sobre sistemas SRS debe seguir el manual del fabricante.

> ⚠️ **ADVERTENCIA CRÍTICA — SISTEMAS DE SUJECIÓN SUPLEMENTARIA (SRS)**
> Los códigos B0xxx referidos a airbags y pretensores involucran
> dispositivos pirotécnicos energizados a tensiones de hasta 35 V por
> el módulo SDM/SRS. Antes de cualquier intervención:
>
> 1. Desconecte la batería y **espere 10 minutos** mínimo (descarga
>    del condensador de respaldo del SDM).
> 2. Use **únicamente conectores cortocircuitados** al desconectar
>    cargas pirotécnicas.
> 3. **Nunca aplique tensión** a un escudete (squib) con un
>    multímetro convencional: utilice exclusivamente equipo
>    aprobado por el fabricante.
> 4. Las bolsas desplegadas o pretensores activados **no se
>    reutilizan**: deben reemplazarse por componente nuevo OEM.

## 3. Estructura del código B

```
B 0 0 4 2
│ │ │ └─┴── Identificador específico
│ │ └────── Subsistema (ver tabla 4.1)
│ └──────── 0 = genérico SAE | 1 = OEM | 2 = OEM | 3 = SAE reservado
└────────── B = Body (carrocería)
```

> 📋 **NOTA TÉCNICA:** A diferencia de la franja P, donde los códigos
> genéricos (P0xxx) cubren prácticamente todos los subsistemas
> regulados por emisiones, en la franja B la mayor parte de los DTC
> orientados a confort y carrocería (luces, cierre centralizado,
> elevavidrios, climatización, instrumentos) se encuentran en el rango
> **B1xxx/B2xxx**, definidos por cada fabricante. La interoperabilidad
> es por lo tanto **limitada** y siempre debe consultarse la
> documentación OEM.

## 4. Subsistemas cubiertos

### Tabla 4.1 — Asignación funcional aproximada en B0xxx

| Rango | Subsistema |
|---|---|
| B0001–B0099 | Despliegue de bolsas de aire (frontal, lateral, cortina, rodilla) |
| B0100–B0199 | Monitoreo de continuidad de circuitos pirotécnicos (squib loops) |
| B0200–B0299 | Sensores de impacto y aceleración |
| B0300–B0399 | Cinturones de seguridad y pretensores |
| B0400–B0499 | Sensores de ocupación (PPS, OCS) |
| B0500–B0699 | Confort eléctrico y HVAC |
| B0700–B0999 | Subsistemas misceláneos del cuerpo |

## 5. Tabla maestra de los 50 códigos B más frecuentes

> **Leyenda de origen:**
> 🅢 = Genérico SAE J2012 (B0xxx / B3xxx) · 🅞 = Específico OEM (B1xxx / B2xxx)

| # | Código | Origen | Descripción | Causa probable | Solución básica |
|---|---|---|---|---|---|
| 1 | **B0001** | 🅢 | Control de despliegue de bolsa frontal del conductor — Etapa 1 | Falla del módulo SDM, arnés del squib, conector amarillo bajo asiento | Diagnóstico SRS con escáner OEM; nunca medir resistencia con multímetro convencional |
| 2 | **B0002** | 🅢 | Control de despliegue de bolsa frontal del conductor — Etapa 2 | Idem B0001 sobre etapa 2 | Idem B0001 |
| 3 | **B0010** | 🅢 | Control de despliegue de bolsa frontal del pasajero — Etapa 1 | Conector amarillo bajo asiento del pasajero, módulo PPS | Verificar conector y revisar PPS si aplica |
| 4 | **B0011** | 🅢 | Control de despliegue de bolsa frontal del pasajero — Etapa 2 | Idem B0010 sobre etapa 2 | Idem B0010 |
| 5 | **B0020** | 🅢 | Control de despliegue lateral izquierdo — Etapa 1 | Squib de bolsa lateral en respaldo o pilar B izquierdo | Verificar conector amarillo del asiento conductor |
| 6 | **B0024** | 🅢 | Control de despliegue lateral izquierdo — Etapa 2 | Idem B0020 sobre etapa 2 | Idem B0020 |
| 7 | **B0028** | 🅢 | Control de despliegue lateral derecho — Etapa 1 | Squib lateral derecho | Verificar conector amarillo del asiento pasajero |
| 8 | **B0050** | 🅢 | Control de despliegue del pretensor del conductor | Pretensor de cinturón conductor activado o circuito abierto | Reemplazar pretensor si hubo evento; verificar continuidad con escáner SRS |
| 9 | **B0053** | 🅢 | Control de despliegue del pretensor del pasajero | Pretensor pasajero | Idem B0050 sobre lado pasajero |
| 10 | **B0057** | 🅢 | Control de despliegue del pretensor lateral del conductor | Pretensor lateral si equipado | Verificar conector y squib lateral |
| 11 | **B0064** | 🅢 | Control de despliegue del pretensor lateral del pasajero | Pretensor lateral pasajero | Idem B0057 |
| 12 | **B0070** | 🅢 | Control de despliegue lateral trasero izquierdo — Etapa 1 | Squib en pilar C izquierdo o asiento trasero | Inspección del pilar C y conectores |
| 13 | **B0078** | 🅢 | Control de despliegue lateral trasero derecho — Etapa 1 | Squib en pilar C derecho o asiento trasero | Inspección del pilar C y conectores |
| 14 | **B0081** | 🅢 | Control de despliegue lateral trasero derecho — Etapa 2 | Idem B0078 sobre etapa 2 | Idem B0078 |
| 15 | **B0092** | 🅢 | Control de despliegue de bolsa de rodilla del conductor | Squib de airbag de rodilla bajo columna de dirección | Verificar conector amarillo bajo tablero |
| 16 | **B0095** | 🅢 | Control de despliegue de bolsa de rodilla del pasajero | Squib de airbag de rodilla del pasajero | Verificar conector amarillo en guantera |
| 17 | **B0100** | 🅢 | Resistencia baja del lazo squib de bolsa frontal del conductor | Cortocircuito en arnés, conector reloj (clockspring) dañado | Reemplazar clockspring; nunca medir con multímetro |
| 18 | **B0101** | 🅢 | Resistencia alta del lazo squib de bolsa frontal del conductor | Conector flojo, oxidación, clockspring desgastado | Limpiar/reemplazar conector; reemplazar clockspring si persiste |
| 19 | **B0102** | 🅢 | Lazo squib de bolsa frontal del conductor abierto | Cable cortado en clockspring, squib desconectado | Reemplazar clockspring |
| 20 | **B0103** | 🅢 | Lazo squib de bolsa frontal del conductor en cortocircuito a batería | Daño físico en arnés bajo columna de dirección | Reparar arnés conforme al diagrama OEM |
| 21 | **B0104** | 🅢 | Lazo squib de bolsa frontal del conductor en cortocircuito a masa | Pellizco de arnés contra estructura metálica | Inspeccionar y reparar arnés |
| 22 | **B0105** | 🅢 | Resistencia baja del lazo squib — etapa 2 conductor | Idem B0100 sobre etapa 2 | Idem B0100 |
| 23 | **B0110** | 🅢 | Resistencia baja del lazo squib de bolsa frontal del pasajero | Conector amarillo bajo asiento, arnés | Limpiar conector y verificar |
| 24 | **B0114** | 🅢 | Lazo squib de bolsa frontal del pasajero en cortocircuito a batería | Daño físico en arnés del pasajero | Reparar arnés conforme al diagrama OEM |
| 25 | **B0124** | 🅢 | Lazo de despliegue de bolsa lateral izquierda | Squib lateral o conector | Verificar conector del asiento conductor |
| 26 | **B0131** | 🅢 | Lazo squib lateral del conductor abierto | Cable cortado en respaldo del asiento | Inspeccionar arnés del asiento conductor |
| 27 | **B0151** | 🅢 | Lazo del pretensor frontal del pasajero | Conector del pretensor o cable | Verificar conector del pretensor pasajero |
| 28 | **B0158** | 🅢 | Lazo squib del pretensor del conductor abierto | Cable del pretensor cortado | Inspeccionar arnés del pretensor conductor |
| 29 | **B0162** | 🅢 | Sensor de impacto frontal 1 — desempeño | Sensor frontal flojo, golpe leve previo, conector | Verificar par de apriete del sensor; sustituir si hubo impacto |
| 30 | **B0164** | 🅢 | Circuito del sensor de temperatura interna del climatizador | Sensor in-car (con aspirador) sucio u obstruido | Limpiar el aspirador del sensor; verificar señal |
| 31 | **B0223** | 🅢 | Sensor lateral de impacto izquierdo | Sensor en pilar B izquierdo | Verificar conector y par de apriete |
| 32 | **B0228** | 🅢 | Sensor lateral de impacto derecho | Sensor en pilar B derecho | Verificar conector y par de apriete |
| 33 | **B0418** | 🅢 | Circuito de sensor de presencia del pasajero (PPS) | Sensor de peso del asiento pasajero, conector bajo asiento | Recalibrar sistema OCS según procedimiento OEM |
| 34 | **B0533** | 🅢 | Circuito del eyector de combustible (corte por colisión) | Sensor inercial post-impacto | Reset del interruptor inercial; verificar instalación correcta |
| 35 | **B0790** | 🅢 | Falla interna del módulo SDM/SRS | Módulo SDM dañado por sobretensión o evento | Reemplazo del módulo y reprogramación con escáner OEM |
| 36 | **B1000** | 🅞 | Falla interna del módulo de control (variadas marcas) | ECU/BCM con falla interna | Verificar tensión y masa; reflasheo o reemplazo según marca |
| 37 | **B1001** | 🅞 | Configuración del módulo no válida (Ford, otros) | BCM sin codificar tras reemplazo | Configurar el módulo con escáner OEM (PMI/AsBuilt) |
| 38 | **B1318** | 🅞 | Tensión de batería baja (Ford y similares) | Batería deteriorada, alternador, masa pobre | Probar batería y alternador; medir caída en masas |
| 39 | **B1342** | 🅞 | Falla interna del PCM/BCM (Ford común) | Módulo dañado | Reemplazo y programación |
| 40 | **B1352** | 🅞 | Circuito de encendido en accesorios abierto (Ford) | Switch de ignición o cableado | Verificar switch y fusibles |
| 41 | **B1602** | 🅞 | PATS — formato de transponder no válido (Ford) | Llave no programada o transponder dañado | Reprogramar llave conforme al procedimiento PATS |
| 42 | **B1681** | 🅞 | Falla del switch on/off del climatizador | Switch HVAC dañado | Reemplazar control de clima |
| 43 | **B2103** | 🅞 | Antena no conectada (PASS-Lock GM) | Cable de antena del inmovilizador desconectado | Verificar conexión bajo cilindro de ignición |
| 44 | **B2206** | 🅞 | Tensión de batería fuera de rango (varias marcas) | Sobretensión del alternador, regulador de voltaje | Probar regulador del alternador |
| 45 | **B2290** | 🅞 | Botón del panel de clima atascado | Botón pegado o tarjeta del control HVAC | Reemplazar control de clima |
| 46 | **B2340** | 🅞 | Switch antiviolación del cilindro de la puerta | Cilindro forzado o switch defectuoso | Inspeccionar cilindro; reemplazar switch |
| 47 | **B2477** | 🅞 | Fallo de configuración del módulo (Ford) | Configuración AsBuilt corrupta o no instalada | Reescribir AsBuilt con FDRS/IDS |
| 48 | **B2603** | 🅞 | Sensor del airbag del conductor dañado | Sensor SRS dañado físicamente | Reemplazar sensor; revisar arnés |
| 49 | **B2752** | 🅞 | Falla del circuito del testigo de airbag | Bombilla del cluster, driver del cluster, cableado | Verificar cluster y testigo; reemplazar si aplica |
| 50 | **B2960** | 🅞 | Datos de seguridad incorrectos (sistema antirrobo) | Llave incorrecta, módulo de seguridad desincronizado | Resincronizar inmovilizador con escáner OEM |

## 6. Variaciones por fabricante (OEM) en el rango B1xxx/B2xxx

> 📋 **NOTA TÉCNICA — INTERPRETACIÓN OEM**
>
> A diferencia de los rangos B0xxx/B3xxx, los códigos **B1xxx** y
> **B2xxx** son específicos del fabricante. Una misma combinación
> (por ejemplo, **B1318**) puede tener significados distintos según
> la marca:
>
> - **Ford / Lincoln / Mercury:** B1318 = *Battery Voltage Low*.
> - **General Motors:** códigos B1xxx propios de PASS-Lock, climate,
>   y BCM. Consultar bases de datos GMSI.
> - **Stellantis (Chrysler/Dodge/Jeep/RAM):** uso intensivo del rango
>   B1xxx para confort y SkREEM/SKIM (inmovilizador).
> - **Toyota / Lexus:** códigos B1xxx para SRS y aire acondicionado;
>   estructura propia documentada en Techstream.
> - **Honda / Acura:** uso de B1xxx para SRS, HFL y MICU (Multiplex
>   Integrated Control Unit).
> - **Nissan / Infiniti:** códigos B1xxx para BCM y módulo IPDM E/R.
> - **Hyundai / Kia:** códigos B1xxx documentados en GDS (Global
>   Diagnostic System).
> - **Grupo VAG (VW, Audi, Seat, Skoda):** estructura propia
>   *5-digit DTC* mapeada a B-codes vía SAE; preferir VCDS/ODIS para
>   diagnóstico literal.
> - **BMW / MINI:** sistema *FastFault* propio; equivalencias a
>   B-codes solo orientativas.
> - **Mercedes-Benz:** sistema XENTRY con códigos propios; mapear a
>   SAE únicamente con escáner certificado.

> ⚠️ **ADVERTENCIA**
> Nunca interprete un código B1xxx o B2xxx genéricamente. Use siempre
> la base de datos del fabricante específico. La interpretación
> incorrecta de un código SRS puede llevar al despliegue accidental
> de bolsas de aire con riesgo de lesión grave.

## 7. Procedimiento de uso de la tabla

1. Realice el escaneo conforme a [`docs/como-escanear.md`](como-escanear.md).
2. Si el código es **B0xxx** o **B3xxx**, búsquelo en la tabla
   maestra de la sección 5.
3. Si el código es **B1xxx** o **B2xxx**:
   - Identifique la marca y modelo exacto del vehículo.
   - Consulte la base de datos OEM correspondiente.
   - Use la tabla solo como referencia preliminar, nunca como fuente
     definitiva.
4. **Antes de cualquier intervención sobre el SRS:** desconecte la
   batería y espere 10 minutos.
5. Aplique pruebas eléctricas únicamente con el escáner SRS — nunca
   con multímetro sobre conectores pirotécnicos vivos.
6. Después de la reparación, ejecute el procedimiento de borrado y
   verificación con escáner OEM.
7. Verifique con un ciclo KOEO + KOER que el testigo SRS se apaga en
   menos de 6 segundos.

> ⚠️ **ADVERTENCIA — REPARACIONES NO AUTORIZADAS**
> Los siguientes procedimientos requieren equipo de taller
> especializado y **no deben realizarse por usuario general**:
>
> - Reemplazo de módulo SDM/SRS y configuración AsBuilt.
> - Codificación de pretensores.
> - Reprogramación de inmovilizadores PATS/SkREEM/SKIM.
> - Reset del sistema OCS (Occupant Classification System).
> - Calibración de sensores de impacto frontales y laterales.

## 8. Bibliografía técnica

1. SAE International. *J2012: Diagnostic Trouble Code Definitions*.
   Warrendale, PA, 2016.
2. ISO. *ISO 15031-6: Road vehicles — Communication between vehicle
   and external equipment for emissions-related diagnostics — Part 6:
   Diagnostic trouble code definitions*. Geneva, 2015.
3. ISO. *ISO 26021: Road vehicles — End-of-life activation of
   on-board pyrotechnic devices*. Geneva, 2008.
4. NHTSA. *Federal Motor Vehicle Safety Standard No. 208 — Occupant
   Crash Protection*. Washington D.C., 2022.
5. Bosch GmbH. *Safety, Comfort and Convenience Systems*. 4.ª edición.
   Plochingen, 2021.
6. SAE International. *J1698-2: Vehicle Event Data Recorder (EDR) —
   Output Data Definition*. Warrendale, PA, 2020.

---

> **Documento elaborado por:** Instituto Nacional de Normalización
> Vehicular (INNV) — Dirección de Documentación Técnica.
> **Próxima revisión obligatoria:** 24 meses a partir de la fecha de
> publicación.
