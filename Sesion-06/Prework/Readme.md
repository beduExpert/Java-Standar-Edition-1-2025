🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 `Prework sesión 06`

<div align="center">
    <img src="../Imagenes/S00.jpg" alt="Bedu | Haz + con tu talento | JAVA STANDARD EDITION I">
</div>

##### **PREWORK**
#### **🟧 Sesión 06**
#### **Colecciones y estructuras de datos**


##### 🔶 **Introducción**  

¡Bienvenido/a a la Sesión 06! 

En esta sesión, aprenderás a manejar listas, conjuntos y mapas de manera eficiente, entendiendo sus diferencias, ventajas y los casos en los que cada uno brilla. Exploraremos desde las diferencias entre `ArrayList`, `HashSet` y `HashMap`, hasta cómo ordenar colecciones con `Comparator` y `Comparable`. También darás tu primer vistazo a las colecciones concurrentes, fundamentales en aplicaciones de alto rendimiento.

**🚨 Consejo**: Lee, experimenta y prepárate con preguntas. ¡Mientras más practiques, más provecho sacarás a la sesión en vivo!

¡Es hora de dar el siguiente paso en tu camino con Java! 🚀🔥

---

#### 🎯 Objetivo  

- Comprender y utilizar las colecciones en Java (`List`, `Set`, `Map`), identificando sus características y aplicaciones en distintos escenarios.
- Diferenciar entre `ArrayList`, `HashSet` y `HashMap`, comprendiendo cuándo y por qué elegir cada estructura según las necesidades del programa.
- Aplicar técnicas de ordenamiento en colecciones utilizando las interfaces `Comparator` y `Comparable` para mejorar la organización y búsqueda de datos.
- Explorar las colecciones concurrentes en Java (`ConcurrentHashMap`, `CopyOnWriteArrayList`) y su importancia en el desarrollo de aplicaciones multihilo.

---

#### 📋 Instrucciones  

Este Prework está diseñado para conocer el contenido que se practicará durante la sesión en vivo. **Por favor no lo omitas.**

Toma notas de lo que consideres relevante y guarda tus preguntas o dudas para resolverlas en la sesión.

Antes de arrancar, verifica que tu entorno de desarrollo esté listo. Es fundamental que tengas instalado IntelliJ IDEA Community Edition y el JDK (Java Development Kit) para trabajar sin interrupciones.

Si te surge alguna dificultad con la instalación o cualquier duda, no dudes en pedir ayuda a tu experto/a. ¡Estamos aquí para asegurarnos de que todo fluya sin problemas! 🚀

---

**Bienvenido/a**  

Bienvenid@ al sexto Prework del módulo. A continuación, te presentamos el tiempo estimado de lectura por tema, para que puedas revisar todos los recursos al máximo: 

| **📖 Temario**                                                              | **🕰️ Tiempo sugerido** |
|-----------------------------------------------------------------------------|----------------------|
| Tema 01. Introducción a las colecciones (`List`, `Set`, `Map`)             | 3 min               |
| Tema 02. Diferencias entre `ArrayList`, `HashSet` y `HashMap`              | 5 min               |
| Tema 03. Ordenamiento de colecciones con `Comparator` y `Comparable`       | 5 min               |
| Tema 04. Introducción a colecciones concurrentes (`ConcurrentHashMap`, `CopyOnWriteArrayList`) | 5 min |

**¡Comencemos! 🏁**

---
 
#### 📚 Tema 01. Introducción a las colecciones (`List`, `Set`, `Map`)
##### ⏳ 3 minutos de lectura.

Piensa que estás desarrollando una aplicación en Java y necesitas almacenar muchos datos del mismo tipo: nombres, productos, números, objetos... ¿Qué harías? ¿Crearías una variable para cada uno? 😰  

¡Claro que no! Para eso existen las *colecciones*, uno de los pilares más importantes del lenguaje Java.  

En esta sección, descubrirás los tres tipos más comunes de colecciones en Java:  

- `List`: cuando importa el orden y puedes tener duplicados.
- `Set`: cuando necesitas elementos únicos.
- `Map`: cuando cada elemento tiene una clave y un valor.

Vamos paso a paso para entenderlas y ver cómo pueden ayudarte en tus propios proyectos.  

**¿Qué es una colección?**

En Java, una colección es una estructura que te permite *almacenar, organizar y manipular un grupo de elementos* (como objetos, números, cadenas, etc.).  

🤔 ¿Para qué te sirve?  
En vez de crear múltiples variables para guardar datos similares, puedes usar una colección para mantenerlos todos juntos y trabajar con ellos de forma más eficiente.

Ejemplo  

💡Imagina que tienes una caja con boletos.

<table style="border-collapse: collapse;">
  <tr>
    <td style="border: 1px solid white; padding: 10px; vertical-align: top;">
      <img src="../Imagenes/S06_Fig1.jpg" alt="tickets" width="60">
    </td>
    <td style="border: 1px solid white; padding: 10px;">
      Con una colección, puedes guardar todos los boletos en una misma caja.<br>
      Puedes revisar, ordenar, buscar o quitar boletos fácilmente sin tener que revisar uno por uno en diferentes lugares.
    </td>
  </tr>
</table>

**Diferencias clave entre `List`, `Set`, `Map`**

Te presento una tabla comparativa sencilla para que comprendas sus diferencias de forma visual:  

| **Colección** | **Permite duplicados**  | **Mantiene orden**              | **Clave-Valor** | **¿Cuándo usarla?**   |
|---------------|-------------------------|---------------------------------|-----------------|-----------------------|
| `List`        | ✅ Sí                  | ✅ Sí                           | ❌ No          | Cuando necesitas una lista ordenada y puedes tener elementos repetidos. *Ej: lista de tareas.* |
| `Set`         | ❌ No                   | ❌ No (aunque depende del tipo) | ❌ No          | Cuando necesitas elementos únicos. *Ej: lista de correos únicos.* | |
| `Map`         | ✅ (en valores)         | ⚠️ (depende del tipo)         | ✅ Sí          | Cuando necesitas asociar una clave con un valor. *Ej: ID de empleado y su nombre.* |



**🧐💡 Dato curioso**: Map no es técnicamente parte de la interfaz Collection, ¡pero se estudia junto con ellas porque cumple una función parecida!  

**📚 Lo que debes llevarte de esta sección**  
- Una colección te ayuda a agrupar datos y manejarlos de forma eficiente.
- `List`, `Set`, `Map` son los tres grandes tipos que usarás frecuentemente.
- Cada uno tiene su propósito: orden, unicidad o asociación clave-valor.
- Aprender a elegir la colección correcta te hace escribir código más limpio y eficiente.

---

#### 📚 Tema 02. Diferencias entre `ArrayList`, `HashSet` y `HashMap`
##### ⏳ 5 minutos de lectura

En Java, `ArrayList`, `HashSet` y `HashMap` son estructuras de datos ampliamente utilizadas. Cada una tiene características específicas que las hacen más adecuadas según el caso de uso.

Características principales y diferencias fundamentales

Para visualizar mejor las diferencias, aquí tienes una tabla comparativa:

| **Estructura** | **Tipo de colección** | **Permite duplicados**  | **Mantiene orden**| **Acceso por índice** | **Uso de clave-valor** |
|----------------|-----------------------|-------------------------|-------------------|-----------------------|------------------------|
| `ArrayList`    | `List`                | ✅ Sí                   | ✅ Sí            | ✅ Sí                 | ❌ No                 |
| `HashSet`      | `Set`                 | ❌ No                   | ❌ No            | ❌ No                 | ❌ No                 |
| `HashMap`      | `Map`                 | ✅ (en valores)         | ❌ No            | ❌ No                 | ✅ Sí                 |


📌 Explicación  

- `ArrayList`: Es una lista ordenada que permite elementos duplicados. Ideal cuando necesitas mantener el orden de inserción y acceder a los elementos por su posición.  
- `HashSet`: Es un conjunto que no permite duplicados y no garantiza orden. Útil cuando solo importa la presencia de elementos únicos.  
- `HashMap`: Es una estructura clave-valor donde cada clave es única. Se usa cuando necesitas asociar datos (ejemplo: DNI → Nombre).  

**Ventajas y desventajas de cada estructura**

| **Estructura** | ✅ **Ventajas**                                | ⚠️ **Desventajas**                   |
|----------------|------------------------------------------------|---------------------------------------|
| `ArrayList`    | - Acceso rápido a elementos por su índice  <br> - Permite elementos duplicados y mantiene el orden de inserción  <br> - Más eficiente en lectura y búsqueda por posición que `LinkedList` | - Inserciones y eliminaciones intermedias pueden ser costosas <br> - Usa más memoria que arreglos tradicionales |
| `HashSet`      | - No permite duplicados, ideal para manejar valores únicos <br> - Operaciones de búsqueda y eliminación más rápidas que en `ArrayList` en grandes volúmenes de datos | - No mantiene el orden de los elementos <br> - No permite acceder a elementos por índice                   |
| `HashMap`      | - Acceso rápido a valores mediante claves <br> - Muy eficiente en operaciones de búsqueda y actualización <br> - Permite almacenar grandes volúmenes de datos de manera organizada | - No mantiene el orden de inserción (a menos que uses `LinkedHashMap`) <br> - Mayor consumo de memoria en comparación con `ArrayList` y `HashSet` |

**Implementación básica de `ArrayList`, `HashSet` y `HashMap`**  

Aunque este prework es más teórico, es importante que veas cómo se declaran estas estructuras para que puedas familiarizarte con su sintaxis:  

📌 Ejemplo simple de cada estructura  

| **Estructura** | **Implementación común**                                            |
|----------------|---------------------------------------------------------------------|
| `ArrayList`    | `ArrayList<String> lista = new ArrayList<>();`                      |
| `HashSet`      | `HashSet<String> conjunto = new HashSet<>();`                       |
| `HashMap`      | `HashMap<Integer, String> mapa = new HashMap<>();`                  |

**💡 Recuerda:** Cada una de estas estructuras tiene otras variantes (como `LinkedList`, `TreeSet`, `TreeMap`), pero empezaremos con las más utilizadas para que te familiarices con sus conceptos básicos.  

**📚 Lo que debes llevarte de esta sección**  

- `ArrayList`, `HashSet` y `HashMap` tienen propósitos distintos.
  - Si el orden es importante → usa `ArrayList`.
  - Si necesitas valores únicos → usa `HashSet`.
  - Si necesitas pares clave-valor → usa `HashMap`.


**💫 Consejo clave:** Cada estructura tiene ventajas y desventajas, por lo que elegir la correcta depende de tu caso de uso.

---

#### 📚 Tema 03. Ordenamiento de colecciones con `Comparator` y `Comparable`
##### ⏳ 5 minutos de lectura

Ordenar una colección significa *organizar sus elementos de acuerdo con un criterio*: alfabéticamente, numéricamente, por fecha, etc.  

En colecciones como `ArrayList`, este orden es *modificable*, y puedes definirlo tú mismo. Ya sea que quieras ordenar una lista de productos por precio o una lista de estudiantes por apellido, Java te da herramientas para hacerlo: `Comparable` y `Comparator`.  

📌Ejemplo

<table style="border-collapse: collapse;">
  <tr>
    <td style="border: 1px solid white; padding: 10px; vertical-align: top;">
      <img src="../Imagenes/S06_Fig2.jpg" alt="paquetes" width="60">
    </td>
    <td style="border: 1px solid white; padding: 10px;">
      Piensa en una lista desordenada de paquetes que necesitas organizar por peso o tamaño. Con estas herramientas, puedes definir cómo se deben ordenar.
    </td>
  </tr>
</table>

**¿Qué es `Comparable` y cómo usarlo para ordenar objetos?**  

`Comparable` es una *interfaz* que se implementa directamente en una clase para *definir un orden natural* entre objetos.

📌Ejemplo  

Supón que tienes una clase `Libro`. Si implementas `Comparable`, puedes decirle a Java:

>*🔠 "Los libros deben ordenarse por título de forma alfabética"*

🗝️ Características clave de `Comparable`  

| **Característica**         | **Detalle**                                 |
|----------------------------|---------------------------------------------|
| ¿Dónde se implementa?      | Dentro de la clase del objeto               |
| ¿Cuántos criterios admite? | Solo uno (el "orden natural")               |
| Método principal           | `compareTo()`                               |

🧠 Úsalo cuando:  
- El orden siempre será el mismo (ej. nombre, ID, fecha).
- Quieres que los objetos *se ordenen automáticamente* al usar métodos como `Collections.sort()`.

**Uso de `Comparator` para ordenar de manera personalizada**  

`Comparator` también es una interfaz, pero se utiliza cuando *necesitas diferentes formas de ordenar* los objetos *desde fuera de la clase*.  

📌Ejemplo

Sigamos con el ejemplo de `Libro`. Ahora quieres ordenar la misma lista de libros, pero esta vez por número de páginas.

Con `Comparator`, puedes crear una regla de ordenamiento externa sin modificar la clase `Libro`.

🗝️ Características clave de `Comparator`  

| **Característica**         | **Detalle**                                   |
|----------------------------|-----------------------------------------------|
| ¿Dónde se implementa?      | En una clase externa o como función anónima   |
| ¿Cuántos criterios admite? | ¡Los que tú definas!                          |
| Método principal           | `compare()`                                   |

🧠Úsalo cuando:  
- Necesitas más de un criterio de ordenamiento.  
- No puedes o no quieres modificar la clase original.  
- Requieres ordenamientos dinámicos, como "por precio ascendente" o "por nombre descendente".  

**Ejemplos prácticos con `ArrayList`**  

Aunque aquí no desarrollaremos el código completo, te damos una visión general de lo que podrías hacer con ambas interfaces en un `ArrayList`:

| **Objetivo**                                                | **Estructura usada**    | **Método de ordenamiento**  |
|-------------------------------------------------------------|-------------------------|-----------------------------|
| Ordenar una lista de estudiantes por nombre (orden natural) | `ArrayList<Estudiante>` |`Comparable`                 |
| Ordenar una lista de productos por precio de menor a mayor  | `ArrayList<Producto>`   | `Comparator`                |
| Ordenar una lista de libros por año de publicación, descendente | `ArrayList<Libro>`  | `Comparator` con lógica personalizada|

>🚨 En la sesión en vivo, verás cómo estos métodos se aplican en código real para que puedas practicarlo por ti mismo.

**📚 Lo que debes llevarte de esta sección**  
- El ordenamiento permite organizar datos de forma lógica y útil.
- Usa `Comparable` para definir un *único orden natural dentro de la clase*.
- Usa `Comparator` cuando necesites *flexibilidad o múltiples criterios*.
- `ArrayList` es una estructura perfecta para practicar ordenamientos.

---

#### 📚 Tema 04. Introducción a colecciones concurrentes (`ConcurrentHashMap`, `CopyOnWriteArrayList`)
##### ⏳ 5 minutos de lectura

Cuando ejecutas una aplicación en Java, normalmente se ejecuta en un solo hilo de ejecución (thread). Sin embargo, en programas más complejos (como servidores, videojuegos, o aplicaciones de red), varios hilos trabajan al mismo tiempo. Esto se llama *concurrencia*.  

🤔 ¿Dónde está el problema?  
Cuando varios hilos acceden a la misma colección al mismo tiempo, pueden ocurrir errores como:  
- Lecturas de datos incompletos o erróneos.
- Modificaciones inesperadas.
- Bloqueos o fallos.

📌Ejemplo

<table style="border-collapse: collapse;">
  <tr>
    <td style="border: 1px solid white; padding: 10px; vertical-align: top;">
      <img src="../Imagenes/S06_Fig3.jpg" alt="Trabajo simultaneo" width="60">
    </td>
    <td style="border: 1px solid white; padding: 10px;">
      Imagina que tú y otra persona intentan escribir en el mismo documento al mismo tiempo. Sin coordinación, uno puede sobrescribir lo que el otro hizo.
    </td>
  </tr>
</table>

**Diferencia entre colecciones tradicionales y concurrentes**

| **Característica**      | **Colecciones tradicionales** <br>(`ArrayList`, `HashMap`)    | **Colecciones concurrentes** <br>(`CopyOnWriteArrayList`, `ConcurrentHashMap`) |
|-------------------------|-----------------------------------------------------------|----------------------------------------------------------------------------|
| ¿Son seguras en entornos multihilo?         | ❌ No                                | ✅ Sí                                                                      |
| ¿Pueden causar errores de concurrencia?     | ✅ Sí                                | ❌ No                                                                      |
| ¿Rendimiento en entorno con un solo hilo?   | ✅ Más rápido                        | ⚠️ Ligeramente más lento (por el control de concurrencia)                  |
| ¿Manejo automático de sincronización?       | ❌ No                                | ✅ Sí                                                                      |

✨ Conclusión
- Usa colecciones concurrentes si tu aplicación trabaja con múltiples hilos que acceden a los mismos datos.
- Usa colecciones tradicionales si no necesitas ese tipo de procesamiento.

**Ejemplos básicos en acción**  

Aquí te explico qué hace cada colección concurrente de forma simple:

**🔹 `CopyOnWriteArrayList`**  

Es una versión de `ArrayList` diseñada para trabajar con múltiples hilos.
Cada vez que se modifica la lista, *se crea una copia nueva* de la misma.

💡 Ideal para:  
- Listas donde se leen muchos datos, pero se modifican pocas veces.
- Aplicaciones en las que varios hilos leen la misma lista al mismo tiempo.

📦 Ejemplo: Lista de usuarios conectados en un chat.  

**🔹 `ConcurrentHashMap`**  
Es una versión segura de `HashMap` que permite que *múltiples hilos lean* y escriban sin interferirse.  

💡 Ideal para:  
- Situaciones donde muchos hilos necesitan acceder o modificar datos clave-valor al mismo tiempo.
- Reemplazo de `HashMap` en entornos multihilo.  

📦 Ejemplo: Almacenar configuraciones personalizadas por usuario en un sistema web.  

**📚 Lo que debes llevarte de esta sección**  
- La concurrencia permite que varios hilos trabajen al mismo tiempo.
- Las colecciones tradicionales no son seguras en estos entornos.
- Java ofrece versiones concurrentes como `CopyOnWriteArrayList` y `ConcurrentHashMap` para evitar errores.
- Usar estas colecciones te permite desarrollar aplicaciones más seguras y robustas en escenarios multihilo.  

---

#### 🧠 Actividad de reforzamiento

**Instrucciones**: Lee cada enunciado y responde si es Verdadero (V) o Falso (F). Luego, revisa la respuesta y justifícala.

| **#** | **Enunciado**                                                                         | **Respuesta** | **Justificación** |
|------|----------------------------------------------------------------------------------------|---------------|-------------------|
| 1    | Un `ArrayList` mantiene el orden de inserción y permite elementos duplicados.          |               |                   |
| 2    | Un `HashSet` permite almacenar elementos duplicados.                                   |               |                   |
| 3    | `HashMap` organiza los datos en pares clave-valor.                                     |               |                   |
| 4    | `Comparable` se usa para ordenar objetos de diferentes clases.                         |               |                   |
| 5    | `Comparator` te permite definir múltiples formas de ordenar una colección sin modificar la clase original.|   |            |
| 6    | `Collections.sort()` no puede usarse con objetos personalizados.                       |               |                   |
| 7    | Las colecciones tradicionales como `ArrayList` o `HashMap` son seguras para entornos multihilo.|       |                   |
| 8    | `CopyOnWriteArrayList` es eficiente cuando se realizan muchas modificaciones en la lista.      |       |                   |
| 9    | `ConcurrentHashMap` permite que varios hilos escriban y lean datos de forma segura.            |       |                   |
| 10   | Puedes acceder a los elementos de un `HashSet` por su índice.                                  |       |                   |



*Respuestas: 
1 – V, Porque conserva el orden en que se agregan los elementos y acepta valores repetidos
2 – F, Un `HashSet` elimina automáticamente cualquier valor duplicado.
3 – V, Cada elemento del `HashMap` está compuesto por una clave única y un valor asociado.
4 – F, `Comparable` se implementa dentro de una clase para definir su orden natural. No se usa entre diferentes clases.
5 – V, Es ideal para ordenar por distintos criterios, como precio, nombre o fecha.
6 – F, Sí se puede, siempre y cuando los objetos implementen `Comparable` o se proporcione un `Comparator`.
7 – F, No son seguras en concurrencia. Para eso existen versiones como CopyOnWrite`ArrayList` o Concurrent`HashMap`.
8 – F, Es más eficiente en lecturas, pero costoso si se modifica constantemente.
9 – V, Está diseñada para manejar operaciones concurrentes sin errores de sincronización.
10 – F, Los conjuntos (Set) no tienen índices, por lo tanto no permiten acceder por posición.*

---

#### 📝 Cierre

¡Felicidades por llegar al final de esta sesión! 🙌

Has recorrido un tema fundamental para cualquier desarrollador Java: el manejo de colecciones.

Ahora ya tienes una base sólida para:  
- Identificar cuándo usar una List, un Set o un Map.
- Entender las diferencias entre `ArrayList`, `HashSet` y `HashMap`.
- Aplicar ordenamientos usando `Comparable` y `Comparator`.
- Reconocer la importancia de las colecciones concurrentes y cuándo aplicarlas.

👉 Lo aprendido aquí te ayudará a escribir código más limpio, organizado y eficiente, y a prepararte para proyectos donde el manejo de datos sea clave.  

💡 Recuerda: **elegir la estructura adecuada marca la diferencia** entre un programa funcional y uno verdaderamente optimizado.  

Nos vemos en clase, ¡con toda la energía! 🚀 Tu camino como desarrollador Java está tomando forma. ¡Sigue así!

---

⬅️ [**Anterior**](../../Sesion-05/Prework/Readme.md) | [**Siguiente**](../../Sesion-07/Prework/Readme.md)➡️