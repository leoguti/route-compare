# Fase 1: Preparación y Normalización

## Fuentes de datos disponibles

Para el análisis de rutas de transporte público en Trujillo, contamos con las siguientes fuentes de datos:

### 1. Listado Maestro Trujillo v2
Tabla maestra previa que contiene información consolidada de rutas, incluyendo códigos, denominaciones y referencias a archivos KML.

### 2. Datos Trujillo 2024
Conjunto de datos actualizado con información de rutas operativas en 2024, incluyendo códigos y características operacionales.

### 3. Carpeta kml-por-ruta
Colección de archivos KML individuales por ruta, proporcionados por la autoridad de transporte. Cada archivo contiene la geometría del recorrido oficial de una ruta específica.

### 4. Plan Regulador
Documento oficial que establece las rutas autorizadas, códigos oficiales, operadores y características del sistema de transporte público.

## Objetivo de la Fase 1

El objetivo principal de esta fase es construir una **tabla maestra consolidada 2025** que integre información de todas las fuentes disponibles. Esta tabla servirá como base para:

- Normalizar códigos y nomenclaturas entre diferentes fuentes
- Establecer correspondencias entre datos de la autoridad y OpenStreetMap
- Identificar rutas presentes en algunas fuentes pero ausentes en otras
- Facilitar el análisis y comparación en fases posteriores

## Estructura de la tabla maestra 2025

La tabla maestra contendrá las siguientes columnas:

### `codigo_normalizado`
Código de ruta estandarizado para uso interno en el análisis. Aplicará reglas de normalización consistentes (ej: eliminación de espacios, mayúsculas, formato uniforme).

### `codigo_autoridad`
Código oficial de la ruta según documentos de la autoridad de transporte (Plan Regulador, archivos KML).

### `letra`
Letra o identificador alfanumérico principal de la ruta (ej: "A", "B", "12", etc.).

### `denominacion`
Nombre descriptivo o denominación oficial de la ruta (ej: "A - El Golf", "12 Prolongación César Vallejo").

### `tipo`
Categoría o tipo de ruta (ej: "urbana", "interurbana", "alimentadora").

### `archivo_kml`
Nombre del archivo KML correspondiente en la carpeta kml-por-ruta, si existe.

### `codigo_osm`
Código de la ruta según la etiqueta `ref` en OpenStreetMap, si está presente.

### `nombre_osm`
Nombre de la ruta según la etiqueta `name` en OpenStreetMap, si está presente.

### `from_osm`
Punto de origen de la ruta según la etiqueta `from` en OpenStreetMap, si está presente.

### `to_osm`
Punto de destino de la ruta según la etiqueta `to` en OpenStreetMap, si está presente.

### `operador_osm`
Nombre del operador según la etiqueta `operator` en OpenStreetMap, si está presente.

### `observaciones`
Campo de texto libre para notas, discrepancias identificadas, o información adicional relevante para el análisis.

## Proceso de construcción

La tabla maestra se construirá mediante:

1. Extracción de datos de cada fuente
2. Identificación de rutas únicas
3. Cruce de información entre fuentes usando códigos y nombres
4. Normalización de campos
5. Validación de consistencia
6. Documentación de observaciones y discrepancias
