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
