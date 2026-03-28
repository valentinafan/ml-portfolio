# Analisis Predictivo de Costos de Seguros Medicos

Modelo de regresion lineal multiple construido desde cero con algebra matricial para predecir costos de seguros medicos en Estados Unidos.

---

## Descripcion

Este proyecto investiga como factores demograficos y de estilo de vida influyen en el precio de las primas de seguro medico. A diferencia de usar librerias como sklearn, el modelo se implementa **desde cero** usando operaciones matriciales con NumPy, lo que permite entender en profundidad como funciona la regresion lineal internamente.

El analisis revela que un solo factor — el tabaquismo — tiene un impacto dramaticamente mayor que cualquier otra variable en el costo del seguro.

---

## Objetivo

- Construir un modelo de regresion lineal multiple usando el metodo de minimos cuadrados ordinarios (OLS) con algebra matricial
- Identificar que factores demograficos y de estilo de vida tienen mayor impacto en los costos de seguros
- Evaluar la significancia estadistica de cada predictor (t-tests, p-values)
- Analizar la calidad del modelo mediante R², residuos y diagnosticos visuales

---

## Dataset

| Atributo | Descripcion |
|----------|-------------|
| **Fuente** | [Medical Cost Personal Dataset - Kaggle](https://www.kaggle.com/mirichoi0218/insurance) |
| **Tamano** | 1,338 registros x 7 variables |
| **Tipo** | Mixto (numericos y categoricos) |
| **Variables** | age, sex, bmi, children, smoker, region, charges |

**Variables principales:**
- `age`: Edad del asegurado
- `bmi`: Indice de masa corporal (kg/m²)
- `smoker`: Si la persona fuma (yes/no)
- `charges`: Costo anual del seguro (variable objetivo)

---

## Metodologia

### Tecnicas Principales

1. **Regresion Lineal Multiple (OLS)**
   - Metodo de minimos cuadrados ordinarios implementado con algebra matricial: β = (X'X)⁻¹X'y
   - Permite estimar el efecto independiente de cada variable sobre el costo

2. **One-Hot Encoding Manual**
   - Codificacion de variables categoricas (sexo, fumador, region) a variables dummy
   - Region northeast como categoria de referencia para evitar multicolinealidad

3. **Inferencia Estadistica**
   - Calculo de errores estandar, t-statistics y p-values para determinar significancia
   - Evaluacion de R² y R² ajustado para bondad de ajuste

### Pasos del Analisis

1. Carga y exploracion del dataset (1,338 registros, 0 valores nulos)
2. EDA con visualizaciones: distribuciones, boxplots, scatter plots, heatmap de correlacion
3. Preprocesamiento: codificacion de variables categoricas
4. Construccion del modelo OLS desde cero con NumPy
5. Evaluacion estadistica completa y analisis de residuos

---

## Resultados

### Hallazgos Principales

- **El tabaquismo es el factor dominante:** ser fumador incrementa el costo en $23,849 anuales (~3.8x mas que un no fumador)
- **La edad y el IMC son significativos:** cada ano adicional agrega ~$257, cada punto de IMC agrega ~$339
- **El sexo no influye:** la diferencia entre hombres y mujeres no es estadisticamente significativa (p = 0.69)

### Estadisticas Clave

| Metrica | Valor |
|---------|-------|
| R² | 0.7509 |
| R² ajustado | 0.7494 |
| Coeficiente smoker_yes | +$23,848.53 |
| Coeficiente age | +$256.86 por ano |
| Coeficiente bmi | +$339.19 por punto |
| Variables significativas (p < 0.05) | 7 de 9 |

### Insights

1. **Tabaquismo como factor de riesgo financiero:** Con un t-statistic de 57.7, fumar es por mucho el predictor mas fuerte. Las aseguradoras cargan casi $24,000 adicionales a los fumadores.
2. **La edad importa mas que el peso:** Aunque ambos son significativos, el efecto acumulativo de la edad supera al del IMC en la mayoria de los rangos.
3. **El genero no deberia influir en las primas:** Los datos no muestran diferencia significativa entre hombres y mujeres, lo cual tiene implicaciones para politicas de precios justas.

---

## Conclusiones

### Resumen

El modelo explica el 75.1% de la variacion en los costos de seguros medicos. El tabaquismo es el factor mas determinante, seguido por la edad y el IMC. Las variables de region tienen efectos menores pero estadisticamente significativos.

### Recomendaciones

- Programas de cesacion tabaquica podrian reducir significativamente los costos de seguros
- Las politicas de precios basadas en genero no se justifican estadisticamente
- Un modelo con interacciones (ej: smoker x bmi) podria mejorar las predicciones

### Limitaciones

- El modelo asume relaciones lineales; la relacion real puede ser no lineal
- No se uso validacion cruzada (train/test split)
- El dataset no incluye variables como historial medico o nivel de actividad fisica

---

## Tecnologias Utilizadas

- **Python 3.x** - Lenguaje de programacion
- **Pandas** - Manipulacion de datos
- **NumPy** - Algebra matricial y operaciones numericas
- **Matplotlib & Seaborn** - Visualizacion estadistica
- **SciPy** - Calculos de t-statistics y p-values
- **Jupyter Notebook** - Entorno interactivo

---

## Estructura del Proyecto

```
01-medical-insurance-costs/
├── us-medical-insurance-costs.ipynb   # Notebook principal
├── insurance.csv                      # Dataset
└── README.md                          # Este archivo
```

---

## Como Usar

```bash
# Clonar el repositorio
git clone https://github.com/valentinafan/ml-portfolio.git
cd ml-portfolio/01-medical-insurance-costs

# Instalar dependencias
pip install pandas numpy matplotlib seaborn scipy

# Abrir notebook
jupyter notebook us-medical-insurance-costs.ipynb
```

Ejecuta todas las celdas: `Kernel → Restart & Run All`

---

## Visualizaciones

- **Histograma + Boxplot**: Distribucion de costos de seguro
- **Scatter plots**: Relacion edad/IMC vs costos, coloreados por fumador
- **Boxplots comparativos**: Impacto de variables categoricas (fumador, sexo, region)
- **Heatmap de correlacion**: Matriz de correlacion entre variables
- **Barplot horizontal**: Importancia relativa de cada variable (coeficientes)
- **Analisis de residuos**: Residuos vs predichos, distribucion de residuos, real vs predicho

---

## Preguntas que responde este analisis

- Que factores determinan cuanto paga una persona por su seguro medico?
- Cuanto mas caro es el seguro para un fumador vs un no fumador?
- El sexo influye significativamente en el costo del seguro?
- Que tan bien predice el modelo los costos reales?

---

**Autora:** Valentina Fandino
- GitHub: [@valentinafan](https://github.com/valentinafan)
