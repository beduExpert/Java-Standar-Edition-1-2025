🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 04**](../Readme.md) ➡️ / 📝 `Ejemplo 01: Constructores e inicialización de objetos`

---

## 🎯 Objetivo

Aplicar de forma práctica el uso de **constructores** en Java (`por defecto`, `con parámetros`, `de copia` y **sobrecarga**), usando un escenario real para modelar una clase de entidad con distintas formas de inicialización.

---

## 🧠 ¿Que es un constructor? 

En Java, un **constructor** es un método especial que se ejecuta al crear un objeto. Sirve para inicializar sus atributos y garantizar que comience con valores válidos. Existen:

- **Constructor por defecto:** No recibe parámetros, asigna valores estándar.
- **Constructor con parámetros:** Permite personalizar el objeto desde el inicio.
- **Constructor de copia:** Crea un nuevo objeto a partir de otro existente.
- **Sobrecarga de constructores:** Permite múltiples formas de crear objetos con diferentes datos disponibles.

---

## 💡 Ejemplo 1

Imagina que trabajas como **Java Backend Developer** para una empresa que gestiona servicios de soporte técnico. Necesitas implementar una clase que represente **tickets de soporte**, permitiendo diferentes formas de crearlos: con valores por defecto, personalizados, clonando uno existente o usando diferentes combinaciones de información inicial.

---

## 🧱 Clase `TicketSoporte`

```java
public class TicketSoporte {

    // Atributos de instancia
    private String titulo;
    private String categoria;
    private int prioridad; // 1: Alta, 2: Media, 3: Baja
    private boolean estaActivo;

    // Constructor por defecto
    public TicketSoporte() {
        this.titulo = "Sin título";
        this.categoria = "General";
        this.prioridad = 2;
        this.estaActivo = true;
    }

    // Constructor con parámetros
    public TicketSoporte(String titulo, String categoria, int prioridad) {
        this.titulo = titulo;
        this.categoria = categoria;
        this.prioridad = prioridad;
        this.estaActivo = true;
    }

    // Constructor de copia
    public TicketSoporte(TicketSoporte otro) {
        this.titulo = otro.titulo;
        this.categoria = otro.categoria;
        this.prioridad = otro.prioridad;
        this.estaActivo = otro.estaActivo;
    }

    // Constructor sobrecargado con solo título
    public TicketSoporte(String titulo) {
        this.titulo = titulo;
        this.categoria = "Sin categoría";
        this.prioridad = 3; // Baja
        this.estaActivo = true;
    }

    // Método para mostrar la información del ticket
    public void mostrarInfo() {
        System.out.println("🎫 Ticket: " + titulo);
        System.out.println("📂 Categoría: " + categoria);
        System.out.println("⚠️ Prioridad: " + prioridad);
        System.out.println("📌 Estado: " + (estaActivo ? "Activo" : "Cerrado"));
    }

    // Método para cerrar el ticket
    public void cerrar() {
        estaActivo = false;
        System.out.println("🔒 El ticket '" + titulo + "' ha sido cerrado.");
    }
}
```

---

## 🚀 Ejecución en `Main`

```java
public class Main {
    public static void main(String[] args) {

        // Constructor por defecto
        TicketSoporte ticket1 = new TicketSoporte();
        System.out.println("\n✅ Ticket creado con constructor por defecto:");
        ticket1.mostrarInfo();

        // Constructor con parámetros
        TicketSoporte ticket2 = new TicketSoporte("Error al iniciar sesión", "Accesos", 1);
        System.out.println("\n✅ Ticket creado con parámetros:");
        ticket2.mostrarInfo();

        // Cerrar ticket y mostrar nuevamente
        ticket2.cerrar();
        ticket2.mostrarInfo();

        // Constructor de copia
        TicketSoporte ticket3 = new TicketSoporte(ticket2);
        System.out.println("\n✅ Ticket copiado desde otro:");
        ticket3.mostrarInfo();

        // Constructor sobrecargado con solo título
        TicketSoporte ticket4 = new TicketSoporte("Consulta sobre facturación");
        System.out.println("\n✅ Ticket con constructor sobrecargado (solo título):");
        ticket4.mostrarInfo();
    }
}
```

---

## 🔍 Revisión rápida

| Constructor                  | Descripción                                       | Ejemplo                                |
|------------------------------|---------------------------------------------------|----------------------------------------|
| Por defecto                  | Inicializa con valores estándar.                 | `new TicketSoporte()`                  |
| Con parámetros               | Permite personalización total.                   | `new TicketSoporte("...", "...", ...)` |
| De copia                     | Duplica otro ticket existente.                   | `new TicketSoporte(ticket)`            |
| Sobrecargado (solo título)   | Permite crear con solo el título.                | `new TicketSoporte("Solo título")`     |

---

## 💡 ¿Sabías que...?

🔹 Puedes tener **múltiples constructores en una misma clase** siempre que sus firmas (parámetros) sean diferentes. Esto se llama **sobrecarga**.

🔹 El uso de constructores ayuda a mantener el código más limpio y seguro, evitando que objetos queden con valores inválidos.

🔹 Los **constructores de copia** son útiles cuando necesitas manipular una copia sin afectar el objeto original.

🔹 Si no defines ningún constructor, Java agregará uno por defecto sin parámetros automáticamente.

---

⬅️ [**Anterior**](../Readme.md) | [**Siguiente**](../Ejemplo-02/Readme.md)➡️
