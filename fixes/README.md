# Manual de Reparación Rápida — Procedimientos `fixes/`

> **Documento normativo INNV-DT-013**
> **Versión:** 1.0
> **Clasificación:** Índice del manual de reparación rápida
> **Audiencia:** Talleres certificados, técnicos automotrices, peritos

---

## Propósito

Este directorio contiene **procedimientos de reparación específicos
por DTC**, cada uno autocontenido y referenciable individualmente.
Cada archivo cumple la estructura INNV:

1. Identificación del DTC (código, sistema, frecuencia, síntomas).
2. Advertencias de seguridad.
3. Equipo y herramientas requeridas.
4. Causas probables ordenadas por frecuencia.
5. Procedimiento de diagnóstico paso a paso.
6. Procedimiento de reparación por caso.
7. Validación post-reparación.
8. Cuándo escalar a equipo especializado.
9. Bibliografía técnica.

## Cómo usar este manual

1. Realice el escaneo conforme a [`docs/como-escanear.md`](../docs/como-escanear.md).
2. Identifique el DTC reportado y consulte el catálogo correspondiente
   en [`docs/codigos-P.md`](../docs/codigos-P.md),
   [`docs/codigos-B.md`](../docs/codigos-B.md),
   [`docs/codigos-C.md`](../docs/codigos-C.md) o
   [`docs/codigos-U.md`](../docs/codigos-U.md).
3. Si el código está cubierto por un archivo en este directorio,
   sígalo como **complemento detallado** del catálogo.
4. Si no existe archivo específico, use el catálogo como referencia y
   consulte el manual de servicio del fabricante.

## Índice de procedimientos publicados

### Categoría P — Powertrain

| ID INNV | Archivo | DTC cubiertos | Tipo de falla |
|---|---|---|---|
| INNV-DT-007 | [`P0420.md`](P0420.md) | `P0420` | Eficiencia del catalizador (Banco 1) |
| INNV-DT-008 | [`P0171.md`](P0171.md) | `P0171` | Sistema demasiado pobre (Banco 1) |
| INNV-DT-009 | [`P0300-P0304.md`](P0300-P0304.md) | `P0300`, `P0301`, `P0302`, `P0303`, `P0304` | Fallos de encendido aleatorio y por cilindro |

### Categoría B — Body

| ID INNV | Archivo | DTC cubiertos | Tipo de falla |
|---|---|---|---|
| INNV-DT-010 | [`B0100-SRS.md`](B0100-SRS.md) | `B0100` | Resistencia baja del lazo squib del airbag conductor (SRS) |

### Categoría C — Chassis

| ID INNV | Archivo | DTC cubiertos | Tipo de falla |
|---|---|---|---|
| INNV-DT-011 | [`C0035-ABS.md`](C0035-ABS.md) | `C0035` | Sensor de velocidad de rueda delantera izquierda |

### Categoría U — Network/CAN

| ID INNV | Archivo | DTC cubiertos | Tipo de falla |
|---|---|---|---|
| INNV-DT-012 | [`U0100-communication-loss.md`](U0100-communication-loss.md) | `U0100` | Pérdida de comunicación con ECM/PCM "A" |

## Procedimientos previstos en próximas iteraciones

Esta es la primera entrega del manual. Procedimientos previstos para
publicaciones siguientes (no exhaustivo):

- `P0011.md` — VVT sincronización adelantada (Banco 1).
- `P0128.md` — Termostato por debajo de regulación.
- `P0401.md` — EGR flujo insuficiente.
- `P0442.md` — Fuga pequeña EVAP.
- `P0455.md` — Fuga grande EVAP.
- `P0606.md` — Procesador del ECM.
- `P0700.md` — Solicitud de MIL desde TCM.
- `B0102.md` — Squib loop abierto.
- `C0040.md` — Sensor velocidad delantera derecha.
- `C0710.md` — Sensor de ángulo de dirección.
- `U0073.md` — Bus de control en estado *Bus Off*.
- `U0140.md` — Pérdida de comunicación con BCM.

> ▪ **Cómo proponer un nuevo procedimiento**
> Abra un *issue* en el repositorio indicando el DTC y aportando
> una experiencia documentada. Los procedimientos del manual se
> validan con bibliografía técnica (SAE/ISO/Bosch/OEM TSB) antes de
> publicarse.

## Convenciones

- 🅢 = código genérico SAE J2012.
- 🅞 = código específico OEM (B1xxx, B2xxx, C1xxx, C2xxx, U1xxx, U2xxx, P1xxx, P3xxx).
- 🛑 = riesgo inmediato a la vida (alta tensión, dispositivos pirotécnicos, gases letales, MIL parpadeante).
- ⚠️ = advertencia operativa general.
- ▪ = nota técnica operativa.

## Limitaciones del manual

> ⚠️ **AVISO**
> Estos procedimientos son **referencia técnica general**. La
> intervención efectiva en cada vehículo debe contrastarse con el
> manual de servicio específico del fabricante (modelo, año, motor,
> mercado). El INNV no se hace responsable por daños derivados del
> uso indebido del manual.

## Bibliografía consolidada

Las referencias completas se mantienen al cierre de cada
procedimiento individual. Las fuentes recurrentes son:

- SAE J2012, J1979, J1962, J2534.
- ISO 15031-3, 15031-5, 15031-6, 11898-1, 14229-1, 15765-4, 26021,
  26262.
- CARB Title 13 CCR §1968.2 y §2222.
- EPA *On-Board Diagnostics Reference Guide*.
- Bosch GmbH (manuales especializados por subsistema).
- TSB (*Technical Service Bulletins*) de cada fabricante.

---

> **Documento elaborado por:** Instituto Nacional de Normalización
> Vehicular (INNV) — Dirección de Documentación Técnica.
> **Próxima revisión obligatoria:** 12 meses (mantener sincronizado
> con el catálogo de procedimientos publicados).
