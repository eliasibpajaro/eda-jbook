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

## 7. Los modelos de Machine Learning permiten complementar el EDA con una evaluación predictiva

La etapa de modelación permitió pasar de una interpretación exploratoria del dataset a una evaluación cuantitativa de su capacidad predictiva. A partir de las variables `Magnitude`, `Rrup_OpenQuake`, `Hypocenter Depth (km)` y `Soil_Class`, junto con variables derivadas coherentes con la escala del conjunto de datos, fue posible entrenar y comparar distintos algoritmos para estimar `T_0.01_RotD50`.

Esta etapa confirma que el dataset no solo permite describir patrones, sino también construir modelos capaces de capturar relaciones entre las características sismológicas, la condición de sitio y la respuesta espectral de periodo corto.

## 8. La corrección de escala fue esencial para evitar transformaciones redundantes

Un aspecto crítico de la modelación fue verificar que `Rrup_OpenQuake` ya se encontraba almacenado como `ln(Rrup)` y que `T_0.01_RotD50` ya correspondía a `ln(PGA)`. Por esta razón, no se aplicó nuevamente una transformación logarítmica sobre estas variables.

En su lugar, se recuperó la distancia física mediante `Rrup_km = exp(Rrup_OpenQuake)` y se conservó `log_Rrup = Rrup_OpenQuake` como representación logarítmica de la distancia. Esta decisión permitió mantener consistencia entre la interpretación física de la distancia y la estructura de variables usada por los modelos.

## 9. La comparación entre algoritmos evidencia diferencias en capacidad predictiva

Se evaluaron cinco modelos siguiendo la lógica del Dash: regresión lineal, XGBoost, Random Forest, SVR con kernel RBF y MLP. La comparación mediante RMSE, MAE, R² y R² en validación cruzada permitió identificar diferencias claras en el desempeño de los algoritmos.

Los modelos no lineales pueden capturar relaciones más complejas entre magnitud, distancia, profundidad, clase de suelo y respuesta espectral. Sin embargo, su desempeño debe interpretarse junto con las métricas de validación, ya que una mayor flexibilidad también puede aumentar el riesgo de sobreajuste si el conjunto de datos no es suficientemente amplio o balanceado.

## 10. El mejor modelo se seleccionó mediante un criterio combinado de desempeño

La selección del mejor modelo no se basó en una única métrica, sino en un ranking combinado que consideró RMSE, MAE, R² en prueba y R² promedio en validación cruzada. Este enfoque permite evitar que la decisión dependa exclusivamente de una métrica aislada.

El modelo seleccionado representa el mejor equilibrio entre bajo error, capacidad explicativa y estabilidad relativa en validación cruzada. Por tanto, puede considerarse como el modelo más adecuado dentro del conjunto de algoritmos evaluados para esta etapa del análisis.

Los resultados de Machine Learning muestran que el conjunto de datos contiene información suficiente para entrenar modelos predictivos de PGA aproximado. Sin embargo, las predicciones deben interpretarse dentro del dominio observado del dataset.

El modelo no debe extrapolarse automáticamente a combinaciones de magnitud, distancia, profundidad o clase de suelo poco representadas en la base. Por tanto, la modelación debe entenderse como una herramienta válida dentro del rango de datos disponible, no como una ecuación general de predicción de movimiento fuerte fuera de dicho dominio.
