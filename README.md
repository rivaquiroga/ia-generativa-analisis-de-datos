# IA generativa para análisis de datos

Taller realizado en el marco de la Escuela Doctoral Psicología UDP en julio de 2026. 

## Descripción

Este taller ofrece una introducción al uso de herramientas de inteligencia artificial generativa como apoyo para el análisis de datos en contextos académicos. Luego de revisar algunos principios básicos, incluyendo cómo estos modelos producen respuestas y cuáles son sus capacidades y limitaciones, se explorará su integración crítica en el análisis de datos mediante ejercicios prácticos en R. Además, se discutirán aspectos éticos relacionados con la privacidad, la confidencialidad y la protección de datos, así como criterios para evaluar la fiabilidad del código y los resultados generados. El objetivo es que los y las participantes incorporen criterios para utilizar estas herramientas de forma crítica y responsable en sus investigaciones.

## Preparación

### R y RStudio
Para poder realizar las actividades prácticas es necesario tener instalada una versión reciente de [R](https://cran.r-project.org/) y de [RStudio](https://docs.posit.co/ide/user/#rstudio-ide-oss-downloads). También es posible trabajar con la versión en la nube de RStudio, disponible en [Posit Cloud](https://posit.cloud/). La versión gratuita de Posit Cloud tiene algunas limitaciones de espacio y memoria RAM. 

Instalaremos los siguientes paquetes:

```
install.packages("ellmer")
install.packages("usethis")
install.packages("tidyverse")
```

### Quick Draw with Google

[quickdraw.withgoogle.com](https://quickdraw.withgoogle.com/)

### Gemini

Para los ejercicios del taller utilizaremos la capa gratuita de los modelos de Google Gemini. Las indicaciones para la configuración se encuentran [en este documento](https://github.com/rivaquiroga/ia-generativa-analisis-de-datos/blob/main/gemini-api-key.md).

## Datos

### Ejercicio 1: Crear datos sintéticos para generación de código

Trabajaremos con un diccionario de datos disponible en [Google Sheets](https://docs.google.com/spreadsheets/d/130wNaZeLyXyrXZiUu_ZG3GJevMei_xrsB4asO8htdpk/edit?usp=sharing).

### Ejercicio 2: Uso de {ellmer} para extraer datos

Primero, usaremos estos dos fragmentos.

Este es [el script que escribimos en la sesión](https://www.dropbox.com/scl/fi/fk0ziq9fidhoe2u2xav3r/ejemplo-uso-ellmer.R?rlkey=xu8oxzyarm2oi7tqj8v34efuk&dl=0).

```
perro_1 <- "Kiara es una perrita quiltra de aproximadamente 2 años. Pesa cerca de 22 kg y fue rescatada hace algunos meses tras ser encontrada deambulando por la ciudad. Es muy sociable con otros perros y convive bien con gatos. Tiene todas sus vacunas al día, está esterilizada y necesita una familia con experiencia en perros de alta energía."

perro_2 <- "Kaila es una perra salchicha de 5 años. Es muy inteligente y aprende con facilidad, pero puede mostrarse tímida con personas desconocidas durante los primeros días. Convive sin problemas con niños, aunque prefiere ser la única mascota del hogar. Está esterilizada y tiene su esquema de vacunación completo."

```

Luego, probaremos importando [un archivo con metadatos de artículos académicos](https://raw.githubusercontent.com/rivaquiroga/ia-generativa-analisis-de-datos/refs/heads/main/abstracts.csv) que se encuentra en este mismo repositorio. 


### Ejercicio 3: Comparar anotación automática vs. estándar de oro

(¡si alcanzamos!)

Anotaremos [una serie de titulares de forma manual en Google Sheets](https://docs.google.com/spreadsheets/d/1WAvlUMHCdyknR-4cm5IXwpd3QPTjcbFbUgoGmg1SKQQ/edit?usp=sharing). 

Y luego utilizaremos [el archivo csv que está en este mismo repositorio](https://raw.githubusercontent.com/rivaquiroga/ia-generativa-analisis-de-datos/refs/heads/main/abstracts.csv) para etiquetarlo con un modelo y comparar. 
