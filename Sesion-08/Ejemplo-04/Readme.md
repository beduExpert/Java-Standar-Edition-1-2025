
🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 08**](../Readme.md) ➡️ / 📖 `Ejemplo 04: Manejo de excepciones con try-catch-finally`

---

## 🎯 Objetivo

🔐 Aprender a manejar errores de forma segura y controlada usando bloques `try-catch-finally` en Java, comprendiendo la diferencia entre excepciones `checked` y `unchecked`.

---

## 🧠 Repasemos

Las **excepciones** en Java te permiten evitar que tu programa falle de forma inesperada, dándole al usuario una respuesta clara ante un error.

### 🧱 Tipos de excepciones

| Tipo        | ¿Compila sin manejarla? | ¿Se debe manejar? | Ejemplos                    |
|-------------|--------------------------|--------------------|-----------------------------|
| Checked     | ❌ No                    | ✅ Sí              | `IOException`, `SQLException` |
| Unchecked   | ✅ Sí                    | ❌ No (recomendado) | `NullPointerException`, `ArithmeticException` |

### 📌 Estructura típica

```java
try {
    // Código que podría fallar
} catch (Exception e) {
    // Qué hacer si falla
} finally {
    // Siempre se ejecuta, ideal para cerrar recursos
}
```

---

## 💼 Ejemplo 

Eres **Remote Work Coordinator** en una empresa multinacional. Parte de tu sistema valida los tiempos de conexión remota de los empleados. Sin embargo, a veces los datos ingresados manualmente están en formatos incorrectos o contienen divisiones por cero.

Necesitas evitar que el sistema falle por errores simples como una división entre 0 o el ingreso de datos no numéricos.

### 💻 Código con riesgo (sin manejo de excepciones)

```java
import java.util.Scanner;

public class ValidadorHorasConexion {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Total de horas conectadas: ");
        int horas = scanner.nextInt();

        System.out.print("Número de días laborales: ");
        int dias = scanner.nextInt();

        int promedio = horas / dias;
        System.out.println("Promedio de horas por día: " + promedio);
    }
}
```

### 🚨 ¿Qué puede salir mal?

- El usuario ingresa texto en lugar de números → `InputMismatchException`
- Ingresan 0 días → `ArithmeticException`
- Nadie cierra el scanner → mala gestión de recursos

---

### ✅ Código optimizado con manejo de excepciones

```java
import java.util.InputMismatchException;
import java.util.Scanner;

public class ValidadorHorasConexionSeguro {
    public static void main(String[] args) {
        Scanner scanner = null;

        try {
            scanner = new Scanner(System.in);

            System.out.print("Total de horas conectadas: ");
            int horas = scanner.nextInt();

            System.out.print("Número de días laborales: ");
            int dias = scanner.nextInt();

            int promedio = horas / dias; // Posible división por cero
            System.out.println("Promedio de horas por día: " + promedio);

        } catch (InputMismatchException e) {
            System.out.println("❌ Error: Debes ingresar un número entero válido.");
        } catch (ArithmeticException e) {
            System.out.println("❌ Error: No puedes dividir entre cero.");
        } catch (Exception e) {
            System.out.println("❌ Error inesperado: " + e.getMessage());
        } finally {
            if (scanner != null) {
                scanner.close(); // Gestión adecuada del recurso
                System.out.println("📦 Recurso liberado correctamente.");
            }
        }
    }
}
```

### 💡 ¿Qué hicimos mejor?

- Controlamos errores de entrada (`InputMismatchException`)
- Evitamos caídas inesperadas por división entre cero
- Liberamos el recurso `Scanner` con `finally`

---

## 🔄 ¿Qué aprendimos?

✅ Las excepciones permiten que el programa no se detenga bruscamente  
✅ `try-catch-finally` ofrece estructura clara y flexible para manejar errores  
✅ Diferenciar entre errores comunes y graves mejora la experiencia del usuario

---

## 💡 ¿Sabías que...?

- En Java, el uso de `try-with-resources` es una evolución moderna que permite cerrar automáticamente ciertos recursos.
- Puedes **encadenar múltiples bloques catch** para manejar diferentes tipos de error de forma específica.
- Las buenas prácticas sugieren **no capturar `Exception` de forma genérica** a menos que sea estrictamente necesario.

---

📘 Recurso adicional:  
🔗 https://www.w3schools.com/java/java_try_catch.asp

---

⬅️ [**Anterior**](../Ejemplo-03/Readme.md) | [**Siguiente**](../Ejemplo-05/Readme.md)➡️

