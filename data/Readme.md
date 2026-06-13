# Urban Flow

## Sprint 1

### Objetivo

Aplicar conocimientos de versionado de código, organización, limpieza de datos y uso de pandas para depurar registros históricos de multas por exceso de velocidad.

## Sprint 2

### Objetivo

Aplicar tratamiento de imágenes con OpenCV y procesamiento de texto (NLTK, spaCy, textstat) para determinar qué multas tienen evidencia visual válida.

## Conclusión Sprint 2

El Sprint 2 integró el procesamiento de imágenes con OpenCV y el análisis de texto con NLTK, spaCy y textstat sobre el dataset de multas de Vaalserberg.

### Imágenes (OpenCV)

- Las imágenes se clasificaron en dos grupos: recortes de patentes
  ('plates') y fotografías completas del vehículo ('completes').
- El pipeline de OpenCV (escala de grises → suavizado Gaussian Blur
  → detección de bordes Canny) permitió resaltar contornos relevantes
  para la posterior lectura OCR.
- EasyOCR logró extraer texto de la mayoría de los recortes 'plates',
  aunque con errores en caracteres ambiguos (O/0, I/1, B/8), lo que
  justifica el umbral de matching del 80 por ciento.

### Procesamiento de texto (NLTK, textstat, spaCy)

- La limpieza de ubicaciones con NLTK (tokenización, stop words y
  stemming) y con spaCy (stop words y lematización) produce
  representaciones compactas útiles para búsquedas y agrupamientos.
- Las estadísticas de textstat confirman que las ubicaciones son textos
  cortos, de baja complejidad léxica, coherente con el dominio
  administrativo.

### Relación imagen-dato

- Una fracción de las multas no pudo ser validada visualmente por
  ausencia o mala calidad de imagen, lo que sugiere mejorar la tasa
  de captura de los radares.
- El matching al 80 por ciento es una aproximación razonable; una
  implementación más robusta podría incorporar distancia de edición
  (Levenshtein) o corrección basada en contexto de dominio.

## Sprint 3
### Objetivo
Profesionalizar la solución incorporando persistencia en base de datos relacional con el ORM de SQLAlchemy, control de versiones de datos con DVC y una base de datos vectorial para búsquedas por imagen.

### Introducción y contexto
El sistema creció en volumen y complejidad, por lo que se migra la información procesada en sprints anteriores a una base de datos estructurada y se prepara la búsqueda de vehículos por evidencia visual.

## Conclusión Sprint 3

En el Sprint 3 se profesionalizó la solución de Urban Flow migrando la
información procesada en los sprints anteriores hacia una arquitectura de
persistencia más robusta y escalable.

### Persistencia relacional con SQLAlchemy

- Se diseñó un modelo lógico de entidades (Vehículo, Multa, Radar y
  Evidencia) con programación orientada a objetos, independiente de la
  base de datos.
- Ese modelo se tradujo a un modelo relacional con el ORM de SQLAlchemy,
  definiendo claves primarias, claves foráneas y relaciones uno a muchos
  (vehículo-multa, radar-multa) y uno a uno opcional (multa-evidencia).
- La base de datos transito se creó y pobló automáticamente desde el CSV
  procesado, evitando duplicar vehículos y radares.

### Control de versiones de datos con DVC

- Los archivos binarios (imágenes) se migraron de git a DVC, manteniendo
  el repositorio liviano y versionando los datos en un remote local.

### Búsqueda vectorial con OpenCLIP y ChromaDB

- Se creó la base vectorial patente_vectorial, que asocia el vector de
  cada imagen con el id del vehículo correspondiente.
- La función buscar_patente_imagen permite recuperar, a partir de una
  imagen, el vehículo más probable y todas sus multas, combinando la
  base vectorial con la base relacional.

### Conclusión general

La integración de bases de datos relacional y vectorial demuestra cómo
distintos tipos de almacenamiento se complementan: la relacional aporta
consultas estructuradas y consistentes, mientras que la vectorial habilita
búsquedas por similitud sobre datos no estructurados como las imágenes.
