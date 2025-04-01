🏠 [**Inicio**](../Readme.md) ➡️ / 📖 `Sesión 09`/ 📝 `Sesión 09: Desarrollo del sistema de gestión de tareas`

---

## 🎯 Objetivo

Construir, ejecutar y probar una miniaplicación funcional en Java para la gestión de tareas dentro de un equipo ágil, integrando los conocimientos adquiridos en todas las sesiones previas: programación orientada a objetos, estructuras de datos, control de flujo y uso de consola.

---

## 🧱 Estructura del sistema

Durante la sesión, utilizaremos las siguientes clases:  

| Clase	        | Descripción                                                                         |
|---------------|-------------------------------------------------------------------------------------|
| `Tarea`       | Representa una tarea individual con ID, título, descripción, responsable y estado.  |
| `EstadoTarea` | Enum que define los estados posibles de una tarea (`TODO`, `IN_PROGRESS`, `DONE`).  |
| `GestorTareas`| Gestiona la colección de tareas: agrega, filtra y busca.                            |
| `Main`	    | Punto de entrada de la aplicación. Interfaz de consola para el usuario.             |


---

## 🧭 Paso 1: Crear el proyecto en tu entorno Java

1. Crea un proyecto nuevo llamado `SistemaTareas`.
2. Crea el siguiente paquete: `com.tareas`.

---

## 📦 Paso 2: Crear la clase `EstadoTarea.java`

Explicamos la importancia del `enum` para manejar constantes controladas.

```java
// Enumeración que define los estados válidos de una tarea
public enum EstadoTarea {
    TODO,         // Por hacer
    IN_PROGRESS,  // En progreso
    DONE          // Terminada
}
```
---

## 🧩 Paso 3: Crear la clase `Tarea.java`

Aquí aplicamos:

- POO (atributos, métodos)
- Constructores
- Encapsulamiento

```java
// Clase que representa una tarea dentro del sistema de gestión
public class Tarea {
    
    // Atributos privados (principio de encapsulamiento)
    private int id;                        // Identificador único de la tarea
    private String titulo;                // Título de la tarea
    private String descripcion;           // Descripción detallada de la tarea
    private String responsable;           // Persona responsable de la tarea
    private EstadoTarea estado;           // Estado actual de la tarea (TODO, IN_PROGRESS, DONE)

    // Constructor: inicializa una nueva tarea con estado TODO por defecto
    public Tarea(int id, String titulo, String descripcion, String responsable) {
        this.id = id;
        this.titulo = titulo;
        this.descripcion = descripcion;
        this.responsable = responsable;
        this.estado = EstadoTarea.TODO; // Estado inicial siempre será "TODO"
    }

    // Método getter para obtener el ID de la tarea
    public int getId() {
        return id;
    }

    // Método getter para obtener el estado actual de la tarea
    public EstadoTarea getEstado() {
        return estado;
    }

    // Método getter para obtener el nombre del responsable
    public String getResponsable() {
        return responsable;
    }

    // Método para cambiar el estado de la tarea (ej. TODO -> IN_PROGRESS)
    public void cambiarEstado(EstadoTarea nuevoEstado) {
        this.estado = nuevoEstado;
    }

    // Método para mostrar toda la información de la tarea en consola
    public void mostrarInfo() {
        System.out.println("ID: " + id);
        System.out.println("Título: " + titulo);
        System.out.println("Descripción: " + descripcion);
        System.out.println("Responsable: " + responsable);
        System.out.println("Estado: " + estado);
        System.out.println("-------------------------");
    }
}

```

## 🧠 Pausa didáctica

1. ¿Por qué inicializamos el estado como `TODO`? 
2. ¿Qué ventajas da mostrar información con `mostrarInfo()` en vez de `toString()`?

---

## 🗂️ Paso 4: Crear la clase `GestorTareas.java`

Aquí aplicamos:

- Colecciones (`ArrayList`)
- Métodos para CRUD parcial
- Modularidad


```java
import java.util.ArrayList;

// Clase que administra una colección de tareas
public class GestorTareas {
    private ArrayList<Tarea> tareas; // Lista que almacena todas las tareas

    // Constructor: inicializa la lista de tareas vacía
    public GestorTareas() {
        tareas = new ArrayList<>();
    }

    // Método para agregar una nueva tarea a la lista
    public void agregarTarea(Tarea tarea) {
        tareas.add(tarea);
    }

    // Método para mostrar todas las tareas registradas
    public void listarTareas() {
        for (Tarea tarea : tareas) {
            tarea.mostrarInfo();
        }
    }

    // Método para mostrar tareas según su estado (TODO, IN_PROGRESS, DONE)
    public void filtrarPorEstado(EstadoTarea estado) {
        for (Tarea tarea : tareas) {
            if (tarea.getEstado() == estado) {
                tarea.mostrarInfo();
            }
        }
    }

    // Método para mostrar tareas según el nombre del responsable
    public void filtrarPorResponsable(String responsable) {
        for (Tarea tarea : tareas) {
            if (tarea.getResponsable().equalsIgnoreCase(responsable)) {
                tarea.mostrarInfo();
            }
        }
    }

    // Método para buscar una tarea específica por su ID
    public Tarea buscarPorId(int id) {
        for (Tarea tarea : tareas) {
            if (tarea.getId() == id) {
                return tarea;
            }
        }
        return null; // Si no se encuentra, retorna null
    }
}

```

---

## 🖥️ Paso 5: Crear la clase `Main.java`

Aquí aplicamos:

- `Scanner` para entrada de datos
- Bucle `while` con `switch`
- Interacción con objetos

```java
import java.util.Scanner;

// Clase principal que muestra un menú interactivo para el usuario
public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);     // Objeto para leer datos desde consola
        GestorTareas gestor = new GestorTareas();     // Instancia del gestor de tareas
        int opcion;

        // Bucle principal del menú hasta que el usuario elija salir
        do {
            // Mostrar el menú de opciones
            System.out.println("===== MENÚ DE TAREAS =====");
            System.out.println("1. Agregar tarea");
            System.out.println("2. Ver todas las tareas");
            System.out.println("3. Filtrar por estado");
            System.out.println("4. Filtrar por responsable");
            System.out.println("5. Cambiar estado de una tarea");
            System.out.println("6. Salir");
            System.out.print("Seleccione una opción: ");
            opcion = scanner.nextInt();
            scanner.nextLine(); // Limpiar buffer después de leer un número

            // Ejecutar la acción según la opción elegida
            switch (opcion) {
                case 1:
                    // Solicitar datos al usuario para crear una nueva tarea
                    System.out.print("ID: ");
                    int id = scanner.nextInt();
                    scanner.nextLine(); // limpiar buffer
                    System.out.print("Título: ");
                    String titulo = scanner.nextLine();
                    System.out.print("Descripción: ");
                    String descripcion = scanner.nextLine();
                    System.out.print("Responsable: ");
                    String responsable = scanner.nextLine();

                    // Crear y agregar la nueva tarea
                    gestor.agregarTarea(new Tarea(id, titulo, descripcion, responsable));
                    break;

                case 2:
                    // Mostrar todas las tareas
                    gestor.listarTareas();
                    break;

                case 3:
                    // Solicitar estado a filtrar y mostrar tareas que lo cumplan
                    System.out.print("Estado (TODO, IN_PROGRESS, DONE): ");
                    String estadoStr = scanner.nextLine().toUpperCase();
                    try {
                        EstadoTarea estado = EstadoTarea.valueOf(estadoStr);
                        gestor.filtrarPorEstado(estado);
                    } catch (IllegalArgumentException e) {
                        System.out.println("Estado inválido.");
                    }
                    break;

                case 4:
                    // Solicitar nombre del responsable y filtrar
                    System.out.print("Responsable: ");
                    String resp = scanner.nextLine();
                    gestor.filtrarPorResponsable(resp);
                    break;

                case 5:
                    // Solicitar ID y nuevo estado para modificar la tarea
                    System.out.print("ID de la tarea: ");
                    int idTarea = scanner.nextInt();
                    scanner.nextLine();
                    Tarea tarea = gestor.buscarPorId(idTarea);
                    if (tarea != null) {
                        System.out.print("Nuevo estado (TODO, IN_PROGRESS, DONE): ");
                        String nuevoEstado = scanner.nextLine().toUpperCase();
                        try {
                            EstadoTarea estado = EstadoTarea.valueOf(nuevoEstado);
                            tarea.cambiarEstado(estado);
                        } catch (IllegalArgumentException e) {
                            System.out.println("Estado inválido.");
                        }
                    } else {
                        System.out.println("Tarea no encontrada.");
                    }
                    break;

                case 6:
                    // Salir del programa
                    System.out.println("¡Hasta luego!");
                    break;

                default:
                    System.out.println("Opción inválida.");
            }

        } while (opcion != 6); // Condición para seguir mostrando el menú

        scanner.close(); // Cerrar el lector al final
    }
}

```

---

## 🧠 Reflexión final

- ¿Qué aprendiste hoy sobre integrar varios conceptos de programación?
- ¿Cómo te sentiste trabajando en un proyecto completo y funcional?

---

## 🎉 Cierre

¡Felicidades por llegar hasta aquí! Hoy no solo programaste, sino que pensaste como desarrollador. Esta miniaplicación es un primer paso para construir software útil y profesional. Puedes mejorarla, extenderla o adaptarla como proyecto de portafolio. 🚀


---

⬅️ [**Anterior**](../Sesion-08/Readme.md)  | [**Siguiente**](../Sesion-10/Readme.md)➡️