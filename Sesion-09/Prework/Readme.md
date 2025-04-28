🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 `Prework sesión 09`

<div align="center">
    <img src="../Imagenes/S00.jpg" alt="Bedu | Haz + con tu talento | JAVA STANDARD EDITION I">
</div>

##### **PREWORK**
#### **🟧 Sesión 09**
#### **Mentorship 1**

##### 🔶 **Introducción** 

¡Hola! 👋

Antes que nada, ¡felicidades! 🎉 Has llegado a la sesión 09, lo que significa que completaste todas las sesiones teóricas del curso de Java Standard Edition I. Este logro no es menor: implica constancia, esfuerzo y, sobre todo, un genuino interés por aprender a programar en uno de los lenguajes más usados en el mundo profesional.

Tu compromiso con cada sesión ha sido un paso firme hacia una nueva carrera o estilo de vida como programador. Ahora cuentas con una base sólida en programación orientada a objetos, estructuras de control, colecciones y muchos otros fundamentos esenciales para el desarrollo de software.

Para cerrar con broche de oro, en este prework vamos a preparar el terreno para construir una aplicación completa que integre gran parte de los temas revisados. Se trata de un ejemplo práctico y profesional basado en la vida real de un programador: el desarrollo de un módulo de gestión de tareas para un equipo de desarrollo ágil.

Durante la sesión en vivo, implementarás esta aplicación en código. Pero antes, en este prework, reforzarás la teoría necesaria para estar listo. ¡Vamos con todo!

---

#### 🎯 Objetivo  

- Comprender los principios de programación orientada a objetos y estructuras de datos necesarios para desarrollar un sistema de gestión de tareas en un contexto de trabajo ágil.

---

#### 📋 Instrucciones

Este Prework está diseñado para conocer el contenido que se practicará durante la sesión en vivo. **Por favor no lo omitas**. Toma notas de lo que consideres relevante y guarda tus preguntas o dudas para resolverlas en la sesión.

---

#### Bienvenido/a

Bienvenid@ al noveno Prework del módulo. A continuación, te presentamos el tiempo estimado de lectura por tema, para que puedas revisar todos los recursos al máximo:

| **📖 Temario**                                      | **🕰️ Tiempo sugerido** |
|-----------------------------------------------------|-------------------------|
| Tema 01. Teoría y fundamentos para caso de estudio  | 15 min                  |

**¡Comencemos! 🏁**

---
 
#### 📚 Tema 01. Teoría y fundamentos para caso de estudio
##### ⏳ 15 minutos de lectura

Hoy daremos un paso importante: vamos a dejar atrás los ejercicios individuales y estructurados para construir algo mucho más completo y cercano a lo que harías como programador en un entorno profesional.  

Vamos a desarrollar un caso de estudio, es decir, una miniaplicación funcional que simula un escenario real de trabajo. En este caso, construiremos un **módulo de gestión de tareas para un equipo ágil**, como los que usan diariamente en equipos que aplican metodologías como Scrum o Kanban.  

Este proyecto te permitirá integrar la mayoría de los conceptos que has aprendido:  

- Programación orientada a objetos
- Manejo de colecciones
- Control de flujo
- Interacción con el usuario en consola
- Buenas prácticas de codificación

El objetivo no es solo escribir código que funcione, sino **razonar como un programador**, identificar cómo se estructura una solución, y entender cómo se representa la lógica del mundo real en código.

Prepárate para aplicar todo lo aprendido… ¡y dar el primer paso hacia tus futuros proyectos reales! 🚀

**Contexto**

Imagina que formas parte de un equipo de desarrollo de software que trabaja bajo metodologías ágiles como Scrum o Kanban. Cada semana o cada sprint, el equipo debe planificar, ejecutar y dar seguimiento a una serie de tareas que forman parte del desarrollo de un producto.  

Tu rol como programador en este equipo implica no solo escribir código, sino también contribuir con herramientas internas que mejoren la eficiencia del equipo. Uno de los retos que han identificado es la necesidad de contar con un módulo ligero y funcional para gestionar tareas de forma interna durante el sprint.  

Como todavía están en fases tempranas del proyecto y no tienen recursos para construir una aplicación web ni base de datos, se ha decidido hacer una aplicación en consola, escrita en Java, que permita al equipo:

- Registrar nuevas tareas, especificando detalles como el título, la descripción, el responsable y el estado inicial.
- Modificar el estado de las tareas conforme avanzan (por ejemplo: de “To Do” a “In Progress” o “Done”).
- Listar tareas filtradas por estado o por persona responsable.
- Simular el flujo de trabajo real que se sigue durante la planificación y ejecución de un sprint.

Este sistema será una herramienta útil para la organización del equipo y un gran ejercicio para ti como desarrollador, ya que representa un caso realista de lo que podrías llegar a construir como parte de un equipo profesional de desarrollo.  

**Temas clave a repasar**

1. **Clases y Objetos**
Una clase es una plantilla para crear objetos. Permite encapsular datos (atributos) y comportamientos (métodos).  

```java
public class Tarea {
    int id;
    String titulo;
    String descripcion;
    String responsable;
    EstadoTarea estado;
}
```
2. **Constructores y Métodos**  
El constructor inicializa un objeto. Los métodos permiten operar sobre los datos del objeto.

```java
public Tarea(int id, String titulo, String descripcion, String responsable) {
    this.id = id;
    this.titulo = titulo;
    this.descripcion = descripcion;
    this.responsable = responsable;
    this.estado = EstadoTarea.TODO;
}

public void cambiarEstado(EstadoTarea nuevoEstado) {
    this.estado = nuevoEstado;
}
```

3. **Encapsulamiento y `Getters`/`Setters`**
Para proteger los datos del objeto y permitir su acceso controlado, se usan modificadores de acceso y métodos `getters`/`setters`.

```java
private int id;
public int getId() {
    return id;
}
```
4. **`ArrayList` de Objetos**
Permite almacenar una colección de tareas y recorrerlas.

```java
ArrayList<Tarea> tareas = new ArrayList<>();
tareas.add(nuevaTarea);
```

5. **Control de flujo**
Menús, bucles y condicionales permiten gestionar la interacción del usuario en consola.

```java
while (true) {
    System.out.println("1. Agregar tarea\n2. Ver tareas\n3. Salir");
    int opcion = scanner.nextInt();
    switch(opcion) {
        case 1: // agregar tarea
        case 2: // ver tareas
        case 3: System.exit(0);
    }
```
6. **Enumeraciones (`Enums`)**
Una forma segura de manejar valores constantes, como el estado de una tarea.

```java
public enum EstadoTarea {
    TODO,
    IN_PROGRESS,
    DONE
}
```

**📅 Esquema del sistema propuesto**

Para construir esta aplicación de consola, seguiremos un enfoque orientado a objetos. Esto significa que modelaremos los elementos del sistema como *clases* que representan entidades del mundo real, cada una con sus *atributos* (características) y *métodos* (acciones o comportamientos).

El núcleo del sistema será la clase `Tarea`, pero también consideraremos el uso de una enumeración (`enum`) para el estado de la tarea, y una clase `GestorTareas` que actuará como controlador o administrador de todas las tareas creadas.

**Detalles adicionales**

🧩 Clase `Tarea`
- Cada objeto representa una actividad dentro del sprint.
- Su método `cambiarEstado()` permite simular el avance de la tarea.
- El método `mostrarInfo()` devuelve una descripción clara para mostrar en consola.

🔁 Enum `EstadoTarea`
- Establece los estados permitidos para una tarea.
- Evita errores de entrada al restringir las opciones a valores válidos.
- Mejora la legibilidad del código.

🗂 Clase `GestorTareas`
- Funciona como una base de datos temporal (en memoria) para las tareas.
- Se encarga de gestionar operaciones como agregar, buscar y listar.
- Permite mantener una lógica ordenada, separando responsabilidades.

🧭 Clase `Main`
- Contiene el menú interactivo en consola.
- Usa un bucle while con switch para navegar entre opciones.
- Recibe entradas del usuario mediante Scanner.

**Glosario técnico**

A continuación, se presentan algunos términos clave que necesitas comprender y dominar para desarrollar correctamente este caso de estudio. Este glosario refuerza conceptos fundamentales que aplicarás directamente al construir tu sistema de gestión de tareas.

🧱 **POO (Programación Orientada a Objetos)**  

Es un paradigma de programación que permite estructurar el código en torno a **objetos** que representan entidades del mundo real. Cada objeto combina datos (atributos) y comportamientos (métodos).

> En este proyecto, cada tarea es un objeto que tiene un estado, un título, un responsable y puede cambiar de estado, mostrar su información, etc.

📋 **`ArrayList`**  

Es una estructura de datos dinámica de Java que permite almacenar y manipular colecciones de objetos. A diferencia de los arreglos tradicionales, puede crecer o reducir su tamaño automáticamente.

> Usaremos un `ArrayList<Tarea>` para guardar todas las tareas del sistema y poder recorrerlas, filtrarlas o buscar una específica.

🔒 **Encapsulamiento**

Es el principio de ocultar los atributos internos de un objeto para que solo puedan ser accedidos o modificados mediante métodos públicos (getters/setters). Esto protege la integridad de los datos.

> Por ejemplo, haremos que el ID de una tarea sea privado, y se accederá a él solo a través de su método `getId()`.

🔁 **`Enum` (Enumeración)**

Es una estructura que define un conjunto fijo de constantes. En Java, los enum son útiles para representar valores limitados y predecibles.

> En nuestro sistema, el estado de una tarea será un `enum` con los valores `TODO`, `IN_PROGRESS` y `DONE`, lo cual evita errores al escribir los estados como cadenas de texto.

🧩 **Modularidad**

Es la práctica de dividir un programa en partes pequeñas y manejables llamadas módulos o clases, cada una con una responsabilidad específica. Esto mejora la organización, el mantenimiento y la reutilización del código.  

> En este proyecto, la clase `Tarea` se encarga de representar tareas, `GestorTareas` de administrarlas, y `Main` de manejar la interacción con el usuario.

Estos conceptos forman parte del lenguaje común que usamos los desarrolladores para construir soluciones sólidas y escalables. Entenderlos te permitirá completar este ejercicio con éxito y también comunicarte mejor en equipos de trabajo y afrontar proyectos reales con mayor seguridad.  

Ahora que ya los tienes claros, estás listo para aplicarlos en un sistema funcional que simula un entorno profesional.  

---

#### 🧠 Actividad de reforzamiento

💬 **Preguntas para reflexión**

- ¿Qué ventajas tiene usar un `enum` para el estado de la tarea?
- ¿Cómo validarías que no se repita el ID de una tarea?
- ¿Qué estructura de datos te permite agregar y recorrer tareas de manera eficiente?
- ¿Cómo se aplicarían estos conceptos en una aplicación real con interfaz o base de datos?

---

#### 📝 Cierre

Has llegado al final del prework de la sesión 09, un paso clave antes de poner manos al código y construir tu primera aplicación completa en Java. Aquí repasaste los conceptos esenciales que aplicaremos en un caso práctico realista, similar a los retos que enfrentan los programadores en su día a día.

Este conocimiento no solo es teórico: está diseñado para ayudarte a **pensar como desarrollador**, estructurar soluciones limpias y funcionales, y trabajar con lógica, orden y claridad.

Prepárate para la siguiente sesión, donde transformarás esta teoría en una aplicación funcional que podrás mostrar con orgullo como parte de tu portafolio.

¡Nos vemos en el código! 💻🚀

---

⬅️ [**Anterior**](../../Sesion-08/Prework/Readme.md) | [**Siguiente**](../../Sesion-10/Prework/Readme.md)➡️