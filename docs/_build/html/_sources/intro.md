# Análisis exploratorio de datos de aceleraciones espectrales: NGA-West y Colombia

Este libro presenta el análisis exploratorio de una base integrada de registros sísmicos provenientes de NGA-West y de Colombia, utilizada para estudiar la respuesta espectral de periodo corto y sus principales variables explicativas. El propósito es organizar, de manera clara y sistemática, el contexto del problema, los fundamentos mínimos para interpretar las variables y la exploración estadística del conjunto de datos.

## Propósito del libro

El libro tiene tres propósitos complementarios:

1. **Contextualizar el problema** desde la ingeniería sísmica y la modelación del movimiento del suelo.
2. **Documentar las variables y el enfoque metodológico** con el que se estructuró el EDA.
3. **Presentar la exploración univariada, bivariada y multivariada** como base para etapas posteriores de modelación predictiva.

## Estructura

El contenido se organiza de la siguiente manera:

- **Contexto, problema y objetivos**: justifica la pertinencia del estudio y delimita su alcance.
- **Marco teórico y metodología**: resume conceptos clave de respuesta espectral, RotD50, transformaciones logarítmicas y estructura del análisis.
- **EDA univariado**: describe distribuciones, escalas y comportamiento individual de las variables.
- **EDA bivariado**: explora relaciones entre la variable objetivo y las predictoras principales.
- **EDA multivariado**: examina dependencias conjuntas, patrones espaciales y estructuras de correlación.
- **Conclusiones**: sintetiza los hallazgos principales del análisis exploratorio.

## Alcance analítico

Aunque el dataset contiene espectros y metadatos asociados al evento, la estación y el sitio, este libro se concentra especialmente en la variable `T_0.01_RotD50`, utilizada como respuesta principal del análisis. En varias secciones también se trabaja con su transformación a escala física, definida como:

```{math}
Sa_{0.01} = \exp\left(T_{0.01,RotD50}\right)
```

## Nota sobre la interpretación

No todas las variables se encuentran almacenadas en su escala física original. Algunas han sido transformadas logarítmicamente durante el preprocesamiento, por lo que su interpretación debe realizarse distinguiendo cuidadosamente entre la escala almacenada y la escala física original.
