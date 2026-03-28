# Portfolio de Data Science & Machine Learning

Proyectos de analisis de datos y machine learning aplicados a problemas reales: desde predecir costos de seguros medicos hasta identificar especies en peligro de extincion. Cada proyecto sigue un flujo completo de ciencia de datos: exploracion, limpieza, modelado, evaluacion y conclusiones accionables.

---

## Proyectos

### 01 - [Analisis Predictivo de Costos de Seguros Medicos](01-medical-insurance-costs/)
**Pregunta:** Que factores determinan cuanto paga una persona por su seguro medico?

Construi un modelo de regresion lineal multiple **desde cero usando algebra matricial** (sin sklearn) para predecir costos de seguros. El modelo revelo que **ser fumador incrementa el costo en $23,849 anuales** — el factor mas determinante, muy por encima de la edad o el IMC.

`Regresion OLS` `Algebra Matricial` `Inferencia Estadistica` `1,338 registros`

---

### 02 - [Seleccion de Features para Prediccion de Obesidad](02-obesity-feature-selection/)
**Pregunta:** De 18 variables sobre habitos alimenticios, cuales realmente predicen la obesidad?

Compare tres metodos de seleccion de caracteristicas (SFS, SBS, RFE) para optimizar un modelo de regresion logistica. El resultado: **con solo 7 de 18 variables se logra mejor precision que con todas**, y los habitos alimenticios (consumo hipercalorico, comer entre comidas) son mas predictivos que el ejercicio o el transporte.

`Feature Selection` `Regresion Logistica` `SFS / SBS / RFE` `Mlxtend`

---

### 03 - [Esperanza de Vida y PIB: Estudio Comparativo entre Paises](03-life-expectancy-gdp/)
**Pregunta:** La riqueza de un pais determina cuanto viven sus ciudadanos?

Analice datos del Banco Mundial y la OMS para 6 paises (2000-2015). Descubri que **Zimbabwe mejoro su esperanza de vida en 14.7 anos** (mas que cualquier otro pais), mientras que la relacion PIB-esperanza de vida **no es lineal**: se aplana en paises de alto ingreso. Incluye pruebas de hipotesis (t-tests) que confirman diferencias significativas entre grupos.

`EDA` `Correlacion de Pearson` `Regresion Lineal` `Pruebas t-test` `6 paises, 16 anos`

---

### 04 - [Biodiversidad en Parques Nacionales de EE.UU.](04-biodiversity-national-parks/)
**Pregunta:** Que especies estan en mayor riesgo y donde debemos enfocar los esfuerzos de conservacion?

Explore datos del National Park Service con 5,824 especies en 4 parques. Un test Chi-cuadrado (p < 0.001) confirmo que **las aves y mamiferos tienen desproporcionadamente mas probabilidad de estar en peligro** que las plantas. Identifique las 15 especies con monitoreo mas urgente y prepare los datos para un futuro modelo de clasificacion.

`Chi-cuadrado` `Analisis de Conservacion` `Crosstabs` `Preparacion ML` `5,824 especies`

---

### 05 - [Hongos: Identificacion de Especies Venenosas](05-exploring-mushrooms/)
**Pregunta:** Que caracteristicas fisicas permiten distinguir un hongo venenoso de uno comestible?

Analice 8,124 hongos con 23 caracteristicas morfologicas. Usando el coeficiente V de Cramer, identifique que **el olor es el predictor mas fuerte de toxicidad**: hongos con olor "Pungent" o "Foul" son practicamente siempre venenosos. Una regla simple basada solo en el olor clasificaria correctamente la gran mayoria de los casos.

`V de Cramer` `Analisis Categorico` `Chi-cuadrado` `8,124 muestras, 23 variables`

---

### 06 - [Analisis Predictivo del Rendimiento en Tenis Profesional](06-tennis-ace-performance/)
**Pregunta:** Que estadisticas de juego predicen mejor las ganancias de un tenista?

Compare modelos de regresion simple y multiple sobre 1,721 registros de tenistas profesionales. El modelo multiple (5 variables) supero significativamente al simple: **las victorias son el mejor predictor individual**, pero agregar ranking, aces y break points mejora la prediccion considerablemente. Los aces por si solos son un predictor debil — se necesita un juego completo para ganar dinero en el tenis.

`Regresion Simple y Multiple` `Train/Test Split` `Scikit-learn` `1,721 registros`

---

### 07 - [Exploracion del Dataset de Jeopardy: 216K+ Preguntas](07-jeopardy-data-exploration/)
**Pregunta:** Que patrones se esconden en mas de 200,000 preguntas del concurso de TV mas famoso?

Desarrolle funciones reutilizables para explorar un dataset masivo del programa Jeopardy!. El analisis revelo las categorias mas frecuentes, como evoluciono la dificultad a lo largo de los anos, y cuales son las respuestas que mas se repiten — informacion valiosa tanto para concursantes como para modelos de NLP.

`Big Data` `Funciones Reutilizables` `Analisis Temporal` `Limpieza de Datos` `216,930 preguntas`

---

## Stack Tecnologico

| Herramienta | Uso |
|-------------|-----|
| **Python 3.x** | Lenguaje principal |
| **Pandas & NumPy** | Manipulacion de datos y operaciones matriciales |
| **Matplotlib & Seaborn** | Visualizaciones estadisticas profesionales |
| **Scikit-learn** | Modelos de Machine Learning y evaluacion |
| **SciPy** | Pruebas de hipotesis y estadistica inferencial |
| **Mlxtend** | Metodos avanzados de seleccion de features |

## Autor

**Valentina Fandino** — Data Science & Machine Learning

[![GitHub](https://img.shields.io/badge/GitHub-valentinafan-181717?style=flat&logo=github)](https://github.com/valentinafan)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat&logo=linkedin)](https://www.linkedin.com/in/valentinafandino/)
