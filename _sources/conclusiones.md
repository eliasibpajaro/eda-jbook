# Conclusiones del análisis exploratorio

El análisis exploratorio permite establecer varias conclusiones generales sobre el conjunto de datos y su utilidad para etapas posteriores de modelación:

## 1. La variable objetivo exige una interpretación cuidadosa de la escala

La respuesta `T_0.01_RotD50` se encuentra almacenada en escala logarítmica, por lo que su lectura física se facilita al trabajar también con `Sa_0_01 = exp(T_0.01_RotD50)`. Esta distinción es fundamental para no confundir la interpretación estadística con la interpretación ingenieril.

## 2. Las predictoras principales conservan coherencia física con la respuesta espectral

Magnitud, distancia, profundidad y condición de sitio constituyen una base conceptualmente consistente para explicar la variabilidad observada en la respuesta espectral de periodo corto. En particular, magnitud y distancia concentran una parte importante del comportamiento esperable desde el punto de vista físico.

## 3. La exploración evidencia la importancia de las transformaciones y de la escala de representación

El comportamiento de varias variables muestra que la escala lineal no siempre es la más adecuada para su análisis. En estos casos, el uso de transformaciones logarítmicas o visualizaciones adaptadas mejora la interpretación y reduce el riesgo de conclusiones engañosas sobre asimetría, dispersión o concentración.

## 4. La integración de NGA-West y Colombia amplía el dominio observado, pero introduce heterogeneidad

La combinación de registros provenientes de NGA-West y Colombia incrementa la cobertura del dataset en términos de magnitud, distancia, profundidad y condiciones de sitio. Sin embargo, esta integración también introduce heterogeneidad entre orígenes, lo que debe ser reconocido al interpretar patrones estadísticos y al plantear modelos posteriores.

## 5. El EDA aporta una base útil para la modelación posterior

La revisión univariada, bivariada y multivariada permite identificar concentraciones, dependencias, contrastes espaciales, diferencias entre grupos y posibles limitaciones del conjunto de datos. En este sentido, el libro funciona como una base documental previa a cualquier etapa de modelación predictiva o comparación entre algoritmos.

## 6. El dataset debe interpretarse dentro de su dominio observado

Los patrones identificados son informativos para la muestra disponible, pero no deben extrapolarse automáticamente a condiciones fuera del rango de magnitudes, distancias, profundidades o clases de sitio representadas en la base analizada.
