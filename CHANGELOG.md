# CHANGELOG — Diagnóstico Profesional Para Carros

> **Documento normativo INNV-DT-014**
> Registro cronológico de cambios sobre el cuerpo documental de la
> guía. Sigue el espíritu de [Keep a Changelog](https://keepachangelog.com/es-ES/1.1.0/)
> con identificadores INNV-DT.

El versionado del repositorio sigue [Versionado Semántico](https://semver.org/lang/es/):
`MAJOR.MINOR.PATCH`.

- `MAJOR` cambia cuando se reorganiza la estructura de la guía o se
  retiran documentos publicados.
- `MINOR` cambia cuando se publica un documento INNV-DT nuevo.
- `PATCH` cambia cuando se aplican correcciones, aclaraciones o
  actualizaciones que no agregan documentos nuevos.

---

## [No publicado]

### Por publicar

- INNV-DT-015 a INNV-DT-026 — 12 procedimientos `fixes/` adicionales
  del *roadmap* (P0011, P0128, P0401, P0442, P0455, P0606, P0700,
  B0102, C0040, C0710, U0073, U0140).
- Glosario técnico (`docs/glosario.md`) consolidando vocabulario
  OBD-II, redes vehiculares y SRS.

---

## [1.0.0] — 2026-05-26

### Agregado

- **INNV-DT-001** — `docs/como-escanear.md`: procedimiento
  normalizado de escaneo OBD-II en 7 etapas (A–G) y 19 pasos.
- **INNV-DT-002** — `docs/codigos-P.md`: catálogo de los 50 códigos
  Powertrain más frecuentes (SAE J2012).
- **INNV-DT-003** — `docs/codigos-B.md`: catálogo de los 50 códigos
  Body más frecuentes con foco en SRS/airbags.
- **INNV-DT-004** — `docs/codigos-C.md`: catálogo de los 50 códigos
  Chassis más frecuentes (ABS, ESC, EBD, TCS, suspensión, dirección).
- **INNV-DT-005** — `docs/codigos-U.md`: catálogo de los 50 códigos
  Network/CAN más frecuentes con cobertura de HS-CAN, MS-CAN,
  LS-CAN, CAN FD, LIN, FlexRay y Automotive Ethernet.
- **INNV-DT-006** — `tools/comparativa-scanners.md`: comparativa
  técnica de 12 modelos representativos de escáneres OBD-II
  clasificados en 4 niveles de capacidad.
- **INNV-DT-007** — `fixes/P0420.md`: procedimiento de reparación
  para eficiencia del catalizador (Banco 1).
- **INNV-DT-008** — `fixes/P0171.md`: procedimiento de reparación
  para mezcla pobre (Banco 1).
- **INNV-DT-009** — `fixes/P0300-P0304.md`: procedimiento de
  reparación para fallos de encendido aleatorio y por cilindro 1–4.
- **INNV-DT-010** — `fixes/B0100-SRS.md`: procedimiento restringido
  para resistencia baja del lazo squib del airbag conductor.
- **INNV-DT-011** — `fixes/C0035-ABS.md`: procedimiento de reparación
  para sensor de velocidad rueda delantera izquierda.
- **INNV-DT-012** — `fixes/U0100-communication-loss.md`: procedimiento
  de reparación para pérdida de comunicación con el ECM.
- **INNV-DT-013** — `fixes/README.md`: índice del manual de
  reparación rápida.
- **INNV-DT-014** — `CHANGELOG.md`: registro de cambios (este
  documento).
- `README.md` reescrito como punto de entrada normativo con índice
  oficial, tabla de estándares aplicados (SAE/ISO/EPA/CARB), diagrama
  de flujo de uso y política de calidad documental.

### Editorial

- Convención iconográfica de **3 niveles** consolidada en todo el
  cuerpo documental:
  - 🛑 — riesgo inmediato a la vida (alta tensión, dispositivos
    pirotécnicos, gases letales, MIL parpadeante).
  - ⚠️ — advertencia operativa general.
  - ▪ — nota técnica operativa (sustituye al icono `📋` de
    iteraciones tempranas).
- Terminología **ECM** preferida sobre **PCM** en prosa
  hispanoamericana, preservando `ECM/PCM` cuando es descripción
  verbatim SAE J2012 (ej. `U0100`, `U0301`, `U0401`).
- Terminología **ajuste de combustible** preferida sobre **fuel
  trim** en prosa, conservando el término en inglés solo en la
  primera mención de cada documento para trazabilidad.
- Tratamiento gramatical **masculino** consistente para todos los
  acrónimos de módulos electrónicos (`el ECM`, `el TCM`, `el BCM`,
  `el EBCM`, `el SDM`, etc.).

### Cobertura normativa

Estándares y marcos regulatorios referenciados en el cuerpo
documental:

- SAE J1850, J1962, J1979, J2012, J2284, J2399, J2534, J1698-2.
- ISO 9141-2, 11898-1, 11898-2, 14229-1, 14230-4, 15031-3, 15031-5,
  15031-6, 15765-2, 15765-4, 17458 (FlexRay), 17987 (LIN), 26021,
  26262, 3779.
- IEEE 802.3bw (Automotive Ethernet 100BASE-T1).
- EPA 40 CFR Part 51 Subpart S (I/M Programs).
- CARB Title 13 CCR §1968.2 y §2222.
- NHTSA FMVSS 126 (ESC) y FMVSS 208 (occupant protection).

---

## Esquema de identificadores INNV

Todos los documentos normativos llevan un identificador único de la
forma `INNV-DT-NNN` asignado en orden de publicación. La asignación
es **monotónicamente creciente** y los identificadores **no se
reutilizan** aunque un documento se retire.

| ID INNV | Tipo | Ubicación canónica |
|---|---|---|
| 001 | Procedimiento | `docs/como-escanear.md` |
| 002–005 | Catálogo de DTC | `docs/codigos-{P,B,C,U}.md` |
| 006 | Comparativa de equipo | `tools/comparativa-scanners.md` |
| 007–012 | Procedimiento de reparación | `fixes/<código>.md` |
| 013 | Índice del manual de reparación | `fixes/README.md` |
| 014 | Registro de cambios | `CHANGELOG.md` (este archivo) |

## Política de revisión

- **Documentos de catálogo y procedimiento técnico** (DT-001 a
  DT-005, DT-007 en adelante): revisión obligatoria a **24 meses**.
- **Documentos sensibles a evolución de mercado** (DT-006
  comparativa de escáneres): revisión obligatoria a **12 meses**.
- **Documentos meta** (DT-013 índice, DT-014 changelog): se
  actualizan en cada *Pull Request* que toque el cuerpo documental.

---

> **Documento elaborado por:** Instituto Nacional de Normalización
> Vehicular (INNV) — Dirección de Documentación Técnica.
