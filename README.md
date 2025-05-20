
# 💱 Conversor de Monedas en Java


En este proyecto aprenderás a consumir APIs, analizar datos JSON y mostrar resultados relevantes para el usuario en Java.


## 🚀 Objetivo

Desarrollar una aplicación Java que permita convertir montos entre diferentes monedas usando una API de tasas de cambio en tiempo real.



## 🧰 Tecnologías utilizadas

* **Java 11 o superior**
* **Gson** – para el manejo de JSON
* **API HTTP Client** de Java
* **ExchangeRate-API** ([https://www.exchangerate-api.com/](https://www.exchangerate-api.com/))



## 📝 Pasos para completar el desafío

### 1. Configuración del ambiente Java

Asegúrate de tener instalado:

* JDK 11 o superior
* Un IDE como IntelliJ IDEA, Eclipse o VSCode
* Maven o Gradle (opcional, pero recomendado)



### 2. Creación del proyecto

Crea una estructura de proyecto Java estándar con paquetes como:

```
com/
├── model/
├── service/
├── exception/
```

Asegúrate de incluir la biblioteca Gson (`gson-<versión>.jar`) en tu classpath o utilizar un gestor de dependencias como Maven o Gradle.



### 3. Consumo de la API

Utiliza la clase `ApiService` para:

* Leer tu clave API desde un archivo `config.properties`
* Realizar una solicitud HTTP a la API de tasas de cambio
* Obtener los datos en formato JSON


### 4. Análisis de la respuesta JSON

Convierte la respuesta JSON en un objeto Java (`MoneyRate`) utilizando la biblioteca **Gson**:

```java
Gson gson = new GsonBuilder()
    .setFieldNamingPolicy(FieldNamingPolicy.LOWER_CASE_WITH_UNDERSCORES)
    .setPrettyPrinting()
    .create();

MoneyRate data = gson.fromJson(response.body(), MoneyRate.class);
```



### 5. Filtro de Monedas

Filtra y muestra únicamente las monedas de interés para el usuario (por ejemplo, USD, EUR, MXN, etc.), o permite al usuario elegir las monedas a convertir.



## 📂 Estructura esperada del proyecto

```
src/
├── main/
│   ├── java/
│   │   ├── com/
│   │   │   ├── model/
│   │   │   ├── service/
│   │   │   └── exception/
│   └── resources/
│       └── config.properties
```



## 🧪 Ejemplo de archivo `config.properties`

```properties
API_KEY=tu_api_key_aqui
```

Este archivo debe estar ubicado en `src/main/resources` y contener tu clave API válida para poder conectarse al servicio de tasas de cambio.


