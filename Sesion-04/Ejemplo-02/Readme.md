🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 04**](../Readme.md) ➡️ / 📝 `Ejemplo 02: Métodos equals(), hashCode() y toString()`

---

## 🎯 Objetivo 

Aplicar los métodos especiales `equals()`, `hashCode()` y `toString()` en una clase personalizada para mejorar la comparación, visualización y uso de objetos en estructuras de datos.

---

## 🧠  Métodos `equals()`, `hashCode()` y `toString()`

Estos métodos permiten trabajar con objetos de forma más eficiente y comprensible:

- `equals()` compara el **contenido** de los objetos.
- `hashCode()` genera un código único para cada objeto (clave en colecciones como HashSet o HashMap).
- `toString()` ofrece una representación **legible** del objeto para la consola o logs.

---

## 📌 Escenario profesional

Siguiendo el ejemplo anterior: trabajas como **Java Backend Developer** en un sistema de soporte técnico. Cada ticket debe poder ser comparado, identificado en estructuras de datos y mostrado fácilmente para depuración.

Para ello, implementamos estos tres métodos en la clase `TicketSoporte`.

---

## 🧱 Clase `TicketSoporte`

```java
import java.util.Objects;

public class TicketSoporte {

    private String titulo;
    private String categoria;
    private int prioridad;
    private boolean estaActivo;

    public TicketSoporte(String titulo, String categoria, int prioridad) {
        this.titulo = titulo;
        this.categoria = categoria;
        this.prioridad = prioridad;
        this.estaActivo = true;
    }

    // Sobrescribimos equals() para comparar contenido
    @Override
    public boolean equals(Object obj) {
        if (this == obj) return true; // Mismo objeto
        if (obj == null || getClass() != obj.getClass()) return false;

        TicketSoporte otro = (TicketSoporte) obj;
        return this.titulo.equals(otro.titulo) &&
               this.categoria.equals(otro.categoria) &&
               this.prioridad == otro.prioridad &&
               this.estaActivo == otro.estaActivo;
    }

    // hashCode() compatible con equals()
    @Override
    public int hashCode() {
        return Objects.hash(titulo, categoria, prioridad, estaActivo);
    }

    // toString() para ver fácilmente la información del ticket
    @Override
    public String toString() {
        return "🎫 TicketSoporte {" +
                "titulo='" + titulo + '\'' +
                ", categoria='" + categoria + '\'' +
                ", prioridad=" + prioridad +
                ", estaActivo=" + estaActivo +
                '}';
    }
}
```

---

## 🚀 Ejecución en `Main`

```java
public class Main {
    public static void main(String[] args) {

        // Creamos dos tickets con los mismos valores
        TicketSoporte t1 = new TicketSoporte("Error de login", "Accesos", 1);
        TicketSoporte t2 = new TicketSoporte("Error de login", "Accesos", 1);

        // Comparación con equals()
        System.out.println("¿Son iguales? " + t1.equals(t2));  // true

        // Hash codes
        System.out.println("Hash de t1: " + t1.hashCode());
        System.out.println("Hash de t2: " + t2.hashCode());

        // Representación legible del objeto
        System.out.println("Ticket 1:");
        System.out.println(t1);
    }
}
```

---

## 💡 No olvides...

🔹 Es **obligatorio** sobrescribir `hashCode()` si sobrescribes `equals()` para evitar errores en estructuras como `HashSet` o `HashMap`.

🔹 `toString()` es muy útil para mostrar objetos en logs, en lugar de ver direcciones de memoria.

🔹 Estas buenas prácticas ayudan a escribir código más limpio, claro y **profesional**.

---

⬅️ [**Anterior**](../Ejemplo-01/Readme.md) | [**Siguiente**](../Reto-01/Readme.md)➡️
