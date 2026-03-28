# Seleccion de Caracteristicas para Prediccion de Obesidad

Comparacion de tres metodos wrapper de feature selection para optimizar un modelo de regresion logistica que predice obesidad.

---

## Descripcion

Cuando un dataset tiene muchas variables, no todas aportan informacion util al modelo. Este proyecto compara tres metodos automatizados de seleccion de features para determinar cuales habitos alimenticios y de estilo de vida son los verdaderos predictores de obesidad — y cuales son ruido.

El resultado: con menos de la mitad de las variables originales se logra igual o mejor precision que con todas.

---

## Objetivo

- Entrenar un modelo base de regresion logistica con las 18 variables disponibles
- Implementar y comparar tres metodos wrapper: SFS, SBS y RFE
- Identificar las variables consistentemente seleccionadas por multiples metodos
- Determinar el mejor balance entre numero de features y rendimiento del modelo

---

## Dataset

| Atributo | Descripcion |
|----------|-------------|
| **Fuente** | [UCI Machine Learning Repository - Obesity Levels](https://archive.ics.uci.edu/ml/datasets/Estimation+of+obesity+levels+based+on+eating+habits+and+physical+condition+) |
| **Tamano** | 2,111 registros x 19 variables |
| **Tipo** | Mixto (numericos y categoricos codificados) |
| **Variables** | 18 predictoras + 1 objetivo (NObeyesdad) |

**Variables principales:** Genero, edad, antecedentes familiares, consumo de alimentos hipercaloricos (FAVC), frecuencia de vegetales (FCVC), comidas principales (NCP), consumo entre comidas (CAEC), tabaquismo, consumo de agua, monitoreo calorico (SCC), actividad fisica (FAF), tiempo en pantallas, consumo de alcohol, y medio de transporte.

---

## Metodologia

### Tecnicas Principales

1. **Sequential Forward Selection (SFS)**
   - Comienza sin variables y agrega una a una la que mas mejora el modelo
   - Seleccion final: 9 features

2. **Sequential Backward Selection (SBS)**
   - Comienza con todas las variables y elimina una a una la menos util
   - Seleccion final: 7 features

3. **Recursive Feature Elimination (RFE)**
   - Entrena el modelo, elimina la variable con menor coeficiente, y repite
   - Requiere estandarizacion previa para comparar coeficientes
   - Seleccion final: 8 features

### Pasos del Analisis

1. Carga y exploracion del dataset
2. Entrenamiento del modelo base (18 variables) como linea de referencia
3. Aplicacion de SFS con k=9 features
4. Aplicacion de SBS con k=7 features
5. Estandarizacion y aplicacion de RFE con k=8 features
6. Comparacion visual y cuantitativa de los tres metodos

---

## Resultados

### Hallazgos Principales

- **SFS** logro el mejor accuracy (78.35%) con 9 features, superando al modelo base
- **SBS** alcanzo accuracy competitivo (78.21%) con solo 7 features — el subconjunto mas compacto
- **RFE** mantuvo accuracy similar al base (76.79%) con 8 features

### Estadisticas Clave

| Metodo | Features | Accuracy | vs Base |
|--------|----------|----------|---------|
| Base (todas) | 18 | 76.60% | --- |
| SFS (Forward) | 9 | 78.35% | +1.75pp |
| SBS (Backward) | 7 | 78.21% | +1.61pp |
| RFE | 8 | 76.79% | +0.19pp |

### Insights

1. **Menos es mas:** Con solo 7-9 variables se iguala o supera el rendimiento de usar las 18. Las variables eliminadas eran ruido que confundia al modelo.
2. **Los habitos alimenticios dominan:** FAVC (consumo hipercalorico), CAEC (comer entre comidas) y SCC (monitoreo calorico) fueron seleccionados por los 3 metodos.
3. **El transporte importa poco:** Las variables de transporte (Automobile, Bike, etc.) fueron consistentemente eliminadas.

---

## Conclusiones

### Resumen

Los tres metodos coinciden en que los habitos alimenticios y los antecedentes familiares son mas predictivos de la obesidad que factores como el transporte o el consumo de agua. Un modelo con 7 variables es tan bueno como uno con 18.

### Recomendaciones

- Para produccion, usar SBS con 7 features: mejor balance entre simplicidad y rendimiento
- Las intervenciones de salud publica deberian enfocarse en educacion alimentaria y monitoreo calorico
- Un modelo mas simple es mas interpretable y menos propenso al sobreajuste

### Limitaciones

- No se uso validacion cruzada (cv=0), lo que podria sobreestimar el rendimiento
- Solo se probo con regresion logistica; otros modelos podrian beneficiarse de features diferentes
- El dataset proviene de encuestas (auto-reporte), lo que puede introducir sesgo

---

## Tecnologias Utilizadas

- **Python 3.x** - Lenguaje de programacion
- **Pandas** - Manipulacion de datos
- **Scikit-learn** - Regresion logistica, RFE, StandardScaler
- **Mlxtend** - Sequential Feature Selector (SFS/SBS)
- **Matplotlib & Seaborn** - Visualizacion
- **Jupyter Notebook** - Entorno interactivo

---

## Estructura del Proyecto

```
02-obesity-feature-selection/
├── wrapper_method_starter.ipynb   # Notebook principal
├── obesity.csv                    # Dataset
└── README.md                      # Este archivo
```

---

## Como Usar

```bash
cd ml-portfolio/02-obesity-feature-selection
pip install pandas scikit-learn mlxtend matplotlib seaborn
jupyter notebook wrapper_method_starter.ipynb
```

---

## Visualizaciones

- **Graficos de accuracy vs features**: Evolucion del rendimiento al agregar/remover variables (SFS y SBS)
- **Barplot comparativo**: Accuracy de los 4 modelos lado a lado
- **Heatmap de seleccion**: Que features selecciono cada metodo (matriz binaria)

---

## Preguntas que responde este analisis

- Cuales habitos alimenticios realmente predicen la obesidad?
- Se puede reducir el numero de variables sin perder precision?
- Que metodo de seleccion de features funciona mejor para este problema?
- Que variables son consistentemente importantes segun multiples metodos?

---

**Autora:** Valentina Fandino
- GitHub: [@valentinafan](https://github.com/valentinafan)
