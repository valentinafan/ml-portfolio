# Hongos: Identificacion de Especies Comestibles vs Venenosas

Analisis exploratorio de 8,124 hongos para identificar las caracteristicas fisicas que mejor predicen la toxicidad.

---

## Descripcion

Identificar correctamente si un hongo es venenoso puede ser una cuestion de vida o muerte. Este proyecto analiza 23 caracteristicas morfologicas de 8,124 hongos para descubrir cuales atributos fisicos son los indicadores mas confiables de toxicidad.

El analisis revela que una sola variable — el olor — podria clasificar correctamente la gran mayoria de los hongos, lo que tiene implicaciones directas para guias de identificacion en campo.

---

## Objetivo

- Explorar la distribucion de 23 caracteristicas morfologicas del dataset
- Identificar que variables distinguen mejor entre hongos comestibles y venenosos
- Cuantificar la fuerza de asociacion entre cada variable y la clase usando V de Cramer
- Descubrir reglas simples de identificacion basadas en los datos

---

## Dataset

| Atributo | Descripcion |
|----------|-------------|
| **Fuente** | [UCI Machine Learning Repository - Mushroom Dataset](https://archive.ics.uci.edu/ml/datasets/mushroom) |
| **Tamano** | 8,124 muestras x 23 variables |
| **Tipo** | Completamente categorico |
| **Variables** | Cap shape, cap color, odor, gill color, spore print, habitat, etc. |

**Variable objetivo:** `Class` (Edible / Poisonous)

---

## Metodologia

### Tecnicas Principales

1. **Analisis de Distribucion Categorica**
   - Countplots y pie charts automatizados para las 23 variables
   - Seleccion inteligente de tipo de grafico segun cardinalidad

2. **Analisis Comparativo (Edible vs Poisonous)**
   - Barplots apilados mostrando la proporcion de toxicidad por valor de cada variable
   - Identificacion de valores que son 100% venenosos o 100% comestibles

3. **V de Cramer**
   - Coeficiente que mide la fuerza de asociacion entre variables categoricas (0 = sin asociacion, 1 = asociacion perfecta)
   - Ranking de todas las variables por su poder discriminante

### Pasos del Analisis

1. Carga y resumen del dataset (8,124 muestras, 0 valores nulos)
2. Visualizacion automatizada de las 23 variables
3. Analisis comparativo de 7 variables clave vs clase
4. Identificacion de valores 100% venenosos/comestibles
5. Calculo de V de Cramer para todas las variables
6. Ranking de poder predictivo

---

## Resultados

### Hallazgos Principales

- **El olor es el predictor mas fuerte** de toxicidad (V de Cramer mas alto)
- Hongos con olor "Pungent", "Creosote" o "Foul" son **practicamente siempre venenosos**
- Hongos sin olor ("None") o con olor a "Anise" son **comestibles**
- **Veil Type** tiene un solo valor para todo el dataset — no aporta informacion

### Reglas de Identificacion Descubiertas

| Caracteristica | Valor | Prediccion | Confianza |
|---------------|-------|------------|-----------|
| Odor | Pungent / Foul / Creosote | Venenoso | ~100% |
| Odor | None / Anise / Almond | Comestible | ~95%+ |
| Spore Print Color | Green | Venenoso | ~100% |
| Gill Color | Buff | Venenoso | Alta |

### Insights

1. **Una regla simple salva vidas:** Solo verificando el olor de un hongo, se puede clasificar correctamente la gran mayoria. Esto es util como regla practica de campo.
2. **Las variables visuales son menos confiables:** Cap shape, cap surface y cap color tienen baja asociacion con la toxicidad. Guiarse solo por la apariencia visual es peligroso.
3. **El poder de los datos categoricos:** Aun sin variables numericas, es posible descubrir patrones fuertes usando tecnicas como V de Cramer y tablas de contingencia.

---

## Conclusiones

### Resumen

El olor es el indicador mas confiable de toxicidad en hongos, seguido por el color de esporas y el color de agallas. Las caracteristicas visuales (forma, superficie, color del sombrero) son sorprendentemente poco confiables.

### Recomendaciones

- Un modelo de Decision Tree basado solo en Odor + Gill Color podria lograr accuracy > 95%
- Las guias de identificacion de hongos deberian enfatizar el olor como criterio primario
- Las variables con V de Cramer < 0.1 pueden descartarse para simplificar modelos

### Limitaciones

- El dataset es de 1987 y puede no representar todas las especies existentes
- Las categorias son simplificaciones de caracteristicas continuas
- No se evalua la interaccion entre variables

---

## Tecnologias Utilizadas

- **Python 3.x** - Lenguaje de programacion
- **Pandas** - Manipulacion de datos
- **NumPy** - Operaciones numericas
- **Matplotlib & Seaborn** - Visualizacion estadistica
- **SciPy** - Test Chi-cuadrado y V de Cramer
- **Jupyter Notebook** - Entorno interactivo

---

## Estructura del Proyecto

```
05-exploring-mushrooms/
├── Exploring Mushrooms.ipynb   # Notebook principal
├── mushroom_data.csv           # Dataset
└── README.md                   # Este archivo
```

---

## Como Usar

```bash
cd ml-portfolio/05-exploring-mushrooms
pip install pandas numpy matplotlib seaborn scipy
jupyter notebook "Exploring Mushrooms.ipynb"
```

---

## Visualizaciones

- **Grid 4x6**: Distribucion de las 23 variables (barplots y pie charts automaticos)
- **Barplots apilados**: Proporcion comestible vs venenoso por variable
- **Barplot horizontal**: Ranking de V de Cramer para todas las variables

---

## Preguntas que responde este analisis

- Que caracteristicas fisicas predicen mejor si un hongo es venenoso?
- Es posible identificar un hongo venenoso con una sola variable?
- Que tan confiable es guiarse por la apariencia visual de un hongo?
- Cuales variables serian las mas utiles para un modelo de clasificacion?

---

**Autora:** Valentina Fandino
- GitHub: [@valentinafan](https://github.com/valentinafan)
