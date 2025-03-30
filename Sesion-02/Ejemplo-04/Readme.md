🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 02**](../Readme.md) ➡️ / 📝 `Ejemplo 04: Repetición con ciclos`

## 🎯 Objetivo

🔍 Comprender cómo utilizar **estructuras de repetición** en Java para ejecutar bloques de código múltiples veces, aplicando `while`, `do-while`, `for` y `for-each`. También exploraremos el uso de `break` y `continue`.

---

## 🧠 ¿Qué son los ciclos?

Los ciclos (o bucles) permiten ejecutar instrucciones de forma **repetitiva** mientras se cumpla una condición. Son muy útiles para procesar datos, validar entradas, repetir cálculos, entre otros usos comunes.

---

## 💡 Ejemplo 1: Control de intentos con `while`

### 🎯 Contexto: Intentos para ingresar una contraseña correcta.

```java
import java.util.Scanner;

public class LoginSistema {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String contraseñaCorrecta = "admin123";
        String input;
        int intentos = 0;
        int maxIntentos = 3;

        while (intentos < maxIntentos) {
            System.out.print("Ingresa tu contraseña: ");
            input = scanner.nextLine();

            if (input.equals(contraseñaCorrecta)) {
                System.out.println("✅ Acceso concedido.");
                break;
            } else {
                System.out.println("❌ Contraseña incorrecta.");
                intentos++;
            }
        }

        if (intentos == maxIntentos) {
            System.out.println("🔒 Cuenta bloqueada por demasiados intentos.");
        }

        scanner.close();
    }
}
```

---

## 💡 Ejemplo 2: Recorriendo productos con `for` y `for-each`

### 🎯 Contexto: Mostrar productos de un carrito de compras.

```java
public class CarritoCompras {
    public static void main(String[] args) {
        String[] productos = {"Laptop", "Mouse", "Teclado", "Pantalla", "Audífonos"};

        // for clásico
        System.out.println("📦 Productos en el carrito:");
        for (int i = 0; i < productos.length; i++) {
            System.out.println("- " + productos[i]);
        }

        // for-each con control de flujo
        System.out.println("\n🔁 Recorriendo con for-each:");
        for (String producto : productos) {
            if (producto.equals("Teclado")) continue; // Saltar teclado
            if (producto.equals("Pantalla")) break;   // Detener en pantalla
            System.out.println("Producto válido: " + producto);
        }
    }
}
```

> 🔎 **Nota**: En este ejemplo usamos un **objeto tipo lista** llamado `array`, que nos permite almacenar y recorrer múltiples elementos del mismo tipo.  
> Más adelante exploraremos estructuras más flexibles como `ArrayList`.

---

## 📌 ¿Qué estructuras vimos?

| Ciclo         | ¿Cuándo usarlo?                                     |
|---------------|------------------------------------------------------|
| `while`       | Cuando no sabes cuántas veces se repetirá.          |
| `do-while`    | Similar a `while`, pero ejecuta **al menos una vez**.|
| `for`         | Ideal para contar o recorrer posiciones con índice. |
| `for-each`    | Recorre todos los elementos de un array fácilmente. |
| `break`       | Sale del ciclo inmediatamente.                      |
| `continue`    | Salta a la siguiente iteración.                     |

---

## 💡 Buenas prácticas

- ⚠️ Asegúrate de actualizar las condiciones para evitar ciclos infinitos.
- ✅ Usa `for-each` cuando no necesites acceder a los índices.
- ❌ No uses `break` y `continue` en exceso, puede dificultar la lectura del código.

---

📘 Recurso recomendado:  
🔗 [Java Loops – W3Schools](https://www.w3schools.com/java/java_while_loop.asp)

---

⬅️ [**Anterior**](../Ejemplo-03/Readme.md) | [**Siguiente**](../Reto-02/Readme.md)➡️