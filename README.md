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

#### KPI_1
**Objetivo:**
* Reducir en un 10% la tasa de homicidios en siniestros viales de los últimos seis meses, en CABA, en comparación con la tasa de homicidios en siniestros viales del semestre anterior.

<p align="center">
    <img src= "images\kpi_1.png"
</p>


Este KPI se enfoca en medir la evolución de la tasa de homicidios en siniestros viales en la Ciudad Autónoma de Buenos Aires (CABA) en un período de varios años, comparando los dos últimos semestres. Análisis más detallado:

* **Tendencia general:** La tendencia en este KPI varía año tras año. En algunos años, se logra una disminución significativa, mientras que en otros se observa un aumento en la tasa de homicidios en siniestros viales.

* **Año 2020:** Se destaca un aumento significativo en la tasa de homicidios en el primer semestre (61.29%), pero una mejora en el segundo semestre (10%), lo que puede ser atribuible a factores específicos, como el impacto de la pandemia o medidas de seguridad vial.

* **Año 2021:** Los datos parecen estar incompletos, ya que falta información para el segundo semestre. Esto puede dificultar una evaluación precisa del rendimiento en ese año.

* **Comparación entre semestres:** En algunos casos, se logra la reducción deseada del 10% entre semestres, mientras que en otros no se alcanza.

* **Análisis de causas:** Sería útil profundizar en las razones detrás de las variaciones en la tasa de homicidios en siniestros viales, como cambios en las políticas de seguridad vial, mejoras en la infraestructura vial, o la influencia de eventos externos como la pandemia.

#### KPI_2
**Objetivo:**
* Reducir en un 7% la cantidad de accidentes mortales de motociclistas en el último año, en CABA, respecto al año anterior.

<p align="center">
    <img src= "images\kpi_2.png"
</p>


Este KPI se centra en evaluar la evolución de la cantidad de accidentes mortales de motociclistas en la Ciudad Autónoma de Buenos Aires (CABA) en un período de varios años, comparando los dos últimos años. Análisis más detallado:

* **Tendencia general:** En este KPI, también se observa una variación año tras año, con fluctuaciones tanto positivas como negativas.

* **Año 2020:** Destaca un aumento significativo del 58.62% en la cantidad de accidentes mortales de motociclistas, lo que podría requerir una atención inmediata para comprender las razones detrás de este aumento.

* **Año 2021:** Al igual que en el KPI 1, faltan datos para el año 2021 en este KPI, lo que dificulta una evaluación precisa.

* **Comparación anual:** La reducción del 7% en la cantidad de accidentes mortales de motociclistas es el objetivo, pero no siempre se logra. Por ejemplo, en el año 2019, se observa una disminución significativa del 42%.

* **Análisis de causas:** Para entender las fluctuaciones en este KPI, sería importante analizar factores como las medidas de seguridad específicas para motociclistas, el aumento en la cantidad de motociclistas en la ciudad y la aplicación de políticas de tráfico.






**Autor:**
Leopoldo Martin Farah Cometti
correo: leopoldomartinfarah@gmail.com
Fecha: Diciembre 2023
 
