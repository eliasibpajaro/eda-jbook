# Contexto, problema y objetivos

## Contexto sísmico y pertinencia

La estimación de aceleraciones espectrales es un insumo fundamental en ingeniería sismorresistente, evaluación de amenaza y desarrollo de modelos de predicción del movimiento del suelo. En este contexto, la disponibilidad de registros instrumentales provenientes tanto de Colombia como de bases internacionales como NGA-West permite ampliar el rango de observación y enriquecer el análisis de variables relevantes para la respuesta espectral.

La integración de registros de distintos orígenes incrementa la cobertura en magnitud, distancia, profundidad y condiciones de sitio, pero también introduce heterogeneidad en la muestra. Por ello, antes de avanzar hacia etapas de modelación, resulta necesario caracterizar la estructura del dataset, sus escalas, sus distribuciones y las relaciones principales entre variables.

## Problema de investigación

La construcción de modelos predictivos para respuesta espectral requiere comprender previamente el comportamiento estadístico del conjunto de datos disponible. En un dataset combinado como el utilizado en este libro, esta necesidad es aún más importante, ya que la integración de registros de NGA-West y Colombia puede generar diferencias de escala, composición y variabilidad entre subconjuntos.

Desde esta perspectiva, este libro parte de la siguiente pregunta práctica:

> ¿Qué patrones estadísticos, relaciones y escalas dominan la respuesta espectral de periodo corto y sus principales predictoras dentro de una base integrada de registros sísmicos de NGA-West y Colombia?

## Objetivo general

Caracterizar exploratoriamente una base integrada de registros sísmicos de NGA-West y Colombia, con énfasis en la respuesta `T_0.01_RotD50` y en sus relaciones con magnitud, distancia, profundidad, condición de sitio y origen del registro.

## Objetivos específicos

1. Describir la distribución individual de las variables principales del dataset.
2. Examinar relaciones bivariadas entre la variable objetivo y las predictoras relevantes.
3. Identificar patrones multivariados y espaciales que puedan ser útiles en etapas posteriores de modelación.
4. Documentar de manera clara el significado físico y estadístico de las variables analizadas.
5. Evaluar de forma exploratoria posibles diferencias asociadas al origen de los registros.

## Variables clave del problema

Las variables de mayor interés en este libro son:

- `Magnitude`: magnitud momento del evento sísmico.
- `Rrup_OpenQuake`: distancia de ruptura.
- `Hypocenter Depth (km)`: profundidad hipocentral.
- `Soil_Class`: clasificación simplificada de sitio.
- `origen`: procedencia del registro dentro de la base integrada.
- `T_0.01_RotD50`: respuesta espectral objetivo en escala logarítmica.

## Aporte del EDA

El análisis exploratorio no sustituye la modelación, pero cumple una función esencial: permite identificar escalas, sesgos, concentraciones, valores atípicos, dependencias y posibles limitaciones del dataset. En este sentido, el libro constituye una base documental previa a cualquier fase de ajuste, validación o comparación de modelos predictivos.
