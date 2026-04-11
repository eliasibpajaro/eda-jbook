# Contexto, problema y objetivos

## Contexto sísmico y pertinencia

Colombia se ubica en una región tectónicamente activa, influenciada por la interacción entre varias placas y bloques corticales. En este contexto, la estimación de aceleraciones espectrales es un insumo relevante para el diseño sismo-resistente, la evaluación de amenaza y la construcción de modelos de predicción del movimiento del suelo.

La disponibilidad de bases de datos instrumentales permite complementar los enfoques empíricos tradicionales con análisis basados en datos. En particular, el uso de análisis exploratorio facilita entender la estructura del dataset, identificar patrones dominantes y preparar el terreno para comparaciones posteriores entre modelos predictivos.

## Problema de investigación

La calibración de relaciones predictivas específicas para Colombia enfrenta limitaciones asociadas al tamaño muestral, la heterogeneidad espacial de los registros y la disponibilidad de variables de sitio más detalladas. En consecuencia, antes de construir modelos, es necesario caracterizar rigurosamente el comportamiento de las variables observadas.

Desde esa perspectiva, este libro parte de una pregunta práctica:

> ¿Qué patrones estadísticos, relaciones y escalas dominan la respuesta espectral de periodo corto y sus principales predictoras dentro del conjunto de datos disponible?

## Objetivo general

Caracterizar exploratoriamente un conjunto de registros sísmicos usados para el estudio de aceleraciones espectrales en Colombia, con énfasis en la respuesta `T_0.01_RotD50` y en sus relaciones con magnitud, distancia, profundidad y condición de sitio.

## Objetivos específicos

1. Describir la distribución individual de las variables principales del dataset.
2. Examinar relaciones bivariadas entre la variable objetivo y las predictoras relevantes.
3. Identificar patrones multivariados y espaciales que puedan ser útiles en etapas posteriores de modelación.
4. Documentar de manera clara el significado físico y estadístico de las variables analizadas.

## Variables clave del problema

Las variables de mayor interés en este libro son:

- `Magnitude`: magnitud momento del evento sísmico.
- `Rrup_OpenQuake`: distancia de ruptura.
- `Hypocenter Depth (km)`: profundidad hipocentral.
- `Soil_Class`: clasificación de sitio.
- `T_0.01_RotD50`: respuesta espectral objetivo en escala logarítmica.

## Aporte del EDA

El análisis exploratorio no reemplaza la modelación, pero sí cumple una función decisiva: permite detectar escalas, sesgos, concentraciones, valores atípicos, dependencias y posibles limitaciones del dataset. Por eso, este libro se entiende como una base documental previa a cualquier fase de ajuste o validación predictiva.
