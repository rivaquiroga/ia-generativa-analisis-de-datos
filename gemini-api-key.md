# Configuración de Google Gemini

En este taller utilizaremos **Google Gemini** como proveedor de modelos de lenguaje. Google ofrece una capa gratuita que nos servirá para realizar algunos de los ejercicios. 


## Paso 1. Obtener una API key

Para poder utilizar los modelos que ofrece Google, necesitaremos crear una "API key" siguiendo los siguientes pasos: 


1. Abre https://aistudio.google.com/api-keys
2. Inicia sesión con tu cuenta de Google si aún no lo has hecho.
3. Haz clic en **Create API key** / **Crear clave de API**.
4. Te pedirá que selecciones un proyecto de Google Cloud. Puedes crear uno nuevo si no tienes ninguno.
5. Una vez creada, copia la API key y guárdala en un lugar seguro.

> **⚠️ Importante:** La API Key funciona como una contraseña. No la compartas con nadie.

## Paso 2. Configurar la API Key en R

Para que R pueda conectarse a Gemini, necesita conocer tu API Key. En lugar de escribir la clave dentro de cada script de R (lo que es poco práctico y puede exponerla accidentalmente), la guardaremos como una **variable de entorno**. 

Una **variable de entorno** es un dato que R puede leer automáticamente al iniciar una sesión. Se utiliza habitualmente para almacenar información sensible, como contraseñas, tokens o API keys.

R guarda estas variables en un archivo llamado **`.Renviron`**, que se carga automáticamente cada vez que inicias R. Esto significa que solo tendrás que configurar la API key una vez en tu computador.

### 1. Instalar `usethis`

Si aún no lo tienes instalado, ejecuta:

```r
install.packages("usethis")
```

### 2. Abrir el archivo `.Renviron`

Ejecuta:

```r
usethis::edit_r_environ()
```

Si es la primera vez que lo haces, R creará el archivo automáticamente.

### 3. Agregar la API Key

Añade una línea como la siguiente:

```text
GEMINI_API_KEY=TU_API_KEY
```

Reemplaza `TU_API_KEY` por la clave que obtuviste en Google AI Studio.

Por ejemplo:

```text
GEMINI_API_KEY=AIzaSy...
```

### 4. Guardar y reiniciar R

Guarda el archivo y reinicia R (o RStudio).

A partir de ese momento, R podrá encontrar automáticamente tu API Key sin que tengas que escribirla nuevamente en tus scripts.

### ¿Qué ocurre si en el futuro genero una nueva API Key?

Si por cualquier motivo decides crear una nueva API key (por ejemplo, porque la revocaste o creaste una nueva en Google AI Studio), solo debes:

1. volver a ejecutar

```r
usethis::edit_r_environ()
```

2. reemplazar la clave antigua por la nueva;

3. guardar el archivo y reiniciar R.

No será necesario modificar ninguno de tus scripts de R.

> **⚠️ Importante:** Nunca incluyas tu API Key directamente en un script de R. 
