# Diagnóstico Profesional Para Carros

> **Guía técnica oficial de diagnóstico electrónico vehicular OBD-II/CAN Bus**
> **Editor:** Instituto Nacional de Normalización Vehicular (INNV) — Dirección de Documentación Técnica
> **Versión del repositorio:** 1.0
> **Idioma oficial:** Español técnico formal
> **Licencia:** MIT (ver [`LICENSE`](LICENSE))

---

## Tabla de contenido

1. [Objetivo del repositorio](#objetivo-del-repositorio)
2. [Alcance INNV](#alcance-innv)
3. [Audiencia objetivo](#audiencia-objetivo)
4. [Índice de documentos técnicos normativos INNV](#índice-de-documentos-técnicos-normativos-innv)
5. [Estándares y normativas aplicadas](#estándares-y-normativas-aplicadas)
6. [Cómo usar esta guía](#cómo-usar-esta-guía)
7. [Estructura del repositorio](#estructura-del-repositorio)
8. [Política de calidad documental](#política-de-calidad-documental)
9. [Contribuciones](#contribuciones)
10. [Licencia](#licencia)

---

## Objetivo del repositorio

Proveer documentación técnica oficial, **precisa, reproducible y
verificable**, para el diagnóstico electrónico de vehículos livianos
mediante el sistema OBD-II/CAN Bus. La guía cubre desde el procedimiento
de escaneo de un vehículo desconocido, hasta la interpretación de los
códigos de diagnóstico (DTC) de las cuatro categorías estandarizadas
por SAE J2012:

- **P** — *Powertrain* (motor y transmisión)
- **B** — *Body* (carrocería, SRS, confort)
- **C** — *Chassis* (frenos, suspensión, dirección)
- **U** — *Network/CAN* (comunicación entre módulos)

## Alcance INNV

Este repositorio constituye el cuerpo documental de referencia
publicado por el INNV para:

- **Talleres certificados** que requieran un protocolo común de
  diagnóstico auditable.
- **Técnicos automotrices** en formación y en ejercicio que necesiten
  una fuente unificada y trazable de los DTC más frecuentes.
- **Centros de inspección técnico-mecánica y de emisiones** que apliquen
  controles de monitores de Readiness y verificación post-reparación.
- **Peritos y autoridades de tránsito** que deban interpretar reportes
  de escáner como evidencia técnica.
- **Ciudadanos calificados** que deseen comprender el estado de su
  vehículo antes de autorizar reparaciones.

> ⚠️ **Limitación de alcance**
> Este repositorio **no sustituye** los manuales de servicio del
> fabricante (OEM) ni autoriza procedimientos que requieran equipo de
> taller especializado, programación de módulos, codificación de
> inmovilizadores ni manipulación de sistemas de alta tensión (vehículos
> híbridos y eléctricos).

## Audiencia objetivo

| Perfil | Documentos prioritarios |
|---|---|
| Técnico automotriz | Todos los archivos `docs/` y `fixes/` |
| Centro de inspección técnica | [`docs/como-escanear.md`](docs/como-escanear.md), monitores de Readiness |
| Perito vehicular | Catálogos `docs/codigos-*.md` |
| Comprador de vehículo usado | [`docs/como-escanear.md`](docs/como-escanear.md), [`tools/comparativa-scanners.md`](tools/comparativa-scanners.md) |
| Estudiante de mecánica | Toda la guía, en orden secuencial |

## Índice de documentos técnicos normativos INNV

### 📘 Procedimientos

| ID INNV | Documento | Contenido | Estado |
|---|---|---|---|
| INNV-DT-001 | [`docs/como-escanear.md`](docs/como-escanear.md) | Procedimiento normalizado de escaneo OBD-II en 7 etapas (A–G) y 19 pasos | ✅ Publicado |

### 📗 Catálogos de códigos DTC (SAE J2012)

| ID INNV | Documento | Cobertura | Estado |
|---|---|---|---|
| INNV-DT-002 | [`docs/codigos-P.md`](docs/codigos-P.md) | 50 códigos *Powertrain* (motor y transmisión) | ✅ Publicado |
| INNV-DT-003 | [`docs/codigos-B.md`](docs/codigos-B.md) | Códigos *Body* (SRS, confort, carrocería) | 🚧 En preparación |
| INNV-DT-004 | [`docs/codigos-C.md`](docs/codigos-C.md) | Códigos *Chassis* (ABS, ESP, dirección) | 🚧 En preparación |
| INNV-DT-005 | [`docs/codigos-U.md`](docs/codigos-U.md) | Códigos *Network/CAN* (comunicación entre módulos) | 🚧 En preparación |

### 📙 Procedimientos de reparación específicos

Directorio [`fixes/`](fixes/) — un archivo por código DTC común con el
procedimiento de reparación detallado, valores de referencia, par de
apriete y diagramas. **En preparación.**

### 📕 Herramientas y equipo

| Documento | Contenido | Estado |
|---|---|---|
| [`tools/comparativa-scanners.md`](tools/comparativa-scanners.md) | Comparativa técnica de escáneres OBD-II por nivel | 🚧 En preparación |

> 📋 **Nota técnica**
> Los documentos marcados como *"En preparación"* serán publicados en
> *Pull Requests* sucesivos. Cada documento incluye su propio número
> de identificación INNV, índice navegable, marco normativo,
> bibliografía y compromiso de revisión obligatoria a 24 meses.

## Estándares y normativas aplicadas

Toda la documentación de este repositorio se elabora sobre la base de
los estándares vigentes para diagnóstico electrónico vehicular y
emisiones:

### Estándares SAE (Society of Automotive Engineers)

| Norma | Título | Aplicación |
|---|---|---|
| **SAE J1850** | Class B Data Communications Network Interface | Protocolo legado (PWM/VPW) en Ford y GM |
| **SAE J1962** | Diagnostic Connector | Conector físico DLC de 16 pines |
| **SAE J1979** | E/E Diagnostic Test Modes | Modos de servicio OBD-II (`0x01`–`0x0A`) |
| **SAE J2012** | Diagnostic Trouble Code Definitions | Codificación y descripción de DTC (P/B/C/U) |
| **SAE J2284** | High-Speed CAN for Vehicle Applications | Capa física del CAN a 500 kbit/s |

### Estándares ISO (International Organization for Standardization)

| Norma | Título | Aplicación |
|---|---|---|
| **ISO 9141-2** | Road vehicles — Diagnostic systems — CARB requirements | Protocolo serie K-Line |
| **ISO 14229-1** | Unified Diagnostic Services (UDS) | Diagnóstico avanzado sobre CAN |
| **ISO 14230-4** | Keyword Protocol 2000 (KWP2000) | Protocolo legado europeo |
| **ISO 15031-3** | Diagnostic connector and related electrical circuits | Equivalente internacional de SAE J1962 |
| **ISO 15031-5** | Emissions-related diagnostic services | Equivalente internacional de SAE J1979 |
| **ISO 15031-6** | Diagnostic trouble code definitions | Equivalente internacional de SAE J2012 |
| **ISO 15765-4** | Diagnostics on CAN (DoCAN) | Capa de transporte CAN para OBD-II |
| **ISO 3779** | Vehicle identification number (VIN) | Estructura del VIN de 17 caracteres |

### Marco regulatorio referenciado

| Entidad | Documento | Aplicación |
|---|---|---|
| U.S. EPA | *On-Board Diagnostics (OBD-II) Regulations Reference Guide* | Requisitos federales OBD-II |
| CARB (California ARB) | *OBD II Regulation, Title 13 CCR §1968.2* | Requisitos OBD-II más estrictos a nivel mundial |

## Cómo usar esta guía

### Flujo recomendado

```
┌──────────────────────────────────────────────────────────┐
│  1. Lectura previa: README.md (este documento)           │
└─────────────────────────┬────────────────────────────────┘
                          ▼
┌──────────────────────────────────────────────────────────┐
│  2. Procedimiento: docs/como-escanear.md                 │
│     → Escaneo del vehículo y obtención del DTC           │
└─────────────────────────┬────────────────────────────────┘
                          ▼
┌──────────────────────────────────────────────────────────┐
│  3. Identificación del DTC según su letra inicial:       │
│     P → docs/codigos-P.md     C → docs/codigos-C.md      │
│     B → docs/codigos-B.md     U → docs/codigos-U.md      │
└─────────────────────────┬────────────────────────────────┘
                          ▼
┌──────────────────────────────────────────────────────────┐
│  4. Reparación: fixes/<código>.md (procedimiento OEM)    │
└─────────────────────────┬────────────────────────────────┘
                          ▼
┌──────────────────────────────────────────────────────────┐
│  5. Validación: ciclo de manejo + Modo 0A (DTC perm.)    │
└──────────────────────────────────────────────────────────┘
```

### Flujo de emergencia (testigo "Check Engine" encendido)

1. Si el testigo **MIL parpadea**: detener el vehículo de forma segura.
   Indica fallo de encendido severo con riesgo de daño al catalizador.
2. Si el testigo **MIL está fijo**: el vehículo puede operarse hasta el
   taller, pero debe diagnosticarse antes de la próxima inspección.
3. Aplicar [`docs/como-escanear.md`](docs/como-escanear.md) — Etapas A
   a G.

> ⚠️ **Advertencia general de seguridad**
> Antes de cualquier procedimiento eléctrico, verifique que el
> encendido esté en posición OFF. Para vehículos híbridos o eléctricos
> no manipule cableado naranja sin certificación HV. La inhalación de
> gases de escape (CO) es letal.

## Estructura del repositorio

```
.
├── README.md                       ← Punto de entrada (este archivo)
├── LICENSE                         ← Licencia MIT
├── docs/
│   ├── como-escanear.md            ← INNV-DT-001 (procedimiento)
│   ├── codigos-P.md                ← INNV-DT-002 (Powertrain)
│   ├── codigos-B.md                ← INNV-DT-003 (Body)        🚧
│   ├── codigos-C.md                ← INNV-DT-004 (Chassis)     🚧
│   └── codigos-U.md                ← INNV-DT-005 (Network/CAN) 🚧
├── fixes/
│   └── <código>.md                 ← Un archivo por DTC común  🚧
└── tools/
    └── comparativa-scanners.md     ← Comparativa de escáneres  🚧
```

## Política de calidad documental

Todos los documentos publicados en este repositorio cumplen los
siguientes criterios verificables:

1. **Trazabilidad normativa.** Cada definición de DTC se valida
   contra **SAE J2012** / **ISO 15031-6**. No se incluyen códigos
   inventados ni fuera de estándar.
2. **Identificación de variantes OEM.** Cuando un código tiene
   comportamiento o causa específica por fabricante, se indica
   explícitamente en una sección dedicada.
3. **Advertencias de seguridad obligatorias.** Todo procedimiento
   eléctrico, sobre alta presión o sobre alta tensión incluye
   advertencia explícita marcada con `⚠️`.
4. **Bibliografía completa.** Cada documento finaliza con sus
   referencias técnicas numeradas.
5. **Revisión periódica.** Cada documento normativo INNV declara una
   fecha de revisión obligatoria a 24 meses.
6. **Idioma único.** Todo el contenido visible (documentación,
   commits, PRs, ramas, comentarios) se publica en **español técnico
   formal**. Solo se conservan en inglés los identificadores técnicos
   normativos (nombres de protocolos, modos OBD-II, identificadores
   de DTC, PID, descripciones literales SAE).

## Contribuciones

Las contribuciones técnicas son bienvenidas siguiendo este flujo:

1. Abrir un *issue* describiendo el documento o corrección propuesta,
   citando el estándar de referencia (SAE/ISO).
2. Crear una rama con el prefijo correspondiente:
   - `docs/<tema>` para nueva documentación.
   - `fixes/<código>` para procedimientos de reparación.
   - `tools/<tema>` para comparativas de equipo.
3. Cumplir la estructura: portada, objetivo, alcance, procedimiento,
   tabla de códigos relevantes, advertencias, notas técnicas y
   bibliografía.
4. Abrir un *Pull Request* en español, referenciando el ID INNV del
   documento afectado.

## Licencia

Distribuido bajo licencia **MIT**. Consulte el archivo [`LICENSE`](LICENSE)
para los términos completos.

---

> **Aviso legal.** Este repositorio constituye documentación técnica
> de referencia. La aplicación de los procedimientos aquí descritos es
> responsabilidad exclusiva del técnico ejecutor, quien deberá
> contrastarlos con el manual de servicio del fabricante del vehículo
> intervenido. El INNV no se hace responsable por daños derivados del
> uso indebido de la información publicada.
