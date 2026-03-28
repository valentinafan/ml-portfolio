# Biodiversidad en Parques Nacionales de Estados Unidos

Analisis de conservacion de 5,824 especies en 4 parques nacionales para identificar patrones de riesgo y priorizar monitoreo.

---

## Descripcion

Este proyecto explora los datos de biodiversidad del Servicio de Parques Nacionales (NPS) para responder preguntas criticas de conservacion: que tipos de especies estan en mayor riesgo? Donde debemos concentrar los esfuerzos de monitoreo? Existe un sesgo taxonomico en los programas de proteccion?

El analisis confirma que las aves y mamiferos reciben desproporcionadamente mas atencion de conservacion, mientras que ciertas especies amenazadas tienen niveles alarmantemente bajos de observacion.

---

## Objetivo

- Analizar la distribucion del estado de conservacion entre las 5,824 especies
- Determinar si ciertos tipos de organismos tienen mayor probabilidad de estar en peligro
- Comparar la biodiversidad y frecuencia de observacion entre los 4 parques
- Identificar las especies amenazadas que necesitan monitoreo mas urgente
- Preparar los datos para un futuro modelo de clasificacion

---

## Dataset

| Atributo | Descripcion |
|----------|-------------|
| **Fuente** | National Park Service (NPS) - Servicio de Parques Nacionales |
| **Tamano** | 5,824 especies + 23,296 registros de observaciones |
| **Tipo** | Categorico y numerico |
| **Variables** | Nombre cientifico, categoria, estado de conservacion, parque, observaciones |

**Archivos:**
- `species_info.csv`: Informacion taxonomica y estado de conservacion de cada especie
- `observations.csv`: Conteo de observaciones por especie y parque

---

## Metodologia

### Tecnicas Principales

1. **Test Chi-cuadrado de Independencia**
   - Evalua si la relacion entre tipo de especie y estado de conservacion es estadisticamente significativa
   - Resultado: Chi² = 628.58, p < 0.001

2. **Analisis de Crosstabs**
   - Tablas cruzadas entre categoria taxonomica y estado de conservacion
   - Heatmap de porcentajes para visualizar sesgos

3. **Analisis de Prioridad de Monitoreo**
   - Especies amenazadas/en peligro con menor numero de observaciones
   - Ranking de urgencia basado en visibilidad

### Pasos del Analisis

1. Carga y merge de los dos datasets
2. Tratamiento de valores nulos en conservacion (5,633 NaN → "No Concern")
3. Analisis de distribucion del estado de conservacion
4. Test Chi-cuadrado: tipo de especie vs estado de conservacion
5. Biodiversidad por parque (especies unicas vs observaciones)
6. Identificacion de especies con monitoreo urgente
7. Preparacion de features para clasificacion ML

---

## Resultados

### Hallazgos Principales

- Solo el **3.3%** de las especies esta en alguna categoria de riesgo
- Existe una relacion **altamente significativa** entre tipo de especie y estado de conservacion (p < 0.001)
- Los 4 parques comparten las **mismas 5,541 especies** — la diferencia esta en la frecuencia de observacion

### Estadisticas Clave

| Metrica | Valor |
|---------|-------|
| Total de especies | 5,824 |
| Especies en riesgo | 191 (3.3%) |
| Chi-cuadrado | 628.58 |
| p-value | 2.46e-117 |
| Parque con mas observaciones | Yellowstone (~1.6M) |

### Insights

1. **Sesgo taxonomico en conservacion:** Aves y Mamiferos representan el 100% de las especies "In Recovery", pero son una fraccion minima del total de especies. Las plantas vasculares, que dominan el ecosistema, estan subrepresentadas en programas de proteccion.
2. **Yellowstone como lider en monitoreo:** Con ~1.6M observaciones totales, Yellowstone tiene la mejor cobertura de monitoreo, posiblemente por mayor inversion o accesibilidad.
3. **Especies invisibles en peligro:** Las especies con menos observaciones (como Grus americana) son las mas vulnerables y las mas dificiles de monitorear.

---

## Conclusiones

### Resumen

La biodiversidad en los parques nacionales es rica pero desigualmente monitoreada. Existe un claro sesgo hacia la proteccion de aves y mamiferos (especies mas "visibles"), mientras que las plantas y otros organismos reciben menos atencion a pesar de ser fundamentales para los ecosistemas.

### Recomendaciones

- Ampliar programas de monitoreo para plantas vasculares y otros grupos subrepresentados
- Priorizar las 15 especies con menores observaciones identificadas en este analisis
- Estandarizar el esfuerzo de monitoreo entre los 4 parques

### Limitaciones

- Los datos no incluyen esfuerzo de muestreo (un parque con mas observaciones puede tener mas rangers, no mas biodiversidad)
- La clasificacion "No Concern" para valores nulos es una suposicion
- No se analiza la tendencia temporal de las observaciones

---

## Tecnologias Utilizadas

- **Python 3.x** - Lenguaje de programacion
- **Pandas** - Manipulacion y merge de datos
- **NumPy** - Operaciones numericas
- **Matplotlib & Seaborn** - Visualizacion (heatmaps, barplots)
- **SciPy** - Test Chi-cuadrado de independencia
- **Jupyter Notebook** - Entorno interactivo

---

## Estructura del Proyecto

```
04-biodiversity-national-parks/
├── biodiversity.ipynb      # Notebook principal
├── species_info.csv        # Datos de especies
├── observations.csv        # Datos de observaciones
└── README.md               # Este archivo
```

---

## Como Usar

```bash
cd ml-portfolio/04-biodiversity-national-parks
pip install pandas numpy matplotlib seaborn scipy
jupyter notebook biodiversity.ipynb
```

---

## Visualizaciones

- **Barplot + Pie chart**: Distribucion del estado de conservacion
- **Heatmap**: Porcentaje de estado de conservacion por tipo de especie
- **Barplots por parque**: Total de observaciones y desglose por categoria
- **Barplot horizontal**: Top 15 especies con monitoreo mas urgente

---

## Preguntas que responde este analisis

- Que porcentaje de especies esta en riesgo de extincion?
- Ciertos tipos de organismos tienen mayor probabilidad de estar en peligro?
- Que parque tiene la mayor actividad de observacion?
- Cuales especies necesitan monitoreo mas urgente?

---

**Autora:** Valentina Fandino
- GitHub: [@valentinafan](https://github.com/valentinafan)
