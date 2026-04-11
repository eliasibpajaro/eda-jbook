# Análisis exploratorio de datos de aceleraciones espectrales en Colombia

Este libro reúne el análisis exploratorio de un conjunto de registros sísmicos usados para estudiar la aceleracion picoefectiva de periodo corto en Colombia y otros paises. El objetivo es presentar, de forma ordenada, el contexto del problema, los fundamentos mínimos para interpretar las variables y la exploración estadística del dataset.

## Propósito del libro

El libro tiene tres propósitos complementarios:

1. **Contextualizar el problema** desde la ingeniería sísmica y la modelación de movimiento del suelo.
2. **Documentar las variables y el enfoque metodológico** con el que se organizó el EDA.
3. **Mostrar la exploración univariada, bivariada y multivariada** como base para etapas posteriores de modelación predictiva.

## Estructura

El contenido se organiza así:

- **Contexto, problema y objetivos**: justifica la pertinencia del estudio y define el alcance.
- **Marco teórico y metodología**: resume conceptos clave de respuesta espectral, RotD50, transformación logarítmica y estructura del análisis.
- **EDA univariado**: describe distribuciones, escalas y comportamiento individual de las variables.
- **EDA bivariado**: explora relaciones entre predictoras y variable objetivo.
- **EDA multivariado**: examina dependencias conjuntas, estructuras espaciales y patrones de correlación.
- **Conclusiones**: sintetiza los principales hallazgos del análisis exploratorio.

## Alcance analítico

Aunque el dataset contiene espectros y metadatos asociados al evento, la estación y el sitio, este libro pone especial atención a la variable `T_0.01_RotD50`, utilizada como respuesta principal en el análisis. En varias secciones también se trabaja con su transformación a escala física, definida como:

```{math}
Sa_{0.01} = \exp\left(T_{0.01,RotD50}\right)
```

## Nota sobre la interpretación

No todas las variables se encuentran almacenadas en escala física original. Algunas fueron transformadas logarítmicamente durante el preprocesamiento, por lo que su interpretación debe hacerse con cuidado y siempre distinguiendo entre la escala almacenada y la escala física original.

```{tableofcontents}
```
