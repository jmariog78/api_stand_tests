# Pruebas Automatizadas de API: Creación de Usuarios

Este proyecto contiene un conjunto de pruebas automatizadas en Python orientadas a validar el comportamiento del endpoint de creación de usuarios, enfocándose específicamente en las reglas de negocio del parámetro `firstName`.

---

## 🛠️ Requisitos Previos

Antes de ejecutar las pruebas, asegúrate de tener instalado Python 3.x en tu sistema. Además, es necesario instalar las dependencias del proyecto ejecutando el siguiente comando en tu terminal:

```bash
pip install pytest requests
```

## 🛠️ Tecnologías Utilizadas

Este proyecto fue desarrollado utilizando el siguiente stack tecnológico enfocado en pruebas automatizadas y control de versiones:

* **Python 3.x**: Lenguaje de programación principal para la lógica de los scripts de prueba.
* **Pytest**: Entorno y framework de pruebas encargado de ejecutar y validar las aserciones de los casos de prueba.
* **Requests**: Biblioteca HTTP de Python empleada para enviar las solicitudes (`POST`, `GET`, etc.) y gestionar las respuestas de la API.
* **Git**: Herramienta de control de versiones utilizada para el seguimiento de cambios y manejo del historial del código.
* **GitHub**: Plataforma de alojamiento para el almacenamiento, documentación y visualización del repositorio del proyecto.

## 🗂️ Estructura del Proyecto

* **`configuration.py`**: Almacena las constantes de configuración, como la URL base del servidor (*URL_SERVICE*) y las rutas de los endpoints (*CREATE_USER_PATH*).
* **`data.py`**: Contiene los diccionarios y cuerpos de datos en formato JSON necesarios para realizar las solicitudes HTTP.
* **`sender_stand_request.py`**: Contiene las funciones lógicas encargadas de realizar las peticiones HTTP (`POST`, `GET`, etc.) utilizando la librería `requests`.
* **`create_user_test.py`**: Archivo principal que aloja las pruebas unitarias y los casos de prueba (tanto positivos como negativos) para el parámetro `firstName`.

---

## 🚀 Ejecución de las Pruebas

Para ejecutar el conjunto completo de pruebas y verificar los resultados, abre la terminal en la raíz del proyecto y ejecuta:

```bash
pytest
```

Si deseas obtener un reporte detallado de cada caso de prueba ejecutado, utiliza el modo detallado (*verbose*):

```bash
pytest -v
```

---

## 📋 Escenarios de Prueba para el Parámetro "firstName"

El suite de pruebas automatizadas valida las reglas de negocio del campo `firstName` durante el proceso de registro y creación de un nuevo usuario, dividiéndose en los siguientes escenarios:

### Casos Positivos (Respuesta esperada: 201 Created)
* **Caso 1**: Registro exitoso con la longitud mínima permitida para el nombre (2 caracteres, Ej: `"Aa"`).
* **Caso 2**: Registro exitoso con la longitud máxima permitida para el nombre (15 caracteres, Ej: `"Aaaaaaaaaaaaaaa"`).

### Casos Negativos (Respuesta esperada: 400 Bad Request)
* **Caso 3**: Error al intentar registrar un nombre que excede el límite permitido (16 caracteres).
* **Caso 4**: Error al intentar registrar un nombre que contiene espacios intermedios (Ej: `"A Aaa"`).
* **Caso 5**: Error al intentar registrar un nombre que contiene símbolos o caracteres especiales (Ej: `'"№%",'`).
* **Caso 6**: Error al intentar registrar un nombre compuesto por dígitos numéricos (Ej: `"123"`).
* **Caso 7**: Error al omitir por completo el parámetro obligatorio `firstName` en el cuerpo de la solicitud JSON.
* **Caso 8**: Error al enviar el parámetro `firstName` como una cadena de texto totalmente vacía (`""`).
* **Caso 9**: Error de tipo al pasar un valor numérico entero (Ej: `12`) en lugar del tipo de dato cadena (*string*).
