🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 01**](../Readme.md) ➡️ / 📝 `Ejemplo 03: Definiendo una clase con constructor`

## 🎯 Objetivo

🔍 Aprender a utilizar **constructores** en Java para inicializar objetos y sus atributos de una forma mucho mas controlada y escalable así como conocer la utilidad de los **modificadores de acceso** en el diseño de clases, y asegurar la integridad de la información en nuestros programas.

---

## 📌 ¿Qué es un constructor?

Un **constructor** es un método especial que se ejecuta automáticamente al crear un objeto. Se utiliza para **inicializar los atributos** de una clase con valores definidos.

```java
public class Producto {
    // Atributos del producto
    String nombre;
    double precio;

    // Constructor que inicializa el producto con nombre y precio
    public Producto(String nombre, double precio) {
        this.nombre = nombre;
        this.precio = precio;
    }

    // Método que muestra la información del producto en consola
    public void mostrarInformacion() {
        System.out.println("Producto: " + nombre + " - Precio: $" + precio);
    }
}

```

```java
public class Principal {
    public static void main(String[] args) {
        // Crear un objeto de tipo Producto utilizando el constructor
        Producto producto1 = new Producto("Laptop", 12499.99);

        // Llamar al método para mostrar la información del producto
        producto1.mostrarInformacion();
    }
}
```

---

## 🔐 ¿Qué es un modificador de acceso?

Los **modificadores de acceso** determinan la visibilidad de atributos y métodos. Por ahora, solo utilizamos `public`, pero más adelante conocerás `private`, `protected` y el modificador por defecto.

---

## 🔐 Modificadores de acceso

| Modificador | Acceso desde la misma clase | Acceso desde otras clases | Acceso desde otras clases en otro paquete |
|-------------|-----------------------------|----------------------------|-------------------------------------------|
| `public`    | ✅                          | ✅                         | ✅                                          |
| `private`   | ✅                          | ❌                         | ❌                                          |
| `protected` | ✅                          | ✅ (si es subclase)        | ✅ (si es subclase y en el mismo paquete)  |
| (sin)       | ✅                          | ✅                         | ❌                                          |

---

## 💡 ¿Sabías que...?

- Si no defines un constructor, Java genera uno vacío automáticamente.
- Puedes definir múltiples constructores en una misma clase (esto se llama **sobrecarga**).
- Los constructores permiten escribir clases más limpias y fáciles de usar.

---

📘 Recurso adicional para repaso:  
🔗 [Constructores en Java – W3Schools](https://www.w3schools.com/java/java_constructors.asp)

---

⬅️ [**Anterior**](../Reto-02/Readme.md) | [**Siguiente**](../Reto-03/Readme.md)➡️