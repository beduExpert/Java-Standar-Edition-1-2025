🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 04**](../Readme.md) ➡️ / 📝 `Ejemplo 04: Principios de encapsulación e inmutabilidad`



## 🎯 Objetivo

Aplicar el principio de **encapsulación** usando `private`, `getters` y `setters` con validación, y demostrar cómo crear una **clase inmutable** usando `final` y sin métodos modificadores.

---

## 🧠 Antes de empezar, recordemos:

- **Encapsulación**: Oculta los atributos de una clase para evitar modificaciones no controladas.
- **Inmutabilidad**: Los objetos no cambian después de ser creados. Útil para asegurar estabilidad y evitar errores.

---

## 📌 Escenario

Imagina que trabajas como **Java Developer** en un sistema de recursos humanos. Debes implementar una clase `Empleado` que proteja los datos del trabajador y otra clase `Contrato` que, una vez creada, **no se puede modificar**.

---

## 🧱 Clase `Empleado` (con encapsulación)

```java
public class Empleado {

    // Atributos privados (encapsulados)
    private String nombre;
    private int edad;

    // Constructor vacío
    public Empleado() {}

    // Getter para nombre
    public String getNombre() {
        return nombre;
    }

    // Setter con validación para nombre
    public void setNombre(String nombre) {
        if (nombre != null && !nombre.isEmpty()) {
            this.nombre = nombre;
        } else {
            System.out.println("❌ El nombre no puede estar vacío.");
        }
    }

    // Getter para edad
    public int getEdad() {
        return edad;
    }

    // Setter con validación para edad
    public void setEdad(int edad) {
        if (edad > 0) {
            this.edad = edad;
        } else {
            System.out.println("❌ La edad debe ser mayor a 0.");
        }
    }

    // Método para mostrar información
    public void mostrarInfo() {
        System.out.println("👨 Empleado: " + nombre + ", Edad: " + edad);
    }
}
```

---

## 🧱 Clase `Contrato` (inmutable)

```java
public final class Contrato {

    // Atributos privados y finales
    private final String tipo;
    private final double salario;

    // Constructor que inicializa todos los atributos
    public Contrato(String tipo, double salario) {
        this.tipo = tipo;
        this.salario = salario;
    }

    // Solo getters, sin setters
    public String getTipo() {
        return tipo;
    }

    public double getSalario() {
        return salario;
    }

    // Método para mostrar información
    public void mostrarInfo() {
        System.out.println("📄 Contrato: " + tipo + ", Salario: $" + salario);
    }
}
```

---

## 🚀 Ejecución en `Main`

```java
public class Main {
    public static void main(String[] args) {

        // Creamos un empleado y asignamos datos de forma segura
        Empleado e = new Empleado();
        e.setNombre("Valeria");
        e.setEdad(29);
        e.mostrarInfo();

        // Creamos un contrato que no se puede modificar después
        Contrato c = new Contrato("Tiempo completo", 25000.00);
        c.mostrarInfo();
    }
}
```

---

## 🔍 Revisión rápida

| Concepto        | Aplicación en el ejemplo                             |
|-----------------|------------------------------------------------------|
| Encapsulación   | Atributos `private`, acceso con `get` y `set`        |
| Validación      | Se verifica que nombre no sea vacío y edad > 0       |
| Inmutabilidad   | Clase `Contrato` con atributos `final` sin setters   |

---

## 💡 ¿Sabías que...?

- Encapsular ayuda a proteger la lógica del negocio y prevenir errores de usuario.
- Las clases inmutables son especialmente útiles en programación concurrente (threads).
- Aunque los records también son inmutables, una clase tradicional te permite aplicar validaciones en el constructor.

---
⬅️ [**Anterior**](../Ejemplo-03/Readme.md) | [**Siguiente**](../Reto-02/Readme.md)➡️
