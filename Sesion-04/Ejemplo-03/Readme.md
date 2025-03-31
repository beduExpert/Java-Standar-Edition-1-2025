🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 04**](../Readme.md) ➡️ / 📝 `Ejemplo 03: Uso de record y Objects.equals()`


## 🎯 Objetivo

Explorar cómo usar `record` para simplificar clases de solo datos y aplicar `Objects.equals()` para hacer comparaciones seguras, incluso si hay valores `null`.

---

## 🧠 Recordemos...

- `record`: Permite crear clases de solo lectura (inmutables) con menos código y métodos útiles generados automáticamente.
- `Objects.equals()`: Compara objetos de manera segura, evitando errores por `null`.

---

## 📌 Escenario profesional

Imagina que trabajas como **Java Backend Developer** en una empresa que gestiona empleados. Necesitas almacenar información simple como nombre y edad de cada empleado, compararlos y mostrarlos fácilmente, asegurando que el sistema no se caiga si uno de los valores es `null`.

---

## 🧱 Creación del record `Empleado`

```java
// Definimos un record simple con dos campos
public record Empleado(String nombre, Integer edad) {
}
```

🧠 Java genera automáticamente:
- Constructor
- Métodos `nombre()`, `edad()`
- `equals()`, `hashCode()`, y `toString()`

---

## 🧪 Comparación segura con `Objects.equals()`

```java
import java.util.Objects;

public class Main {
    public static void main(String[] args) {
        // Creamos dos empleados con valores null en el nombre
        Empleado e1 = new Empleado(null, 25);
        Empleado e2 = new Empleado(null, 25);

        // Usamos Objects.equals() para comparar los nombres (evita NullPointerException)
        boolean nombresIguales = Objects.equals(e1.nombre(), e2.nombre());

        // Mostramos los objetos y la comparación
        System.out.println("Empleado 1: " + e1);
        System.out.println("Empleado 2: " + e2);
        System.out.println("¿Los nombres son iguales?: " + nombresIguales);
    }
}
```

---

## 🔍 Revisión rápida

| Elemento             | ¿Qué hace?                                                   |
|----------------------|--------------------------------------------------------------|
| `record`             | Crea una clase inmutable con constructor, getters y más.     |
| `Objects.equals()`   | Compara valores sin lanzar excepciones si hay `null`.        |
| `toString()`         | Ya viene implementado en un `record` para mostrar datos.     |

---

## 💡 ¿Sabías que...?

- Los `record` son ideales para **representar datos simples** como respuestas de API, formularios, o resultados de base de datos.
- `Objects.equals()` **evita errores comunes** que se dan al comparar campos que podrían ser `null`.
- Los `record` no permiten setters ni herencia, lo que los hace seguros y predecibles.

---

⬅️ [**Anterior**](../Reto-01/Readme.md) | [**Siguiente**](../Ejemplo-04/Readme.md)➡️