🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 01**](../Readme.md) ➡️ / 📝 `Ejemplo 04: Uso de record y sealed classes`

## 🎯 Objetivo

🔍 Explorar dos características modernas de Java: el uso de `record` para crear clases inmutables de manera concisa, y `sealed classes` para restringir la herencia en estructuras más seguras y controladas.

---

## 📌 ¿Qué es un `record`?

Un `record` es una forma concisa de declarar clases inmutables en Java. Fueron introducidos en Java 14 como feature preview y estables desde Java 16. Son ideales para representar estructuras simples de datos, como DTOs (Data Transfer Objects).

```java
// Un record es una forma concisa de definir una clase inmutable en Java.
public record Producto(String nombre, double precio) { }
```

✅ Con esta única línea, Java genera automáticamente:
- Constructor
- Getters (`nombre()` y `precio()`)
- `equals()`, `hashCode()` y `toString()`

```java
public class Principal {
    public static void main(String[] args) {
        // Crear un objeto de tipo Producto usando el record
        Producto producto = new Producto("Monitor", 3299.99);

        // Muestra el toString() generado automáticamente por el record.
        System.out.println(producto);
    }
}
```

🧠 Salida:
```
Producto[nombre=Monitor, precio=3299.99]
```

📝 Esta salida representa el contenido del objeto `producto` impreso automáticamente por el método `toString()` generado por el record.

---

## 📌 ¿Qué es una `sealed class`?

Una `sealed class` (introducida en Java 17) permite **restringir qué clases pueden heredar** de ella. Esto mejora la seguridad y el control en jerarquías de clases.

```java
// Clase base sellada: solo las clases permitidas pueden extenderla.
// Mejora el control de herencia en jerarquías cerradas.
public sealed class Vehiculo permits Auto, Camion { }

// Clase Auto que extiende Vehiculo. Se declara como final para no permitir más herencia.
final class Auto extends Vehiculo { }

// Clase Camion que también extiende Vehiculo y es final.
final class Camion extends Vehiculo { }
```

📌 En este ejemplo:
- Solo `Auto` y `Camion` pueden extender de `Vehiculo`.
- Cualquier otro intento de herencia será un error de compilación.

### ❌ Ejemplo de error al extender `Vehiculo` sin permiso:

```java
// Esta clase NO está en la lista de 'permits', por lo tanto, genera un error.
class Moto extends Vehiculo { }
```

🛑 **Error de compilación esperado:**
```
class Moto is not allowed to extend sealed class Vehiculo
```
---

## 📌 ¿Qué significa `final`?

El modificador `final` en una clase indica que **no puede ser heredada**. En el contexto de una `sealed class`, es obligatorio que las clases que extienden de ella sean:

- `final` → no pueden ser heredadas.
- `sealed` → continúan una jerarquía sellada.
- `non-sealed` → permiten herencia abierta.

✅ En el ejemplo anterior, `Auto` y `Camion` son `final` porque no se espera que otras clases hereden de ellas.

---

## 💡 ¿Sabías que...?  
- Los `record` no permiten atributos mutables (no se pueden modificar después de crear el objeto).
- Las `sealed classes` promueven jerarquías cerradas, ideales para modelar flujos de negocio controlados (por ejemplo: tipos de notificaciones, transacciones, permisos).
- Ambas funcionalidades son parte del enfoque moderno de Java hacia un código más **conciso**, **seguro** y **mantenible**.

---

📘 Recurso adicional para repaso:  
🔗 [Records – Oracle Docs](https://docs.oracle.com/en/java/javase/17/language/records.html)  
🔗 [Sealed Classes – Oracle Docs](https://docs.oracle.com/en/java/javase/17/language/sealed-classes-and-interfaces.html)

---

⬅️ [**Anterior**](../Ejemplo-03/Readme.md) | [**Siguiente**](../Reto-02/Readme.md)➡️