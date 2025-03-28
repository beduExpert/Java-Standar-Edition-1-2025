🏠 [**Inicio**](../Readme.md) ➡️ / 📖 `Sesión 07`

<div align="center">
    <img src="Imagenes/S07.jpg" alt="Sesion_07">
</div>

## 🎯 Objetivo

⚒️ Aprender a utilizar la API **java.nio.file (NIO.2)** para manejar archivos y directorios de forma eficiente y segura, comprendiendo desde las operaciones básicas de lectura y escritura hasta funciones avanzadas como copiar, mover, verificar permisos y aplicar buenas prácticas de manejo de archivos en Java.

---

📘 Material del prework:

Antes de comenzar con los ejercicios de esta sesión, recordemos que en el material de prework hemos cubierto los fundamentos teóricos que aplicaremos hoy. A lo largo de esta sesión, pondremos en práctica estos conceptos mediante una serie de ejercicios y retos diseñados para reforzar y validar nuestro entendimiento. 
🔥¡Vamos a comenzar!🔥

---

## 📂 Temas de la sesión...


### 📖 Introducción a `java.nio.file` (NIO.2)

Las colecciones permiten almacenar y manipular grupos de datos de manera eficiente.

La API NIO.2 ofrece una forma moderna y potente de trabajar con archivos y rutas en Java, utilizando las clases `Path` y `Files`.

- Diferencias entre IO y NIO.2
- Estructura del paquete `java.nio.file`
- Conceptos clave: rutas y operaciones


##### 📜 **[Introducción a java.nio.file (NIO.2)](Ejemplo-01/Readme.md)**
##### 🔥 **[Reto 01: ](Reto-01/Readme.md)**
---

### 📖 Lectura y escritura con `Files.readString()` y `Files.write()`

Dos métodos fundamentales para interactuar con archivos de texto:

- `Files.readString()`: lee todo el contenido de un archivo como `String`
- `Files.write()`: escribe contenido a un archivo, lo crea o sobrescribe


##### 📜 **[Ejemplo 02: Lectura y escritura con Files.readString() y Files.write()](Ejemplo-02/Readme.md)**
##### 🔥 **[Reto 02: ](Reto-02/Readme.md)**

---

### 📖 Manejo avanzado de archivos

Con NIO.2 puedes realizar operaciones esenciales para manipular archivos y directorios:

- `Files.copy()` y `Files.move()`
- Crear carpetas con `createDirectory()`
- Verificar permisos con `Files.isReadable()`, `isWritable()`, etc.

##### 📜 **[Ejemplo 03: Manejo avanzado de archivos](Ejemplo-03/Readme.md)**
##### 🔥 **[Reto 03:   ](Reto-03/Readme.md)**

---

### 📖 Buenas prácticas en manejo de archivos

Trabajar con archivos requiere planificación y prevención de errores:

- Manejo de excepciones con `try-catch`
- Uso de `try-with-resources`
- Mejora el rendimiento en archivos extensos con `BufferedReader`

##### 📜 **[Ejemplo 04: Buenas prácticas en manejo de archivos](Ejemplo-04/Readme.md)**
##### 🔥 **[Reto 04: Verificar y crear archivos de respaldo solo si no existen](Reto-04/Readme.md)**

---


⬅️ [**Anterior**](../Sesion-06/Readme.md) | [**Siguiente**](../Sesion-08/Readme.md)➡️
