**🌐 Idioma:** [English](README_en.md) · Español

# Análisis del sistema Bicing de Barcelona (2020–2024)

Análisis exploratorio y visual del servicio público de bicicletas compartidas
de Barcelona, basado en un dataset de **223 millones de filas** repartidas en
ficheros anuales (2020–2024).

## Pipeline de datos

El proceso comenzó con la exploración individual de cada fichero anual:
eliminación de valores nulos, descarte de columnas irrelevantes y normalización
de esquemas para poder unir todos los años en un único dataset. Dado el volumen
de datos, el fichero resultante se compiló en **formato Parquet**, reduciendo
significativamente los tiempos de carga y procesamiento frente a trabajar con
ficheros CSV.

## Muestreo estratificado

Procesar el dataset completo para generar los mapas de calor no era viable en
memoria. Se construyó una **muestra de 10.000 registros** aplicando criterios de
estratificación por barrio, franja horaria y mes del año, garantizando que la
muestra siguiera siendo representativa de los patrones de uso reales.

## Variable proxy y limitación metodológica

El dataset no registra directamente si una bicicleta está en uso. Para
aproximarlo, se utilizó la diferencia entre la capacidad máxima de cada estación
y las bicicletas disponibles en cada momento como estimación de las bicicletas
en circulación. Este enfoque introduce un sesgo conocido: el sistema de furgonetas
que redistribuye las bicicletas entre estaciones puede crear huecos o excedentes
que no reflejan la demanda real.

## Hallazgo principal

A pesar de esta limitación, el análisis visual revela un patrón diferencial
consistente: los barrios costeros con menores niveles de renta concentran el uso
en las primeras horas de la mañana, mientras que los barrios más acomodados
muestran mayor actividad entre las 17:00 y las 19:00. El patrón se mantiene
estable en distintos días y meses, lo que sugiere que refleja un comportamiento
de movilidad real y no ruido operativo del sistema de redistribución.

## Estructura del repositorio

```
Script/                  notebooks de análisis (ver Script/README_es.md)
├── analisis exploratorio.ipynb   análisis exploratorio sobre el dataset completo
└── Sample 10K/                   flujo de trabajo con la muestra estratificada de 10k
Graphics/                gráficos interactivos en HTML (ver Graphics/README_es.md)
Presentación Pycing.pdf  presentación final del proyecto (PDF)
```

## Presentación final del proyecto

- [Presentación final del proyecto](https://www.canva.com/design/DAGmCY6ezpQ/jewSJEZVutvoF-PRD4fX7Q/edit?utm_content=DAGmCY6ezpQ&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton)

## Gráficos de la presentación final del proyecto (HTML)

- [Geolocalización de las estaciones Bicing](https://isanagui1818.github.io/analisis-bicing/Graphics/Geolocalizacion_estaciones_bicing.html)
- [Número de estaciones Bicing](https://isanagui1818.github.io/analisis-bicing/Graphics/Num_estaciones_bicing_interactivo.html)
- [Mapa de calor del uso de las bicicletas Bicing](https://isanagui1818.github.io/analisis-bicing/Graphics/Mapa_de_calor_uso_bicis.html)
- [Distritos por promedio de uso](https://isanagui1818.github.io/analisis-bicing/Graphics/Distritos_por_promedio_de_uso.html)
- [Grafo de red por distritos](https://isanagui1818.github.io/analisis-bicing/Graphics/grafo_red_distritos.html)
- [Diagrama de cajas: renta, distritos y horas de uso](https://isanagui1818.github.io/analisis-bicing/Graphics/diagrama_cajas_grupos_renta.html)

## Stack

Python · pandas · Parquet · Muestreo estratificado · Plotly · Folium · GeoPandas · Análisis exploratorio de datos

## Aviso legal

Proyecto académico de portfolio construido sobre fuentes abiertas de Bicing /
Open Data Barcelona. Compartido con fines educativos y de demostración.
