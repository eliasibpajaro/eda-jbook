# Conclusiones del análisis exploratorio

El análisis exploratorio permite establecer varias conclusiones generales sobre el conjunto de datos y su utilidad para etapas posteriores de modelación:

## 1. La variable objetivo requiere interpretación por escala

La respuesta `T_0.01_RotD50` se encuentra almacenada en escala logarítmica, por lo que su lectura física mejora al trabajar también con `Sa_0_01 = exp(T_0.01_RotD50)`. Esta distinción es clave para no mezclar interpretación estadística e interpretación ingenieril.

## 2. Las predictoras dominantes tienen significado físico claro

Magnitud, distancia, profundidad y condición de sitio ofrecen una base consistente para explicar la variabilidad observada en la respuesta espectral de periodo corto. En particular, magnitud y distancia concentran gran parte de la variación esperable desde el punto de vista físico.

## 3. La exploración evidencia escalas y transformaciones necesarias

El comportamiento de varias variables sugiere que la escala lineal no siempre es la más adecuada para su lectura. En estos casos, el uso de transformaciones logarítmicas o visualizaciones adaptadas mejora la interpretación y evita conclusiones engañosas sobre asimetría o dispersión.

## 4. El EDA aporta una base útil para la modelación posterior

La revisión univariada, bivariada y multivariada permite detectar concentraciones, dependencias, contrastes espaciales y limitaciones del dataset. Esto hace que el libro funcione como una base documental previa a cualquier etapa de modelación predictiva o comparación entre algoritmos.

## 5. El dataset debe interpretarse dentro de su dominio observado

Los patrones encontrados son informativos para el conjunto de datos disponible, pero no deben extrapolarse automáticamente a condiciones fuera del rango de magnitudes, distancias, profundidades o clases de sitio representadas en la muestra.
