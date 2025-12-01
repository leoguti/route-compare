# route-compare

Este proyecto tiene como finalidad comparar rutas de transporte público entre diferentes fuentes de datos (OpenStreetMap, GTFS, archivos KML de autoridades de transporte, entre otros). El caso de estudio inicial se centra en las rutas de transporte público de Trujillo, Perú, con el objetivo de identificar inconsistencias, evaluar la calidad de los datos y generar insumos técnicos para autoridades de transporte.

## Objetivos

- Comparar códigos de rutas entre diferentes fuentes de datos.
- Calcular métricas de desviación geométrica entre recorridos (por ejemplo, rutas en OSM vs. rutas en KML de la autoridad).
- Generar tablas e insumos para informes técnicos destinados a autoridades de transporte.

## Estructura del proyecto

- **docs/**: Documentación general del proyecto, incluyendo metodologías, notas técnicas y referencias.
- **notebooks/**: Notebooks de Jupyter para análisis exploratorio, visualizaciones y experimentación.
- **scripts/**: Código Python reutilizable para procesamiento de datos, cálculo de métricas y transformaciones.
- **data/raw/**: Datos originales sin procesar (archivos KML, datos exportados de OSM, tablas originales de GTFS, etc.).
- **data/processed/**: Datos procesados y limpios (GeoJSON normalizados, tablas de comparación, métricas calculadas).
- **reports/**: Reportes finales, tablas listas para exportar y resultados del análisis.
