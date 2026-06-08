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

# Presentación proyecto final:
- [Presentación proyecto final](https://www.canva.com/design/DAGmCY6ezpQ/jewSJEZVutvoF-PRD4fX7Q/edit?utm_content=DAGmCY6ezpQ&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton)

# Gráficos presentación proyecto final en formato html:
- [Geolocalización estaciones Bicing](https://isanagui1818.github.io/Proyecto-final-bootcamp/Gráficos/Geolocalizacion_estaciones_bicing.html)
- [Numero estaciones bicing](https://isanagui1818.github.io/Proyecto-final-bootcamp/Gráficos/Num_estaciones_bicing_interactivo.html)
- [Mapa de calor uso bicis bicing](https://isanagui1818.github.io/Proyecto-final-bootcamp/Gráficos/Mapa_de_calor_uso_bicis.html)
- [Distritos por promedio de uso](https://isanagui1818.github.io/Proyecto-final-bootcamp/Gráficos/Distritos_por_promedio_de_uso.html)
- [Grafico red por distritos](https://isanagui1818.github.io/Proyecto-final-bootcamp/Gráficos/grafo_red_distritos.html)
- [Boxplot renta, distritos, horas de uso](https://isanagui1818.github.io/Proyecto-final-bootcamp/Gráficos/diagrama_cajas_grupos_renta.html)


