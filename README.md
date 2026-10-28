# Procesamiento de espectros infrarrojos (FTIR)

## Descripción

Este repositorio contiene código desarrollado en Python para el procesamiento y análisis de espectros obtenidos mediante espectroscopía infrarroja por transformada de Fourier (FTIR).

El análisis permite comparar los espectros de referencia de metanol, etanol e isopropanol con el espectro de una muestra desconocida, identificar bandas de absorción características y estimar las contribuciones relativas de sus componentes.

## Metodología

El procesamiento incluye:

1. Visualización y comparación de espectros FTIR.
2. Identificación de máximos de absorción.
3. Comparación de bandas espectrales características.
4. Ajuste espectral mediante mínimos cuadrados no negativos (NNLS).
5. Estimación de las contribuciones relativas de metanol e isopropanol.
6. Evaluación del ajuste mediante el coeficiente de determinación (R²) y reconstrucción del espectro experimental.

### Ajuste mediante mínimos cuadrados no negativos

El espectro experimental se aproxima mediante una combinación lineal de los espectros de referencia:

\[
A_{\mathrm{muestra}}(\tilde{\nu}) \approx aA_{\mathrm{metanol}}(\tilde{\nu}) + bA_{\mathrm{isopropanol}}(\tilde{\nu})
\]

Los coeficientes \(a\) y \(b\) se determinan minimizando la suma de los residuos cuadrados, sujetos a restricciones de no negatividad.

Las contribuciones relativas se calculan normalizando los coeficientes respecto a su suma:

\[
P_{\mathrm{metanol}}=\frac{a}{a+b}\times100
\]

\[
P_{\mathrm{isopropanol}}=\frac{b}{a+b}\times100
\]

Los porcentajes obtenidos representan contribuciones espectrales relativas y no necesariamente concentraciones molares o volumétricas, ya que estas requieren una calibración apropiada.

## Herramientas utilizadas

- Python
- NumPy
- Pandas
- SciPy
- Matplotlib
- Jupyter Notebook

## Archivo principal

`Procesamiento_espect_infrarroja.ipynb`

Contiene el procesamiento de los datos experimentales, la comparación de espectros, el ajuste numérico y la representación gráfica de los resultados.

