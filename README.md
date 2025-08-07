# Regresión Lineal Múltiple para Predicción de Precios de Viviendas

Este repositorio documenta el desarrollo de un modelo de regresión lineal múltiple aplicado al conjunto de datos `kc_house.csv`, con el objetivo de predecir el precio de venta de propiedades en función de sus características físicas y geográficas.

## Objetivo

Construir un modelo estadístico que permita estimar el precio de una vivienda a partir de variables como número de habitaciones, superficie construida, ubicación, año de construcción, entre otras.

## Flujo de trabajo

### 1. Preparación de datos
- Carga del dataset con `pandas`
- Eliminación de columnas irrelevantes (`id`, `date`)
- Definición de variable dependiente (`price`) y variables independientes
- Adición de columna de intercepto para el modelo

### 2. Construcción del modelo
- División en conjunto de entrenamiento y prueba (`train_test_split`)
- Cálculo de coeficientes mediante álgebra lineal:
  - Producto matricial `XᵗX`
  - Pseudo-inversa `pinv(XᵗX)`
  - Obtención de betas: `β = (XᵗX)⁻¹ XᵗY`

### 3. Evaluación del modelo
- Métricas calculadas:
  - Error Cuadrático Medio (MSE)
  - Raíz del Error Cuadrático Medio (RMSE)
  - Coeficiente de Determinación (R²)
  - R² ajustado
- Comparación con reporte automatizado de `statsmodels`

### 4. Visualización de resultados
- Gráfico de predicciones vs valores reales
- Gráfico de residuos
- Histograma de distribución de errores residuales

## Resultados clave

- **R² ajustado**: 0.703  
- **RMSE**: $219,830.12 USD  
- **Media de error residual**: $5,252 USD  
- El modelo captura relaciones importantes, pero presenta limitaciones en precisión para valores altos.

## Herramientas utilizadas

- Python 3.x  
- pandas, NumPy  
- scikit-learn  
- statsmodels  
- matplotlib, seaborn

## Conclusiones

- El modelo es funcional y explica aproximadamente el 70% de la variabilidad del precio.
- La dispersión en zonas de alto valor inmobiliario sugiere necesidad de modelos más robustos.
- La distribución de residuos es cercana a la normal, lo que valida el supuesto de linealidad.
