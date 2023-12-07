# Accidentes viales en la Ciudad Autónoma de Buenos Aires 

## Introducción

En el contexto de una ciudad como Buenos Aires, los siniestros viales pueden ser una preocupación importante debido al alto volumen de tráfico y la densidad poblacional. Estos incidentes pueden tener un impacto significativo en la seguridad de los residentes y visitantes de la ciudad, así como en la infraestructura vial y los servicios de emergencia.

Las tasas de mortalidad relacionadas con siniestros viales suelen ser un indicador crítico de la seguridad vial en una región. Estas tasas se calculan, generalmente, como el número de muertes por cada cierto número de habitantes o por cada cierta cantidad de vehículos registrados. Reducir estas tasas es un objetivo clave para mejorar la seguridad vial y proteger la vida de las personas en la ciudad.

En este contexto, surge nuestro proyecto individual, una iniciativa que busca utilizar el poder de los datos y el análisis para abordar el desafío de los siniestros viales en la Ciudad de Buenos Aires. En colaboración con el Observatorio de Movilidad y Seguridad Vial (OMSV), nos hemos propuesto la tarea de analizar a fondo los incidentes de tráfico ocurridos en los últimos años. Nuestro objetivo es claro: generar información valiosa que permita a las autoridades locales tomar medidas efectivas para reducir la cantidad de víctimas fatales en estos incidentes.

## Objetivo

El objetivo del proyecto "Siniestros Viales" es abordar el problema de los accidentes de tráfico o siniestros viales en la Ciudad de Buenos Aires desde la perspectiva de un Data Analyst. El proyecto tiene como contexto el alto volumen de tráfico y la densidad poblacional en la ciudad, lo que aumenta la preocupación por la seguridad vial.

El rol a desarrollar en este proyecto implica colaborar con el Observatorio de Movilidad y Seguridad Vial (OMSV) bajo la órbita de la Secretaría de Transporte del Gobierno de la Ciudad Autónoma de Buenos Aires. El objetivo principal es analizar un conjunto de datos sobre homicidios en siniestros viales ocurridos en la Ciudad de Buenos Aires durante el período 2016-2021. A partir de este análisis, se busca generar información que permita a las autoridades locales tomar medidas efectivas para reducir la cantidad de víctimas fatales en siniestros viales.

El proyecto se divide en varias etapas, que incluyen la Extraccion, Transformacion y Carga de los datos (ETL) referidos a siniestros viales en CABA, seguido de un Análisis Exploratorio de Datos (EDA), la medición y representación de KPI's relacionados con la seguridad vial, la creación de un Dashboard interactivo donde podamos visualizar como actuan dichos KPI's y posteriormente la creación de un repositorio en GitHub que incluye un informe de análisis basado en los dashboards y los KPIs.

En resumen, el objetivo principal del proyecto es utilizar el análisis de datos para contribuir a la reducción de la cantidad de víctimas fatales en siniestros viales en la Ciudad de Buenos Aires, brindando información valiosa a las autoridades para la toma de decisiones en materia de seguridad vial.

## Tecnologías usadas para el análisis de los datos

* Jupyter Notebook
* Python
* Numpy
* Pandas
* Matplotlib
* VS Code
* Markdown
* Git
* Github

## ETL

Durante la fase de transformación y limpieza de datos (ETL), se han aplicado una serie de pasos esenciales para garantizar la calidad y coherencia de los datos. Estas acciones buscan preparar el conjunto de datos de manera óptima para su análisis posterior.

**1. Eliminación de Duplicados y verificamos tipo de datos por cada tabla:** Para asegurar la unicidad de las filas en el conjunto de datos, se han eliminado los duplicados y verificando tipos de datos para cada tabla.

**2. Eliminación de nulos y columnas:** Se procedio a ver los nulos dentro del conjunto de datos, notamos que una de las columnas contenia mas del 70% de datos nulos, luego de analizar la importancia de dicha columna, se decide eliminarla. Luego seguimos analizando las columnas que no eran necesarias para nuestro análisis y descartamos las innecesarias.

**3. Cambiamos el nombre de columnas:** Se decide cambiar el nombre de varias columnas con el objetivo de tener una visualizacion de los datos mas homogenea.

**4. Se hace un merge de 2 conjuntos de datos:** Se procede hacer el merge de dos dataframes distintos, con el objetivo de tener una disposicion mas completa del conjunto de datos para el análisis posterior.

**5. Creacion de nuevas columnas:** Luego de hacer el merge de ambos dataframe, se decide eliminar columnas duplicadas y luego se procede a la creacion de nuevas columnas que seran de utilidad a la hora de la creacion de los KPI's.

**6. Guardado de los dataset:** Una vez terminado el proceso de limpieza y transformacion de los datos, se procede a guardarlos en formato .CSV

## EDA

Una vez limpio el conjunto de datos, se procede a hacer un análisis del conjunto de los datos con el fin de ver la correlacion entre estos. El primer paso fue separar nuestras variables categóricas de las Numéricas.

#### **Variables Categóricas**
* **ID:** Identificador unico del siniestro
* **FECHA:** Fecha del siniestro
* **LUGAR_DEL_HECHO:** Direccion del siniestro
* **TIPO_DE_CALLE:** Tipo de arteria. 
* **CALLE:** Nombre de la arteria donde se produjo el siniestro.
* **DIRECCIÓN NORMALIZADA:** Direccion en formato normalizado USIG.
* **COMUNA:** Comuna de la ciudad (1 a 15)
* **XY (CABA):** Geocodificacion plana.
* **PARTICIPANTES:** Conjuncion de victima y acusado
* **ACUSADO:** Vehiculo que ocupaba quien resulto acusado/a del siniestro.
* **ROL:** Posicion relativa al vehiculo que presentaba la victima en el momento del siniestro.
* **VICTIMA:** Vehiculo que ocupaba quien haya fallecido o se haya lastimado durante el siniestro.
* **SEXO:** Sexo de la victima.
* **FECHA_FALLECIMIENTO:** Fecha de fallecimiento de la victima.

#### Variables Numéricas
* **N_VICTIMAS:** Cantidad de victimas en el siniestro.
* **AAAA:** Año que ocurrio el siniestro.
* **MM:** Mes que ocurrio el siniestro. 
* **FRANJA_HORARIA:** Franja horaria.
* **POS X:** Longitud con separador punto. WGS84
* **POS Y:** Latitud con separador punto. WGS84
* **EDAD:** Edad de la victima al momento del siniestro.

#### Análisis Univariado
**Objetivo:**
* Calcular estadísticas descriptivas básicas, como la media, la mediana, la desviación estándar, los percentiles, etc., para cada variable numérica.
* Obtener conteos y proporciones para variables categóricas.
* Crear gráficos y visualizaciones por variable para comprender la distribución de los datos.
* Identificar valores atípicos (outliers) que puedan requerir una atención especial.

#### `N_VICTIMAS`

<p align="center">
    <img src= "images\output.png"
</p>

**Conclusiones [N_VICTIMAS]**
* Solo hay 3 posibilidades de victimas por accidente: 1, 2, 3
* La media del numero de victimas por accidente es aproximadamente 1.06, lo que indica que en promedio, la mayoria de los accidentes tienen una sola victima.
* mayor frecuencia de vicitmas por accidente es de: 1 (94.28%)
* menor frecuencia de victimas por accidente es de : 3 (0.42%)

#### `VICTIMA`

<p align="center">
    <img src= "images\conteo_tipo_victima.png"
</p>

**Conclusiones [VICTIMA]**
* Existen 8 tipos diferentes de victimas involucradas.
* El valor mas frecuente es 'MOTO'. Esto quiere decir que 'MOTO' es el tipo de victima mas frecuente en los siniestros viales.
* hay 303 accidentes donde el tipo 'MOTO' estuvo involucrado, esto representa el 42.26% del total de accidentes viales.
* Victima con mayor frecuencia es: 'MOTO' (42.26%)
* Victima con menor frecuencia es: 'MOVIL' (0.42%)

#### `ACUSADO`

<p align="center">
    <img src= "images\conteo_acusado.png"
</p>

**Conclusiones [ACUSADO]**
* Existen 10 registros únicos dentro de la columna 'ACUSADO'. Esto significa que existen 10 tipos diferentes de vehiculos acusados en los siniestros viales.
* El valor mas frecuente en la columna 'ACUSADO' es 'AUTO'. Esto significa que 'AUTO' es el vehiculo acusado con la mayor cantidad de siniestros viales. se pueden contar 208 siniestros a manos de este vehiculo.
* Acusado con mayor frecuencia: 'AUTO' (29.01%)
* Acusado con menor frecuencia: 'TREN' (0.14%)

#### `AAAA`

<p align="center">
    <img src= "images\siniestro_anio.png"
</p>


**Conclusiones [AAAA]**
* Hay 6 registros únicos dentro de la columna 'AAAA'. Esto hace referencia a los años 2016 a 2021.
* (Cuartiles): Estos valores representan los cuartiles del conjunto de datos. Por ejemplo, el valor del primer cuartil (25%) es 2017, lo que significa que el 25% de los accidentes ocurrieron en 2017 o antes. El segundo cuartil (50%) es 2018, que es la mediana, indicando que el 50% de los accidentes ocurrieron en 2018 o antes. El tercer cuartil (75%) es 2019, lo que sugiere que el 75% de los accidentes ocurrieron en 2019 o antes.
* Año con mayor frecuencia de siniestros: 2018 (20.78%)
* Año con menor frecuencia de siniestros: 2020 (11.30%) 

#### `SEMESTRE`

<p align="center">
    <img src= "images\conteo_semestre.png"
</p>

**Conclusiones [SEMESTRE]**
* Como podemos observar, el valor mas frecuente corresponde al del segundo semetre de cada año, lo que sugiere que la mayoria de los siniestros se generan en el segundo semetre. 
* El segundo semetre cuenta con el 51.61% de los registros, mientras que el primer semetre cuenta con el 48.39% de los registros.

#### `TIPO_DE_CALLE`

<p align="center">
    <img src= "images\conteo_calle.png"
</p>

**Conclusiones [TIPO_DE_CALLE]**
* Tenemos 4 registros únicos dentro de la columna 'TIPO_DE_CALLE'. Estos hacen referencias a las diferentes arterias dentro de CABA. Cabe recalcar que 'GRAL PAZ' es tanto una avenida como tambien una autopista en ciertas partes, por ese motivo la dejamos como un registro unico.
* El valor mas frecuente corresponde a 'AVENIDA', ya que en esta ocurren la mayoria de los siniestrios con un valor de 442.
* La arteria con mayor frecuencia de siniestros es: AVENIDA (61.65%)
* La arteria con menor frecuencia de siniestros es: AUTOPISTA (9.48%)


#### `COMUNA`

<p align="center">
    <img src= "images\conteo_comuna.png"
</p>

**Conclusiones [COMUNA]**
* Contamos con 16 registros únicos para la columna 'COMUNA'. Esto hace referencia a las 15 comunas dentro de CABA, desde la 0 a la 15.
* Como podemos ver la frecuencia de siniestros es mayor en la comuna 1 con 93 siniestros, seguido de la comuna 4 con 79.
* La comuna con mayor frecuencia de siniestros es: 1 (12.97%)
* La comuna con menor frecuencia de siniestros es: 0 (0.28%)

#### `SEXO`

<p align="center">
    <img src= "images\sexo.png"
</p>

**Conclusiones [SEXO]**
* Contamos con 3 registros únicos. Dichos registros hacen referencia a 'MASCULINO', 'FEMENINO' Y 'SD', este ultimo son las personas que no se encontraron datos de su sexo, pero teniendo en cuenta la frecuencia de estas, las dejamos ya que no representan un cambio en el analisis.
* Como podemos observar el dato mas frecuente es 'MASCULINO' con 545 siniestros viales.
* El sexo con mayor frecuencia es: MASCULINO (76.01%)
* El sexo con menor frecuencia es: FEMENINO (23.15%)

## KPI's

Dentro del Notebook `KPIs.ipynb` se encontrara todo lo relacionado a los 2 KPI propuestos por el Observatorio de Movilidad y Seguridad Vial (OMSV).
En esta etapa, mientras estaba haciendo los ultimos cambios y los push pertinentes, cometi un error y borre todo el archivo `KPIs.ipynb` al querer hacer un git restore. esto sucedio 1 hora antes de tener que entregar el proyecto, por eso es que dentro de este archivo encontraras la lectura de los df pertinentes a cada KPI. El proceso de la creacion de estos df no esta documentado ya que fue borrado al hacer le git restore y como no contaba con el tiempo para hacerlo de nuevo, decidi cargar los df que ya tenia guardados y presentar los graficos y conclusiones solamente. 

Cabe recalcar que en la creacion de dichos df, me base en el dataset `PBP_CO_1020.xls` el cual lo consegui de la siguiente fuente:
https://www.estadisticaciudad.gob.ar/eyc/?p=28146

Habiendo aclarado mi error, estare haciendo un commit en las horas proximas para documentar como fue el proceso de creado de los dataframes `df_kpi_1` y `df_kpi_2`.

#### KPI_1
**Objetivo:**
* Reducir en un 10% la tasa de homicidios en siniestros viales de los últimos seis meses, en CABA, en comparación con la tasa de homicidios en siniestros viales del semestre anterior.

<p align="center">
    <img src= "images\kpi1.png"
</p>

**Conclusiones:**

1. Dado que no tenemos datos previos al año 2016-1 nuestra primer medida relaciona el semestre 2016-1 y 2016-2 por eso solo se evidencian valores a partir del semestre 2016-2.

2. Si el valor del semestre en la gráfica es positivo significa que para ese semestre hubo menos homicidios que el semestre pasado.

3. Si la gráfica tiene pendiente positiva (creciente) significa que la diferencia de accidentes vs. el semestre anterior aumentó de manera positiva.

4. El valor que se representa en la gráfica indica el porcentaje en que se redujo la tasa de homicidios en accidentes de tránsito del semestre anterior vs. el actual. Dado que el objetivo es que dicho valor sea superior al 10% se puede concluir que en el periodo de 6 años comprendido entre 2016 y 2021 se cumplió para los semestres:

* 2017-1: En comparación con el semestre anterior se redujeron los homicidios y ese numero fue mayor que el logrado el semestre anterior.

* 2019-1: En comparación con el semestre anterior se redujeron los homicidios y ese numero fue mayor que el logrado el semestre anterior.

* 2019-2: En comparación con el semestre anterior se redujeron los homicidios y ese numero fue menor que el logrado el semestre anterior.

* 2021-2: En comparación con el semestre anterior se redujeron los homicidios y ese numero fue mayor que el logrado el semestre anterior.

5. 4 semestres de 11 cumplieron el objetivo lo cual nos indica que no es positivo el balance de acuerdo a lo planteado inicialmente

6. 5 semestres de 11 tienen un porcentaje de cambio negativo, es decir, aumenta la tasa de homicidios vs. el semestre anterior. Aunque es minoría sigue siendo alarmante la cantidad


#### KPI_2
**Objetivo:**
* Reducir en un 7% la cantidad de accidentes mortales de motociclistas en el último año, en CABA, respecto al año anterior.

<p align="center">
    <img src= "images\kpi2.png"
</p>

**Conclusiones:**

1. Dado que no tenemos datos previos al año 2016 nuestra primer medida relaciona el año 2016 y 2017 por eso solo se evidencian valores a partir del año 2017.

2. Si el valor del año en la gráfica es positivo significa que para ese año hubo menos homicidios que el año pasado.

3. Si la gráfica tiene pendiente positiva (creciente) significa que la diferencia de accidentes de motos vs. el año anterior aumentó de manera positiva.

4. El valor que se representa en la gráfica indica el porcentaje en que se redujo la cantidad de homicidios en accidentes de motos del año anterior vs. el actual. Dado que el objetivo es que dicho valor sea superior al 7% se puede concluir que en el periodo de 6 años comprendido entre 2016 y 2021 se cumplió para los años:

* 2017: En comparación con el año anterior se redujeron los homicidios y dado que no tenemos valores para el año anterior no podemos decir si fue mayor o menor respecto de ese año.

* 2019: En comparación con el año anterior se redujeron los homicidios y ese numero fue mayor que el logrado el año anterior.

* 2020: En comparación con el año anterior se redujeron los homicidios y ese numero fue mayor que el logrado el año anterior.

5. 3 años de 5 cumplieron el objetivo lo cual nos indica que es positivo el balance de acuerdo a lo planteado inicialmente

6. 2 años de 5 tienen un porcentaje de cambio negativo, es decir, aumenta la tasa de accidentes en moto vs. el año anterior. Aunque es minoría sigue siendo alarmante la cantidad







**Autor:**
Leopoldo Martin Farah Cometti
correo: leopoldomartinfarah@gmail.com
Fecha: Diciembre 2023
 
