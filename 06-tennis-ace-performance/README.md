# Analisis Predictivo del Rendimiento en Tenis Profesional

Modelos de regresion lineal para predecir las ganancias de tenistas profesionales a partir de sus estadisticas de juego.

---

## Descripcion

Que hace que un tenista profesional gane mas dinero: tener un servicio potente o ganar muchos partidos? Este proyecto usa regresion lineal simple y multiple para descubrir cuales estadisticas de juego predicen mejor las ganancias (prize money) de los tenistas.

El analisis muestra que los aces por si solos son un predictor debil — se necesita un juego completo para ganar dinero en el tenis.

---

## Objetivo

- Explorar las correlaciones entre 20+ estadisticas de juego y las ganancias
- Construir y comparar modelos de regresion simple (una variable) y multiple (5 variables)
- Identificar cuales metricas de rendimiento tienen mayor poder predictivo
- Evaluar la calidad de los modelos con metricas estandar (R², RMSE)

---

## Dataset

| Atributo | Descripcion |
|----------|-------------|
| **Fuente** | Estadisticas de la ATP (Association of Tennis Professionals) |
| **Tamano** | 1,721 registros x 23 variables |
| **Tipo** | Numerico |
| **Variables** | Wins, Losses, Aces, DoubleFaults, BreakPoints, Ranking, Winnings, etc. |

**Variable objetivo:** `Winnings` (ganancias en dolares)

---

## Metodologia

### Tecnicas Principales

1. **Analisis de Correlacion**
   - Correlacion de Pearson entre cada variable y las ganancias
   - Heatmap de correlacion entre variables top

2. **Regresion Lineal Simple**
   - Modelo 1: Wins → Winnings
   - Modelo 2: Aces → Winnings
   - Comparacion directa del poder predictivo de cada variable

3. **Regresion Lineal Multiple**
   - 5 features: Wins, Ranking, Aces, BreakPointsConverted, ServiceGamesWon
   - Train/test split (80/20) para evaluacion

### Pasos del Analisis

1. Carga y exploracion del dataset (1,721 registros)
2. EDA: distribucion de ganancias, matriz de correlacion
3. Scatter plots de variables clave con lineas de tendencia
4. Modelo simple con Wins (mejor predictor individual)
5. Modelo simple con Aces (comparacion)
6. Modelo multiple con 5 variables
7. Comparacion de los 3 modelos

---

## Resultados

### Hallazgos Principales

- **Wins es el mejor predictor individual** de ganancias — ganar partidos genera prize money directamente
- **El modelo multiple supera significativamente al simple**, capturando mas variabilidad
- **Los Aces son un predictor debil**: potencia de servicio sola no garantiza ganancias

### Estadisticas Clave

| Modelo | Variables | R² (Test) | RMSE |
|--------|-----------|-----------|------|
| Simple (Wins) | 1 | ~0.83 | Variable |
| Simple (Aces) | 1 | ~0.16 | Variable |
| Multiple | 5 | ~0.87 | Variable |

### Insights

1. **Ganar partidos es lo que cuenta:** Wins tiene la correlacion mas alta con ganancias. Esto confirma la estructura de prize money del tenis: ganar = avanzar en torneos = mas dinero.
2. **El Ranking tiene efecto negativo:** Un coeficiente negativo es correcto — un ranking menor (ej: #1) indica mejor posicion, por lo que menor ranking = mayores ganancias.
3. **Potencia vs consistencia:** Los aces (servicio potente) predicen poco por si solos. Las ganancias dependen mas de un juego integral que de una sola habilidad.

---

## Conclusiones

### Resumen

Las ganancias en el tenis profesional se predicen mejor con una combinacion de variables: victorias, ranking, aces y break points. Un servicio potente ayuda, pero sin victorias y buen ranking, no se traduce en dinero.

### Recomendaciones

- Aplicar transformacion logaritmica a Winnings (distribucion muy sesgada)
- Usar validacion cruzada k-fold para estimaciones mas robustas
- Probar modelos no lineales (Random Forest, Gradient Boosting)

### Limitaciones

- Solo un split train/test (sin cross-validation)
- Los modelos asumen linealidad
- Las ganancias tienen sesgo positivo extremo (pocos jugadores ganan mucho)
- No se controla por era o tipo de superficie

---

## Tecnologias Utilizadas

- **Python 3.x** - Lenguaje de programacion
- **Pandas** - Manipulacion de datos
- **NumPy** - Operaciones numericas
- **Matplotlib & Seaborn** - Visualizacion
- **Scikit-learn** - LinearRegression, train_test_split, metricas
- **Jupyter Notebook** - Entorno interactivo

---

## Estructura del Proyecto

```
06-tennis-ace-performance/
├── tennis_ace_analysis.ipynb   # Notebook principal
├── tennis_stats.csv            # Dataset
└── README.md                   # Este archivo
```

---

## Como Usar

```bash
cd ml-portfolio/06-tennis-ace-performance
pip install pandas numpy matplotlib seaborn scikit-learn
jupyter notebook tennis_ace_analysis.ipynb
```

---

## Visualizaciones

- **Histograma**: Distribucion de ganancias (original y log-transformada)
- **Barplot + Heatmap**: Correlaciones con ganancias y entre variables top
- **Scatter plots**: 4 variables mas correlacionadas vs ganancias con lineas de tendencia
- **Real vs Predicho**: Comparacion para modelos simple y multiple
- **Analisis de residuos**: Diagnostico del modelo simple
- **Barplot comparativo**: R² de los 3 modelos

---

## Preguntas que responde este analisis

- Que estadisticas predicen mejor cuanto dinero gana un tenista?
- Es el servicio (aces) mas importante que ganar partidos?
- Cuanto mejora un modelo al agregar mas variables?
- Que metricas deberia priorizar un tenista para maximizar ganancias?

---

**Autora:** Valentina Fandino
- GitHub: [@valentinafan](https://github.com/valentinafan)
