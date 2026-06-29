**🌐 Language:** English · [Español](README_es.md)

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

## Repository layout

```
Script/                  analysis notebooks (see Script/README_en.md)
├── analisis exploratorio.ipynb   exploratory analysis on the full dataset
└── Sample 10K/                   10k stratified-sample workflow
Graphics/                interactive HTML charts (see Graphics/README_en.md)
Presentación Pycing.pdf  final project presentation (PDF)
```

## Final project presentation

- [Final project presentation](https://www.canva.com/design/DAGmCY6ezpQ/jewSJEZVutvoF-PRD4fX7Q/edit?utm_content=DAGmCY6ezpQ&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton)

## Graphics for the final project presentation (HTML)

- [Bicing stations geolocation](https://isanagui1818.github.io/analisis-bicing/Graphics/Geolocalizacion_estaciones_bicing.html)
- [Number of Bicing stations](https://isanagui1818.github.io/analisis-bicing/Graphics/Num_estaciones_bicing_interactivo.html)
- [Bicing bike usage heatmap](https://isanagui1818.github.io/analisis-bicing/Graphics/Mapa_de_calor_uso_bicis.html)
- [Districts by average usage](https://isanagui1818.github.io/analisis-bicing/Graphics/Distritos_por_promedio_de_uso.html)
- [Network graph by districts](https://isanagui1818.github.io/analisis-bicing/Graphics/grafo_red_distritos.html)
- [Boxplot: income, districts and usage hours](https://isanagui1818.github.io/analisis-bicing/Graphics/diagrama_cajas_grupos_renta.html)

## Tech stack

Python · pandas · Parquet · Stratified Sampling · Plotly · Folium · GeoPandas · Exploratory Data Analysis

## Disclaimer

Academic portfolio project built on open Bicing / Open Data Barcelona sources.
Shared for educational and demonstration purposes.
