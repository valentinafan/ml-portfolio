# Exploracion del Dataset de Jeopardy: 216,000+ Preguntas

Analisis a gran escala de mas de 200,000 preguntas del programa de television Jeopardy! para descubrir patrones tematicos y temporales.

---

## Descripcion

Jeopardy! es uno de los concursos de conocimiento mas iconicos de la television. Este proyecto explora un dataset masivo de mas de 216,000 preguntas para descubrir que temas son los mas frecuentes, como ha evolucionado la dificultad a lo largo del tiempo, y cuales son las respuestas que mas se repiten.

El analisis incluye funciones reutilizables para filtrado y busqueda, permitiendo explorar cualquier tema de interes de forma flexible.

---

## Objetivo

- Limpiar y preparar un dataset a gran escala con formatos inconsistentes
- Desarrollar funciones reutilizables para filtrado por palabras clave
- Analizar la distribucion de valores (dificultad) de las preguntas
- Identificar las categorias y respuestas mas frecuentes
- Explorar tendencias temporales en el programa

---

## Dataset

| Atributo | Descripcion |
|----------|-------------|
| **Fuente** | Archivo historico de preguntas de Jeopardy! |
| **Tamano** | 216,930 preguntas x 7 variables |
| **Tipo** | Mixto (texto, fechas, numerico) |
| **Periodo** | Multiples decadas del programa |
| **Variables** | Show Number, Air Date, Round, Category, Value, Question, Answer |

**Rondas:** Jeopardy! (ronda 1), Double Jeopardy! (ronda 2), Final Jeopardy! (ronda final)

---

## Metodologia

### Tecnicas Principales

1. **Limpieza de Datos a Escala**
   - Conversion de valores monetarios (string "$1,000" → float 1000.0)
   - Manejo de valores "no value" y formatos inconsistentes
   - Parsing de fechas para analisis temporal

2. **Funciones de Busqueda Reutilizables**
   - `filter_questions()`: Filtra preguntas que contengan palabras clave (case-insensitive)
   - `top_answers()`: Retorna las N respuestas mas frecuentes
   - `avg_difficulty()`: Calcula el valor promedio como proxy de dificultad

3. **Analisis Exploratorio a Gran Escala**
   - Distribucion de valores, categorias, respuestas y tendencias temporales
   - Agrupacion y visualizacion de patrones en 216K+ registros

### Pasos del Analisis

1. Carga y limpieza de columnas (nombres con espacios extra)
2. Conversion de tipos de datos (fechas, valores monetarios)
3. Desarrollo de funciones de filtrado y busqueda
4. Analisis de distribucion de valores por ronda
5. Identificacion de categorias y respuestas mas frecuentes
6. Analisis de tendencias temporales

---

## Resultados

### Hallazgos Principales

- El dataset contiene **216,930 preguntas** con miles de categorias unicas
- La dificultad (valor) **aumenta significativamente entre rondas**, confirmando la estructura progresiva
- Ciertas respuestas aparecen con **alta frecuencia**, revelando temas favoritos del programa

### Estadisticas Clave

| Metrica | Valor |
|---------|-------|
| Total de preguntas | 216,930 |
| Categorias unicas | Miles |
| Valor promedio | Variable por ronda |
| Valor maximo | $10,000+ |

### Insights

1. **Patrones repetitivos:** Las mismas respuestas aparecen cientos de veces. Un concursante que estudie las respuestas mas frecuentes tendria ventaja estadistica.
2. **Dificultad progresiva:** Double Jeopardy tiene valores significativamente mas altos que la primera ronda, y Final Jeopardy tiene los mas altos de todos.
3. **Temas dominantes:** Ciertos temas (historia, ciencia, geografia) aparecen mucho mas frecuentemente que otros, reflejando el conocimiento culturalmente valorado en EE.UU.

---

## Conclusiones

### Resumen

Jeopardy! tiene patrones claros y explotables: respuestas recurrentes, categorias dominantes y dificultad predecible por ronda. El dataset es una fuente rica para analisis de NLP y modelos de prediccion de dificultad.

### Recomendaciones

- Las funciones de busqueda desarrolladas permiten investigar cualquier tema de interes
- Un modelo de NLP podria predecir la dificultad de una pregunta basandose en su texto
- Las respuestas mas frecuentes son un recurso valioso para concursantes

### Limitaciones

- No se aplican tecnicas de NLP avanzadas (embeddings, topic modeling)
- El analisis temporal depende de la cobertura del dataset
- No se analiza la relacion entre categoria y valor (dificultad)

---

## Tecnologias Utilizadas

- **Python 3.x** - Lenguaje de programacion
- **Pandas** - Manipulacion de datos a gran escala
- **NumPy** - Operaciones numericas
- **Matplotlib & Seaborn** - Visualizacion
- **Jupyter Notebook** - Entorno interactivo

---

## Estructura del Proyecto

```
07-jeopardy-data-exploration/
├── This is Jeopardy.ipynb   # Notebook principal
├── jeopardy.csv             # Dataset (216K+ registros)
└── README.md                # Este archivo
```

---

## Como Usar

```bash
cd ml-portfolio/07-jeopardy-data-exploration
pip install pandas numpy matplotlib seaborn
jupyter notebook "This is Jeopardy.ipynb"
```

---

## Visualizaciones

- **Histograma**: Distribucion de valores de las preguntas
- **Barplot horizontal**: Top 10 valores mas comunes
- **Barplot**: Valor promedio por ronda
- **Barplot temporal**: Preguntas y valor promedio por ano
- **Barplot horizontal**: Top 20 categorias y respuestas mas frecuentes

---

## Preguntas que responde este analisis

- Cuales son los temas mas frecuentes en Jeopardy?
- Como ha evolucionado la dificultad del programa?
- Que respuestas se repiten mas?
- Es posible identificar patrones utiles para un concursante?

---

**Autora:** Valentina Fandino
- GitHub: [@valentinafan](https://github.com/valentinafan)
