# Marco teórico y metodología

## Fundamentos del problema

La respuesta espectral resume la máxima respuesta de un sistema de un grado de libertad frente a una excitación sísmica. De forma general, el movimiento relativo del sistema puede representarse mediante:

```{math}
\ddot{x}(t) + 2\zeta\omega_n\dot{x}(t) + \omega_n^2 x(t) = -\ddot{x}_g(t)
```

A partir de esta ecuación, se construyen ordenadas espectrales para distintos periodos y un amortiguamiento dado. La aceleración espectral puede representarse como:

```{math}
S_a(T,\zeta)=\max_t\left|\ddot{x}(t)+\ddot{x}_g(t)\right|
```

En este trabajo, la medida de interés se expresa mediante `RotD50`, una medida rotacional que resume la respuesta horizontal independiente de la orientación:

```{math}
\mathrm{RotD50}(T)=P_{50}\left(S_a^{(\theta)}(T)\right)
```

## Variable objetivo

La variable principal del análisis es `T_0.01_RotD50`, correspondiente a la respuesta espectral en un periodo corto. En el dataset esta variable se encuentra almacenada en escala logarítmica natural, por lo que en varias secciones se usa también su forma en escala física:

```{math}
Sa_{0.01} = \exp\left(T_{0.01,RotD50}\right)
```

## Variables predictoras principales

Las predictoras de mayor interés son:

- **Magnitude**: representa el tamaño del evento sísmico.
- **Rrup_OpenQuake**: distancia de ruptura; en algunos flujos puede encontrarse almacenada en escala logarítmica y debe interpretarse en consecuencia.
- **Hypocenter Depth (km)**: profundidad hipocentral.
- **Soil_Class**: categorización simplificada de la condición de sitio.

## Consideraciones metodológicas

El enfoque del libro es estrictamente exploratorio. No se persigue aquí un ajuste final de modelos, sino una caracterización ordenada del conjunto de datos. El análisis se organizó en tres niveles:

## 1. Análisis univariado

Se estudian distribuciones marginales, medidas resumen, posibles asimetrías, escalas de representación y comportamiento de variables numéricas y categóricas.

## 2. Análisis bivariado

Se examinan relaciones entre la variable objetivo y distintas predictoras. Esta etapa permite identificar tendencias, posibles dependencias monotónicas, contrastes por grupos y comportamientos diferenciales por clases de sitio u origen.

## 3. Análisis multivariado

Se revisan estructuras conjuntas mediante matrices de correlación, visualizaciones espaciales, cruces simultáneos entre variables y representaciones tridimensionales o geográficas cuando aportan claridad.

## Criterios de interpretación

A lo largo del libro se siguen tres criterios:

1. **Separar la interpretación física de la estadística**: una variable transformada en log no debe discutirse como si estuviera en kilómetros o en escala lineal.
2. **Priorizar claridad visual**: en varias gráficas se utilizan escalas logarítmicas cuando mejoran la lectura de la distribución.
3. **Mantener trazabilidad conceptual**: cada sección conecta la visualización con su significado dentro del problema sísmico.

## Alcance y limitaciones

Este EDA describe el comportamiento del dataset disponible, pero no constituye por sí mismo evidencia suficiente para generalizaciones fuera del dominio observado. Sus resultados deben interpretarse como base para etapas posteriores de modelación, validación y discusión ingenieril.
