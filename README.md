# Análisis de reproducciones musicales con Pandas

Proyecto del Sprint 3 de Ciencia de Datos de TripleTen, realizado como ejercicio
formativo por Jesús Alejandro Gómez Pérez con práctica guiada.

## Pregunta del proyecto

¿Cómo varía el número de reproducciones registradas entre Springfield y
Shelbyville, y entre los lunes y los viernes?

## Competencias aplicadas

Python y Pandas: inspección de datos, normalización de encabezados, tratamiento
de ausentes de texto, duplicados explícitos e implícitos, filtros booleanos,
agrupación y funciones reutilizables.

## Preparación y análisis

1. Leer 65,079 registros de reproducciones.
2. Homogeneizar encabezados y renombrar `userid` a `user_id`.
3. Completar ausentes de `track`, `artist` y `genre` con la categoría `unknown`,
   conservando los eventos aunque falte ese metadato.
4. Eliminar 3,826 duplicados exactos, bajo el criterio del ejercicio.
5. Unificar `hip`, `hop` y `hip-hop` como `hiphop`.
6. Comparar conteos por ciudad y día mediante `groupby()` y la función
   `number_tracks(day, city)`.

## Resultados

| Ciudad | Lunes | Viernes |
|---|---:|---:|
| Springfield | 15,740 | 15,945 |
| Shelbyville | 5,614 | 5,895 |

Springfield tiene más reproducciones registradas en ambos días; el viernes
supera ligeramente al lunes en las dos ciudades.

Los conteos describen eventos del dataset. No son tasas por usuario y no
demuestran diferencias estadísticas, preferencias individuales ni causalidad.

## Ejecutar

```powershell
py -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
```

Abre `music_streaming_analysis.ipynb` en VS Code, elige `.venv` como kernel y
ejecuta las celdas de arriba abajo desde esta carpeta. El notebook lee el CSV
local incluido; conserva la ruta `/datasets/` como alternativa educativa.

## Edición de portafolio

La versión original incluye una aprobación y una sugerencia opcional sobre
presentar la conclusión en Markdown. En esta copia de portafolio:

- Se adaptó la ruta del archivo para la ejecución local.
- Dos operaciones sobre Series usan asignación explícita en lugar de
  `inplace=True`, para evitar depender del comportamiento de asignación
  encadenada de Pandas.
- La conclusión del estudiante se presenta en Markdown y describe diferencias
  de conteos sin afirmar significación estadística.
- Los comentarios de revisión originales se mantienen intactos. La aprobación
  corresponde a la versión original; esta adaptación no tiene una nueva revisión.

## Fuente

[music_project_en.csv — material de práctica de TripleTen](https://practicum-content.s3.us-west-1.amazonaws.com/datasets/music_project_en.csv).
Springfield y Shelbyville corresponden al caso educativo presentado.
