# Laboratorio S06 · Del modelo E/R al esquema relacional

**Seminario de Análisis y Extracción de Conocimientos de Bases de Datos** · Clave 10645 · Grupo 1002 / 1002A · Ciclo 2027-1
**Sesión:** miércoles 23 de septiembre de 2026 · 10:30 – 12:00 · Laboratorio A14-14113
**Unidad 2.3 — Diseño lógico** (lo vimos el viernes 18)

---

El jueves pasado cada equipo construyó el diagrama E/R de su proyecto. El viernes vimos las reglas para transformar ese diagrama en tablas. Hoy juntamos las dos cosas: vamos a pasar su E/R a un esquema relacional, y otro equipo lo va a revisar antes de que mañana lo conviertan en DDL.

Hoy no se escribe `CREATE TABLE`. Eso es mañana. Hoy lo que me importa es que cada llave foránea esté donde debe estar y que sepan **por qué** está ahí. Si mañana llegan con el esquema bien pensado, el DDL sale en media hora; si llegan con dudas, se les va la sesión corrigiendo tablas.

## Qué vamos a hacer

| Hora | Actividad | Dónde |
|---|---|---|
| 10:30 – 10:40 | Fork, Codespace, rama de trabajo y carpeta del equipo | [`guias/flujo-git.md`](guias/flujo-git.md) |
| 10:40 – 11:00 | Ejercicio de calentamiento: caso Gimnasio | [`ejercicio/caso-gimnasio.md`](ejercicio/caso-gimnasio.md) |
| 11:00 – 11:08 | Puesta en común (yo pregunto, ustedes defienden) | — |
| 11:08 – 11:30 | Esquema relacional de **su** proyecto y apertura del Pull Request | `equipos/equipo-XX/esquema-relacional.md` |
| 11:30 – 11:48 | Revisión cruzada entre equipos, en el Pull Request | [`guias/revision-cruzada.md`](guias/revision-cruzada.md) |
| 11:48 – 12:00 | Atender comentarios, llenar el documento de Google y cierre | Documento de Google del equipo |

## Qué entregan hoy

1. **Un Pull Request** a este repositorio con la carpeta `equipos/equipo-XX/` completa (los dos archivos de la plantilla).
2. **El documento de Google del equipo** con las respuestas, el enlace a su fork y el enlace a su Pull Request.

Tienen hasta **mañana jueves 24 a las 10:00** para terminar ambas cosas, porque mañana arrancamos directamente con el DDL sobre este esquema.

## Reglas del trabajo en equipo

- **Un fork por equipo.** Lo hace un integrante y agrega a los otros dos como colaboradores de su fork. Así los tres hacen commits sobre el mismo repositorio.
- **Los tres hacen commits.** Recuerden que el historial de commits es su evidencia de contribución individual. Si uno solo escribe todo, los otros dos no tienen cómo demostrar que participaron.
- **Solo tocan su carpeta.** Nadie modifica archivos fuera de `equipos/equipo-XX/`. Así ningún Pull Request choca con el de otro equipo.
- **IA:** pueden usarla, declarándolo en la última sección del documento de Google. Eres responsable de todo lo que entregas: si no puedes explicar por qué una llave foránea está en una tabla, no la pusiste tú.

## Estructura del repositorio

```
.
├── README.md                     ← estás aquí
├── guias/
│   ├── flujo-git.md              ← fork, clone, rama, commit, Pull Request
│   ├── notacion.md               ← cómo escribir el esquema relacional
│   └── revision-cruzada.md       ← quién revisa a quién y qué preguntar
├── ejercicio/
│   └── caso-gimnasio.md          ← ejercicio de calentamiento
├── equipos/
│   └── _plantilla/               ← cópienla como equipo-XX (no la editen)
│       ├── gimnasio.md
│       └── esquema-relacional.md
└── .github/
    └── pull_request_template.md
```
