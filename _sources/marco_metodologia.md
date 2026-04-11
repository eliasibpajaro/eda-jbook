# Marco teórico y metodología

## Fundamentos del problema

La respuesta espectral resume la máxima respuesta de un sistema de un grado de libertad sometido a una excitación sísmica. De forma general, el movimiento relativo del sistema puede representarse mediante:

```{math}
\ddot{x}(t) + 2\zeta\omega_n\dot{x}(t) + \omega_n^2 x(t) = -\ddot{x}_g(t)
```

A partir de esta ecuación se construyen ordenadas espectrales para distintos periodos y para un amortiguamiento dado. La aceleración espectral puede expresarse como:

```{math}
S_a(T,\zeta)=\max_t\left|\ddot{x}(t)+\ddot{x}_g(t)\right|
```

En este trabajo, la medida de interés se representa mediante `RotD50`, una medida rotacional que resume la respuesta horizontal de manera independiente de la orientación:

```{math}
\mathrm{RotD50}(T)=P_{50}\left(S_a^{(\theta)}(T)\right)
```

## Variable objetivo

La variable principal del análisis es `T_0.01_RotD50`, correspondiente a la respuesta espectral en un periodo corto. En el dataset, esta variable se encuentra almacenada en escala logarítmica natural, por lo que en varias secciones se utiliza también su forma en escala física:

```{math}
Sa_{0.01} = \exp\left(T_{0.01,RotD50}\right)
```

## Variables predictoras principales

Las predictoras de mayor interés son:

- **Magnitude**: representa el tamaño del evento sísmico.
- **Rrup_OpenQuake**: distancia de ruptura; en algunos flujos puede encontrarse almacenada en escala logarítmica, por lo que su interpretación debe hacerse con cuidado.
- **Hypocenter Depth (km)**: profundidad hipocentral.
- **Soil_Class**: categorización simplificada de la condición de sitio.
- **origen**: variable que distingue la procedencia de los registros dentro de la base integrada.

## Consideraciones metodológicas

El enfoque del libro es estrictamente exploratorio. No se pretende ajustar aquí un modelo predictivo final, sino caracterizar de manera ordenada el conjunto de datos y sus principales patrones estadísticos. El análisis se organiza en tres niveles:

## 1. Análisis univariado

Se estudian distribuciones marginales, medidas resumen, posibles asimetrías, escalas de representación y comportamiento individual de variables numéricas y categóricas.

## 2. Análisis bivariado

Se examinan relaciones entre la variable objetivo y distintas predictoras. Esta etapa permite identificar tendencias generales, dependencias monotónicas, contrastes por grupos y diferencias asociadas a clases de sitio u origen.

## 3. Análisis multivariado

Se revisan estructuras conjuntas mediante matrices de correlación, visualizaciones espaciales, cruces simultáneos entre variables y representaciones tridimensionales o geográficas cuando aportan claridad interpretativa.

## Criterios de interpretación

A lo largo del libro se siguen tres criterios principales:

1. **Distinguir entre escala física y escala transformada**: una variable almacenada en logaritmo no debe interpretarse como si estuviera en kilómetros o en escala lineal.
2. **Priorizar claridad visual y consistencia analítica**: en varias gráficas se emplean escalas logarítmicas cuando ello mejora la lectura de la distribución y evita interpretaciones engañosas.
3. **Mantener trazabilidad conceptual**: cada visualización se interpreta en función de su significado físico y de su papel dentro del problema sísmico.

## Alcance y limitaciones

Este EDA describe el comportamiento del dataset disponible, pero no constituye por sí mismo evidencia suficiente para generalizar resultados fuera del dominio observado. Sus hallazgos deben entenderse como base para etapas posteriores de modelación, validación y discusión ingenieril.
