# Esperanza de Vida y PIB: Estudio Comparativo entre Paises

Analisis de la relacion entre el producto interno bruto y la esperanza de vida en 6 paises representativos (2000-2015).

---

## Descripcion

Este proyecto investiga una pregunta fundamental de economia y salud publica: la riqueza de un pais determina cuanto viven sus ciudadanos? Usando datos del Banco Mundial y la OMS, se analizan las tendencias de PIB y esperanza de vida en Chile, China, Alemania, Mexico, Estados Unidos y Zimbabwe.

El analisis revela que la relacion no es tan simple como "mas dinero = mas vida" — y que algunos paises logran resultados sorprendentes.

---

## Objetivo

- Analizar la evolucion temporal del PIB y la esperanza de vida por pais
- Medir la correlacion entre ambas variables a nivel global y por pais
- Evaluar si un modelo de regresion lineal puede predecir la esperanza de vida a partir del PIB
- Realizar pruebas de hipotesis para comparar grupos de paises

---

## Dataset

| Atributo | Descripcion |
|----------|-------------|
| **Fuente** | Banco Mundial y Organizacion Mundial de la Salud (OMS) |
| **Tamano** | 96 registros (6 paises x 16 anos) |
| **Tipo** | Series temporales, numerico |
| **Periodo** | 2000 - 2015 |
| **Variables** | Country, Year, Life expectancy at birth (years), GDP |

**Paises analizados:** Chile, China, Alemania, Mexico, Estados Unidos, Zimbabwe

---

## Metodologia

### Tecnicas Principales

1. **Analisis de Tendencias Temporales**
   - Line plots por pais para identificar patrones de crecimiento
   - Calculo de tasas de crecimiento 2000 vs 2015

2. **Correlacion de Pearson**
   - Medicion de la fuerza de asociacion lineal entre PIB y esperanza de vida
   - Calculo por pais y global

3. **Pruebas de Hipotesis (t-tests)**
   - T-test de una muestra: Chile vs media global
   - T-test de dos muestras: paises de alto PIB vs bajo PIB

### Pasos del Analisis

1. Carga, limpieza y renombramiento de columnas
2. Estadisticas descriptivas por pais
3. Visualizacion de tendencias temporales (esperanza de vida y PIB)
4. Analisis de distribuciones (boxplots, violin plots, histogramas)
5. Correlacion y regresion lineal con analisis de residuos
6. Pruebas de hipotesis estadisticas

---

## Resultados

### Hallazgos Principales

- **Zimbabwe mejoro su esperanza de vida en 14.7 anos** (de ~44 a ~59), el mayor avance de todos los paises
- **China lidero en crecimiento de PIB** (~900%), pero no en mejora de esperanza de vida
- **La relacion PIB-esperanza de vida no es lineal:** se aplana en paises de alto ingreso

### Estadisticas Clave

| Pais | Esperanza de Vida (media) | PIB medio (B USD) | Cambio EV 2000-2015 |
|------|--------------------------|-------------------|---------------------|
| Alemania | ~80 anos | ~3,200B | +1.7 anos |
| EE.UU. | ~78 anos | ~14,500B | +1.9 anos |
| Chile | ~78 anos | ~190B | +2.3 anos |
| China | ~74 anos | ~5,200B | +3.8 anos |
| Mexico | ~75 anos | ~1,000B | +1.6 anos |
| Zimbabwe | ~50 anos | ~10B | +14.7 anos |

### Insights

1. **El PIB no es destino:** Chile, con un PIB modesto, logra esperanza de vida comparable a EE.UU. y Alemania. Politicas de salud publica importan tanto como la riqueza.
2. **Zimbabwe: una historia de recuperacion:** El salto de 14.7 anos coincide con la expansion de tratamientos antirretrovirales para VIH/SIDA post-2005.
3. **Rendimientos decrecientes:** A partir de cierto nivel de PIB, invertir mas dinero no aumenta proporcionalmente la esperanza de vida.

---

## Conclusiones

### Resumen

Existe una correlacion positiva entre PIB y esperanza de vida, pero la relacion no es lineal. Factores como el sistema de salud, la educacion y las politicas publicas pueden compensar las diferencias economicas. Zimbabwe demuestra que mejoras dramaticas son posibles incluso con recursos limitados.

### Recomendaciones

- Para predicciones mas precisas, incluir variables como gasto en salud per capita, educacion e indice de Gini
- Los modelos lineales son inadecuados para esta relacion; considerar modelos logaritmicos
- Las politicas de desarrollo deberian priorizar salud publica sobre crecimiento economico puro

### Limitaciones

- Solo 6 paises y 16 anos de datos
- No se controla por variables confundentes (gasto en salud, conflictos, epidemias)
- La clasificacion "alto/bajo PIB" es simplificada

---

## Tecnologias Utilizadas

- **Python 3.x** - Lenguaje de programacion
- **Pandas** - Manipulacion de datos
- **NumPy** - Operaciones numericas
- **Matplotlib & Seaborn** - Visualizacion estadistica
- **SciPy** - Correlacion de Pearson, t-tests
- **Jupyter Notebook** - Entorno interactivo

---

## Estructura del Proyecto

```
03-life-expectancy-gdp/
├── life_expectancy_gdp.ipynb   # Notebook principal
├── all_data.csv                # Dataset
└── README.md                   # Este archivo
```

---

## Como Usar

```bash
cd ml-portfolio/03-life-expectancy-gdp
pip install pandas numpy matplotlib seaborn scipy
jupyter notebook life_expectancy_gdp.ipynb
```

---

## Visualizaciones

- **Line plots**: Tendencias temporales de esperanza de vida y PIB por pais
- **Subplots individuales**: Evolucion por pais con cambio total anotado
- **Barplots comparativos**: Tasa de crecimiento de PIB y cambio en esperanza de vida
- **Boxplots y violin plots**: Distribucion de esperanza de vida por pais
- **Scatter plot**: PIB vs esperanza de vida con linea de regresion
- **Histogramas**: Comparacion alto vs bajo PIB

---

## Preguntas que responde este analisis

- La riqueza de un pais determina cuanto viven sus ciudadanos?
- Que pais mejoro mas su esperanza de vida en 15 anos?
- Es la relacion PIB-esperanza de vida lineal?
- Hay diferencia estadistica entre paises ricos y pobres en esperanza de vida?

---

**Autora:** Valentina Fandino
- GitHub: [@valentinafan](https://github.com/valentinafan)
