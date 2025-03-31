🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 `Prework sesión 07`

<div align="center">
    <img src="../Imagenes/S00.jpg" alt="Bedu | Haz + con tu talento | JAVA STANDARD EDITION I">
</div>

##### **PREWORK**
#### **🟧 Sesión 07**
#### **Colecciones y estructuras de datos**


##### 🔶 **Introducción** 

¡Bienvenido/a a la Sesión 07!  

En esta etapa del módulo te adentrarás en una de las herramientas más poderosas para trabajar con archivos y directorios en Java: **NIO.2**.

¿Te imaginas poder leer, escribir, copiar o mover archivos de forma sencilla y eficiente? Pues en esta sesión aprenderás justo eso, ¡y mucho más!  

Este prework te dará una primera mirada a los conceptos clave y te permitirá familiarizarte con las clases y métodos que usarás. La idea es que llegues a la sesión en vivo con una base sólida y listo para poner manos al código sin miedo.  

¡Prepárate para llevar tu conocimiento de Java al siguiente nivel! 🚀  

---

#### 🎯 Objetivo  

- Comprender qué es y para qué sirve la API `java.nio.file`(NIO.2).
- Familiarizarte con las funciones básicas para leer y escribir archivos usando `Files.readString()`y `Files.write()`.
- Explorar métodos avanzados para copiar, mover y gestionar archivos con seguridad.
- Conocer buenas prácticas para trabajar con archivos de forma eficiente y sin errores

---

#### 📋 Instrucciones  

Este Prework está diseñado para conocer el contenido que se practicará durante la sesión en vivo. **Por favor no lo omitas.**

Toma notas de lo que consideres relevante y guarda tus preguntas o dudas para resolverlas en la sesión.

Antes de arrancar, verifica que tu entorno de desarrollo esté listo. Es fundamental que tengas instalado IntelliJ IDEA Community Edition y el JDK (Java Development Kit) para trabajar sin interrupciones.

Si te surge alguna dificultad con la instalación o cualquier duda, no dudes en pedir ayuda a tu experto/a. ¡Estamos aquí para asegurarnos de que todo fluya sin problemas! 🚀

---

#### Bienvenido/a

Bienvenid@ al séptimo Prework del módulo. A continuación, te presentamos el tiempo estimado de lectura por tema, para que puedas revisar todos los recursos al máximo: 

| **📖 Temario**                                                                      | **🕰️ Tiempo sugerido** |
|--------------------------------------------------------------------------------------|------------------------|
| Tema 01. Introducción a `java.nio.file` (NIO.2)                                      | 5 min                  |
| Tema 02. Lectura y escritura de archivos con `Files.readString()` y `Files.write()`  | 5 min                  |
| Tema 03. Manejo avanzado de archivos (`Path`, `Files.copy()`, `Files.move()`)        | 5 min                  |
| Tema 04. Buenas prácticas en manejo de archivos                                      | 5 min                  |

**¡Comencemos! 🏁**

---
 
#### 📚 Tema 01. Introducción a `java.nio.file`(NIO.2)
##### ⏳ 5 minutos de lectura

¿Te ha pasado que trabajar con archivos en Java usando la clase `File` se siente algo limitado o confuso? ¡No estás solo! Por eso, desde Java 7 se introdujo una nueva forma de manejar archivos: la **API NIO.2**, a través del paquete `java.nio.file`.  

En esta sección conocerás cómo esta nueva API mejora y moderniza el manejo de archivos y rutas en Java. Aprenderás a utilizar clases como `Path` y `Files`, que te ofrecen una manera más clara, segura y flexible de interactuar con el sistema de archivos.  

La idea es que te familiarices con los conceptos básicos de esta API antes de pasar al código. Así, cuando llegues a la parte práctica, ya tendrás una visión general de cómo funciona todo.  

**Diferencias entre IO y NIO.2**  

Java tiene dos formas principales de trabajar con archivos: la antigua API IO y la más moderna NIO.2. Aquí te ayudamos a entender sus diferencias:  

| **Característica**       | **IO (`java.io`)**                    | **NIO.2 (`java.nio.file`)**                   |
|--------------------------|-------------------------------------|---------------------------------------------|
| Estilo de acceso         | Secuencial                          | Aleatorio y más flexible                    |
| Orientación              | Basada en streams                   | Basada en buffers y canales                 |
| Soporte para archivos    | Básico (lectura/escritura simple)   | Avanzado (copiar, mover, observar, etc.)    |
| Multithreading           | Menos eficiente                     | Mejor adaptado para operaciones en paralelo |
| Manejadores de rutas     | `File`                              | `Path`, `Files`, `FileSystems`, entre otros |
| Introducción             | Desde Java 1.0                      | Desde Java 7 (NIO.2)                        |

💡 ¿Por qué NIO.2?  
Porque es más moderna, flexible y eficaz. Te permite trabajar con archivos y directorios de forma más controlada y segura. 

**Estructura del paquete java.nio.file**

El paquete `java.nio.file`es parte de la nueva forma de manejar archivos y rutas en Java. Aquí tienes una vista general de los elementos clave que encontrarás:


```java
java.nio.file

├── Path                        -> Representa una ruta (a un archivo o directorio)
├── Files                       -> Provee métodos estáticos para operar archivos y rutas
├── FileSystems                 -> Permite acceder al sistema de archivos
├── StandardWatchEventKinds     -> Observa cambios en archivos/directorios
└── Paths (java.nio.file.Paths) -> Crea instancias de Path
```
🧩 Conceptos clave  
- `Path`: Es una representación de una ruta, como `"C:/archivos/miArchivo.txt"` o `"/home/usuario/documento.txt"`.
- `Files`: Una clase utilitaria que te ayuda a leer, escribir, copiar, mover y borrar archivos.
- `FileSystems`: Te conecta con el sistema de archivos actual.
- `WatchService` (opcional): Si en el futuro necesitas monitorear cambios, esta herramienta será tu aliada.

NIO.2 organiza las responsabilidades de manera más clara y modular, facilitando el mantenimiento del código y su evolución.  

**Primeros pasos con `Path` y `Files`**

Para empezar con NIO.2, hay dos clases que debes tener muy presentes:

| **Clase** | **¿Para qué sirve?**                                                                  |
|-----------|---------------------------------------------------------------------------------------|
| `Path`    | Para representar y manipular rutas del sistema de archivos.                           |
| `Files`   | Para realizar acciones sobre esas rutas, como leer, escribir o verificar si existen.  |


Ejemplo 

💡Imagínate que estás en tu computadora.

<table style="border-collapse: collapse;">
  <tr>
    <td style="border: 1px solid white; padding: 10px; vertical-align: top;">
      <img src="../Imagenes/S07_Fig1.png" alt="Persona trabajando en computadora" width="60">
    </td>
    <td style="border: 1px solid white; padding: 10px;">
      •	El `Path` sería como escribir la ruta en el explorador de archivos (ej. C:/documentos/tarea.txt).<br>
      •	La clase `Files` sería como las acciones que puedes hacer: abrir, copiar, mover o borrar ese archivo.<br>
    </td>
  </tr>
</table>

**📢Importante**  
No necesitas aprenderte todo de memoria. Lo más importante es que tengas clara la relación entre las rutas (`Path`) y las operaciones (`Files`).

---

#### 📚 Tema 02. Lectura y escritura de archivos con `Files.readString()`y `Files.write()` 
##### ⏳ 5 minutos de lectura

¿Sabías que con tan solo una línea de código puedes leer o escribir archivos de texto en Java? Con la API NIO.2, eso es totalmente posible gracias a los métodos `Files.readString()`y `Files.write()`.  

En esta sección te familiarizarás con estas funciones, que te permitirán trabajar con archivos de manera sencilla y directa. Aprenderás para qué sirve cada una, cómo se usan y qué debes tener en cuenta para evitar errores comunes.  
Antes de entrar al entorno de programación, es importante que comprendas *qué hace cada método, cuándo usarlos y cómo aplicarlos de forma segura y eficiente.*

**Cómo leer archivos con `Files.readString()`**  

`Files.readString()`es un método que te permite leer todo el contenido de un archivo como una cadena de texto.  

🎯 ¿Qué hace exactamente?  
Toma una ruta (representada como un objeto `Path`) y te devuelve el contenido completo del archivo como un solo `String`.

🤔¿Cuándo es útil?  
- Cuando necesitas cargar un archivo completo para analizarlo, mostrarlo en pantalla o procesarlo.
- Ideal para archivos de texto plano como .txt, .csv, .json, etc.

**💫 Concepto clave:**

<table style="border-collapse: collapse;">
  <tr>
    <td style="border: 1px solid white; padding: 10px; vertical-align: top;">
      <img src="../Imagenes/S07_Fig2.png" alt="foto instantánea" width="60">
    </td>
    <td style="border: 1px solid white; padding: 10px;">
      Piensa en `Files.readString()`como una "foto instantánea" del contenido del archivo. Es rápida y cómoda, pero debe usarse con cuidado en archivos muy grandes, ya que carga todo en memoria.
    </td>
  </tr>
</table>

**Escritura de archivos con `Files.write()`**

`Files.write()` es el complemento ideal para `readString()`. Con este método puedes guardar texto (o incluso datos binarios) dentro de un archivo.  

🤔 ¿Qué hace exactamente?
Toma una ruta (`Path`) y una secuencia de datos (`String`, `List`, o `byte[]`), y los escribe en el archivo indicado. Si el archivo no existe, lo crea. Si ya existe, puede sobrescribirlo o agregar contenido, según lo configures.  

🎯 ¿Cuándo es útil?  
- Cuando necesitas guardar resultados, reportes, logs o configuraciones generadas por tu programa.
- También puedes usarlo para actualizar archivos existentes.

💫 Concepto clave 
<table style="border-collapse: collapse;">
  <tr>
    <td style="border: 1px solid white; padding: 10px; vertical-align: top;">
      <img src="../Imagenes/S07_Fig3.png" alt="impresora digital" width="60">
    </td>
    <td style="border: 1px solid white; padding: 10px;">
      `Files.write()` es como una "impresora digital" para tus datos. Lo que tú envíes, se guarda. Solo asegúrate de no sobrescribir sin querer información importante.
    </td>
  </tr>
</table>

---

#### 📚 Tema 03. Manejo avanzado de archivos (`Path`, `Files.copy()`, `Files.move()`)
##### ⏳ 5 minutos de lectura  

Una vez que dominas la lectura y escritura de archivos, es momento de avanzar hacia otras operaciones. En esta sección aprenderás cómo copiar, mover, organizar y acceder a archivos y directorios usando las herramientas que te ofrece Java NIO.2.  

Con clases como `Path` y métodos como `Files.copy()` y `Files.move()`, podrás realizar tareas comunes del día a día en el desarrollo de software: respaldar archivos, organizar carpetas, procesar múltiples documentos, entre otras.  

Vamos paso a paso para que entiendas cómo aplicar estas funciones de forma correcta y segura.  

**Uso de `Files.copy()` y `Files.move()`**

Estos dos métodos te permiten realizar acciones muy comunes pero esenciales:

| **Método**        | **¿Qué hace?**                                       |
|-------------------|------------------------------------------------------|
| `Files.copy()`    | Copia un archivo de una ubicación a otra             |
| `Files.move()`    | Mueve (o renombra) un archivo o directorio           |

🎯 ¿Cuándo los usarías?
- Para hacer una copia de seguridad antes de modificar un archivo.
- Para reorganizar archivos según su tipo, fecha o contenido.
- Para cambiar el nombre de un archivo o moverlo de carpeta.

⚠️ Precaución  
Ambos métodos pueden sobrescribir archivos si no se configuran adecuadamente. Es importante revisar si el archivo de destino ya existe.

**📢Recuerda**: Estas operaciones funcionan con objetos `Path`, así que asegúrate de tener bien definida la ruta de origen y destino.  

**Cómo manejar directorios y listas de archivos**  

En muchas ocasiones, no trabajarás con un solo archivo, sino con *carpetas enteras* o conjuntos de archivos. Java NIO.2 también tiene herramientas para eso.  

🤔 ¿Qué puedes hacer?  
- Verificar si un directorio existe (`Files.exists()`).
- Crear carpetas nuevas (`Files.createDirectory()` o `createDirectories()`).
- Listar todos los archivos dentro de una carpeta usando `DirectoryStream`.

Ejemplo
<table style="border-collapse: collapse;">
  <tr>
    <td style="border: 1px solid white; padding: 10px; vertical-align: top;">
      <img src="../Imagenes/S07_Fig4.png" alt="carpeta de descargas" width="60">
    </td>
    <td style="border: 1px solid white; padding: 10px;">
      Imagina una carpeta de descargas. Puedes usar NIO.2 para listar todos los archivos .pdf, copiarlos a otra ubicación y borrar los duplicados. ¡Automatización al rescate!
    </td>
  </tr>
</table>

**💫 Tip**
Puedes combinar métodos como `Files.walk()` o `Files.list()` para recorrer estructuras de carpetas más complejas (aunque eso lo veremos más adelante).  

**Accesos y permisos en archivos**

No todos los archivos pueden ser leídos o modificados libremente. Por eso, es importante verificar los *permisos* de acceso antes de realizar operaciones.

| **Verificación**                 | **¿Para qué sirve?**                                |
|----------------------------------|-----------------------------------------------------|
| `Files.isReadable(path)`         | Saber si el archivo puede leerse                    |
| `Files.isWritable(path)`         | Ver si se puede escribir/modificar                  |
| `Files.isExecutable(path)`       | Verifica si el archivo puede ejecutarse             |
| `Files.isDirectory(path)`        | Confirma si es una carpeta o archivo                |

🛡️ ¿Por qué esto importa?
- Te ayuda a evitar errores por falta de permisos.
- Protege al sistema de operaciones no deseadas.
- Mejora la confiabilidad de tus programas.

📢 **Recuerda:** No todos los sistemas operativos manejan permisos de la misma forma. Lo que funciona en tu máquina puede comportarse distinto en otro entorno.

---

#### 📚 Tema 04. Buenas prácticas en manejo de archivos
##### ⏳ 5 minutos de lectura

Trabajar con archivos puede parecer simple, pero hacerlo de forma responsable es lo que marca la diferencia entre un código funcional y un código confiable.  

Estas recomendaciones aplican tanto para principiantes como para desarrolladores con experiencia. ¡Entre más pronto las apliques, mejor programador serás! 

**Buenas prácticas en el manejo de archivos de texto**

| **Práctica recomendada**                     | **¿Por qué es importante?**                               |
|----------------------------------------------|-----------------------------------------------------------|
| Verificar que el archivo exista              | Evitas errores al intentar leer archivos inexistentes     |
| Usar rutas absolutas solo para pruebas       | Las rutas relativas hacen tu código más portable          |
| Manejar excepciones (`try-catch`)            | Te protege ante errores como permisos o archivos vacíos   |
| No abrir archivos innecesariamente grandes   | Mejora el rendimiento y evita bloqueos de memoria         |
| Usar codificación estándar (UTF-8)           | Evitas problemas de caracteres no reconocidos             |

**💡 Tip**
Siempre que trabajes con archivos, pregúntate:

>"¿Qué pasaría si este archivo no existe, está vacío o es demasiado grande?"

Prepararte para esos escenarios es lo que te hará un mejor programador.

**Manejo seguro de excepciones en archivos**

Cuando trabajas con archivos, muchas cosas pueden salir mal:
- El archivo no existe
- No tienes permisos para acceder
- El disco está lleno
- El archivo está en uso por otro programa

Por eso, *siempre* debes manejar posibles errores usando estructuras de control como `try-catch`.  

🤔 ¿Por qué es importante?  
- Evita que tu programa se detenga de forma inesperada.
- Te permite dar mensajes claros al usuario.
- Puedes tomar decisiones alternativas (por ejemplo, crear el archivo si no existe).

🧠 *Piensa en esto como un cinturón de seguridad para tu código*: no siempre lo necesitas, pero cuando ocurre un error, ¡te salva!

**Uso eficiente de recursos con `try-with-resources`**

Cuando abres un archivo, estás usando un *recurso del sistema*. Si no lo cierras correctamente, puedes generar errores, consumir memoria innecesaria o incluso bloquear el acceso a otros programas.
Para evitar esto, Java te ofrece una forma elegante de trabajar con recursos: `try-with-resources`.  

❓ ¿Qué hace esta estructura?  
- Abre el recurso (como un archivo)
- Lo usa dentro del bloque try
- Lo cierra automáticamente al final, incluso si ocurre un error

**🔆 Ventaja**: No necesitas preocuparte por cerrar manualmente el archivo con .close() Java lo hace por ti.

>💡 Este patrón no solo es útil con archivos, también se aplica a conexiones de base de datos, sockets, y más.

**Consejos para mejorar el rendimiento en operaciones de archivos**

Si bien las operaciones con archivos son sencillas, cuando trabajas con muchos datos o archivos grandes, es importante optimizar tu código.

Aquí tienes algunos consejos prácticos:

| **Consejo**                                       | **¿Por qué es útil?**                                          |
|---------------------------------------------------|----------------------------------------------------------------|
| Evita leer archivos enormes en memoria completa   | Reduce el consumo de memoria y mejora la velocidad             |
| Usa `BufferedReader` para lectura por líneas      | Mejora el rendimiento en archivos extensos                     |
| Revisa si el archivo cambió antes de reescribir   | Evitas trabajo innecesario y prolongas la vida útil del disco  |
| Usa rutas relativas en lugar de absolutas         | Facilita la portabilidad y mantenimiento del código            |
| Centraliza la lógica de manejo de archivos        | Reduce duplicación y mejora la legibilidad                     |

🤓🧠 *Piensa como un programador eficiente*: cada línea que optimizas hoy puede ahorrarte muchos problemas mañana.

---

#### 🧠 Actividad de reforzamiento

**Descripción de la actividad**
Imagina que estás creando un programa muy simple para guardar notas personales en archivos `.txt`. El usuario podrá:
1. Crear una nueva nota (archivo de texto).
2. Leer el contenido de una nota.
3. Copiar una nota a una carpeta de respaldo.
4. Mover una nota a una carpeta de archivo.
5. Verificar si una nota es legible o modificable.

⚠️ En esta actividad NO necesitas codificar todavía. El objetivo es pensar y planear cómo lo harías utilizando los conceptos aprendidos.

**Instrucciones**

1. **Analiza el siguiente escenario**
Tienes una carpeta llamada `notas/` y dentro de ella vas a guardar tus archivos de texto. También tienes dos carpetas adicionales:
    - `respaldo/` → para copias de seguridad
    - `archivo/` → para mover notas antiguas

2. **Responde las siguientes preguntas**
a) ¿Qué clases y métodos de NIO.2 usarías para crear un archivo con una nueva nota?
b) ¿Cómo leerías el contenido de una nota usando `Files.readString()`?
c) Si quieres hacer una copia de una nota antes de modificarla, ¿qué método usarías? ¿Cómo te asegurarías de no sobrescribirla sin querer?
d) ¿Qué pasos seguirías para mover una nota antigua a la carpeta `archivo/`?
e) ¿Qué métodos utilizarías para comprobar si una nota es legible y escribible antes de trabajar con ella?
f) ¿Qué excepción podría lanzarse si la nota no existe? ¿Cómo la manejarías?

3. **Reto adicional**
Investiga cómo listar todas las notas dentro de la carpeta `notas/` y qué clase podrías usar para recorrerlas una por una.

---

#### 📝 Cierre

¡Felicidades! 🎉 Has llegado al final del prework de esta sesión, y con ello has dado un paso importante hacia el dominio del manejo de archivos en Java usando **NIO.2**.

Ahora ya tienes una visión clara de:
- Las diferencias entre IO y NIO.2
- Cómo se estructura el paquete `java.nio.file`
- Cómo leer y escribir archivos de forma sencilla
- Cómo copiar, mover y organizar archivos y carpetas
- Y lo más importante: cómo hacerlo todo **de forma segura, ordenada y eficiente**

Este conocimiento será clave en muchos de los proyectos que desarrolles en el futuro, ya que prácticamente cualquier aplicación profesional necesita interactuar con archivos de alguna manera.

**🚀 Recuerda:** cada archivo que manipulas con inteligencia y cuidado es una señal de que estás creciendo como desarrollador.  

¡Nos vemos en la sesión con el experto/a! 💻✨

---

⬅️ [**Anterior**](../../Sesion-06/Prework/Readme.md) | [**Siguiente**](../../Sesion-08/Prework/Readme.md)➡️