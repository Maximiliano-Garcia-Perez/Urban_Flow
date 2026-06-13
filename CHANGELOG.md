# CHANGELOG
## Sprint 1 - Día 1 (Ejercicio 01)
- Clonación del repositorio remoto desde GitHub.
- Creación de rama Sprint_1.
- Creación de estructura de directorios del proyecto.
- Creación de README.md y CHANGELOG.md.

## Sprint 1 - Día 2 (Ejercicio 02)
- Descarga del dataset raw desde GitHub.
- Análisis exploratorio: tipos de datos y valores nulos.

## Sprint 1 - Día 3 (Ejercicio 03)
- Normalización de fechas, horas, ubicaciones y patentes.
- Eliminación de nulos y outliers.
- Creación de columnas exceso_velocidad_real y exceso_velocidad.
- Dataset limpio guardado en data/interim/.

## Sprint 1 - Día 4 (Ejercicio 04)
- Implementación de la clase FineAnalyzer.
- Métodos: ranking_patentes, ranking_horarios, exceso_promedio,
  exceso_real_promedio, multas_por_ubicacion.

## Sprint 1 - Día 5 (Ejercicio 05)
- Gráficos: top 10 patentes, torta por hora, barras por mes,
  líneas por hora 00:00 y por fecha 1932-01-01.

## Sprint 1 - Día 6 (Ejercicio 06)
- Análisis de porcentajes de registros con fecha y hora inválida.

## Sprint 2 - Día 1 (Ejercicio 01)
- Creación de rama Sprint_2 a partir de Sprint_1.
- Descarga y descompresión del dataset de imágenes.

## Sprint 2 - Día 2 (Ejercicio 02)
- Listado de imágenes con tamaño en kb.
- Clasificación en grupos 'plates' y 'completes'.
- Creación y guardado del diccionario group_images.
- Función reutilizable mostrar_imagenes_grid.

## Sprint 2 - Día 3 (Ejercicio 03)
- Conversión a escala de grises con OpenCV.
- Suavizado Gaussian Blur.
- Detección de bordes Canny.
- Imágenes guardadas en data/interim/imgs/.

## Sprint 2 - Día 4 (Ejercicio 04)
- Extracción de patentes con EasyOCR.
- Limpieza de ubicaciones con NLTK (stop words + stem).
- Estadísticas de texto con textstat.
- Limpieza de ubicaciones con spaCy (stop words + lemma).
- Matching patentes imagen/dataset (umbral 80%).
- Dataset final guardado en data/processed/.
<<<<<<< HEAD
=======

## Sprint 2 - Día 5 (Ejercicio 05)
- Métricas: multas con/sin imagen, imágenes sin match,
  multas pendientes y pendientes con imagen.

## Sprint 2 - Día 6 (Ejercicio 06)
- Conclusión Sprint 2 escrita en README.md.
>>>>>>> e0ee7eb2c3d9084472d69733bcbc6fbf168015c4

## Sprint 2 - Día 4 (Ejercicio 04)
- Extracción de patentes con EasyOCR.
- Limpieza de ubicaciones con NLTK (stop words + stem).
- Estadísticas de texto con textstat.
- Limpieza de ubicaciones con spaCy (stop words + lemma).
- Matching patentes imagen/dataset (umbral 80%).
- Dataset final guardado en data/processed/.

## Sprint 3 - Día 1 (Ejercicio 01)
- Creación de rama Sprint_3 a partir de Sprint_2.
- Verificación de acceso a los datasets generados.

## Sprint 3 - Día 2 (Ejercicio 02)
- Inicialización de DVC y remote local en /content/remote_dvc.
- Migración de archivos binarios (imágenes y ZIP) de git a DVC.

## Sprint 3 - Día 3 (Ejercicio 03)
- Diseño del modelo lógico de entidades (POO), independiente de
  la base de datos.

## Sprint 3 - Día 4 (Ejercicio 04)
- Implementación de la función procesar_fila_csv.

## Sprint 3 - Día 5 (Ejercicio 05)
- Diseño del modelo relacional con el ORM de SQLAlchemy.
