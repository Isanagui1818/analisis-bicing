# Análisis del sistema Bicing de Barcelona (2020–2024)

Análisis exploratorio y visual del uso del servicio de bicicletas públicas 
de Barcelona a partir de un dataset de **223 millones de filas** distribuidas 
en archivos anuales (2020–2024).

## Pipeline de datos

El proceso comenzó con la exploración individual de cada archivo anual: 
eliminación de valores nulos, descarte de columnas irrelevantes y normalización 
de esquemas para hacer posible el merge de todos los años en un único dataset. 
Dado el volumen de datos, el archivo resultante se compiló en formato **Parquet**, 
lo que redujo significativamente los tiempos de carga y procesamiento respecto 
al trabajo con CSV.

## Muestreo estratificado

Para la generación de los mapas de calor, trabajar con el dataset completo 
resultaba inviable en memoria. Se construyó un **sample de 10.000 registros** 
con criterios de estratificación por barrio, hora del día y mes del año, 
garantizando que la muestra fuera representativa de los patrones reales de uso.

## Variable proxy y limitación metodológica

El dataset no registra directamente si una bicicleta está en uso. Para 
aproximarlo, se calculó la diferencia entre la capacidad máxima de cada 
estación y las bicicletas disponibles en cada momento, tomando esa diferencia 
como estimación de bicis en circulación. Esta aproximación introduce un sesgo 
conocido: el sistema de furgonetas que redistribuye bicicletas entre estaciones 
puede generar huecos o excedentes que no reflejan demanda real.

## Hallazgo principal

A pesar de esta limitación, el análisis visual revela un patrón diferencial 
consistente: los barrios costeros de renta más baja concentran el uso en las 
primeras horas de la mañana, mientras que los barrios de renta alta muestran 
mayor actividad en la franja de 17h–19h. El patrón se mantiene estable a lo 
largo de distintos días y meses, lo que sugiere que responde a comportamientos 
reales de movilidad más que al ruido operacional del sistema.

---
<br>
🇺🇸 English version
<sub><img src="https://flagcdn.com/16x12/us.png" alt="US"> English version</sub>


# Bicing Barcelona System Analysis (2020–2024)

Exploratory and visual analysis of Barcelona's public bike-sharing service
based on a dataset of **223 million rows** across annual files (2020–2024).

## Data Pipeline

The process started with individual exploration of each annual file:
removing null values, dropping irrelevant columns, and normalising schemas
to enable merging all years into a single dataset. Given the data volume,
the resulting file was compiled into **Parquet format**, significantly
reducing load and processing times compared to working with CSV files.

## Stratified Sampling

Processing the full dataset for heat map generation was not feasible in
memory. A **10,000-record sample** was built using stratification criteria
by neighbourhood, time of day, and month of year, ensuring the sample
remained representative of real usage patterns.

## Proxy Variable and Methodological Limitation

The dataset does not directly record whether a bike is in use. To
approximate this, the difference between each station's maximum capacity
and available bikes at any given moment was used as an estimate of bikes
in circulation. This approach introduces a known bias: the van system that
redistributes bikes between stations can create gaps or surpluses that do
not reflect real demand.

## Key Finding

Despite this limitation, the visual analysis reveals a consistent
differential pattern: coastal neighbourhoods with lower income levels
concentrate usage in the early morning hours, while wealthier
neighbourhoods show higher activity between 17:00–19:00. The pattern holds
stable across different days and months, suggesting it reflects real
mobility behaviour rather than operational noise from the redistribution
system.

# Presentación proyecto final:
- [Presentación proyecto final](https://www.canva.com/design/DAGmCY6ezpQ/jewSJEZVutvoF-PRD4fX7Q/edit?utm_content=DAGmCY6ezpQ&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton)

# Gráficos presentación proyecto final en formato html:
- [Geolocalización estaciones Bicing](https://isanagui1818.github.io/Proyecto-final-bootcamp/Gráficos/Geolocalizacion_estaciones_bicing.html)
- [Numero estaciones bicing](https://isanagui1818.github.io/Proyecto-final-bootcamp/Gráficos/Num_estaciones_bicing_interactivo.html)
- [Mapa de calor uso bicis bicing](https://isanagui1818.github.io/Proyecto-final-bootcamp/Gráficos/Mapa_de_calor_uso_bicis.html)
- [Distritos por promedio de uso](https://isanagui1818.github.io/Proyecto-final-bootcamp/Gráficos/Distritos_por_promedio_de_uso.html)
- [Grafico red por distritos](https://isanagui1818.github.io/Proyecto-final-bootcamp/Gráficos/grafo_red_distritos.html)
- [Boxplot renta, distritos, horas de uso](https://isanagui1818.github.io/Proyecto-final-bootcamp/Gráficos/diagrama_cajas_grupos_renta.html)


