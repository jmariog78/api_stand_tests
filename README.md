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

## 📋 Casos de Prueba Cubiertos

El script de pruebas valida los siguientes escenarios para el campo `firstName`:
1. **Valores válidos**: Cadenas de texto con longitudes permitidas (por ejemplo, límites mínimos y máximos de caracteres).
2. **Valores inválidos**: Cadenas vacías, valores nulos (`None`), tipos de datos incorrectos (números o booleanos) o longitudes que exceden el límite permitido.
