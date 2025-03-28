🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 02**](../Readme.md) ➡️ / 📝 `Ejemplo 03: Sentencias condicionales`

## 🎯 Objetivo

🔍 Aprender a utilizar las **estructuras condicionales** en Java para tomar decisiones en función de ciertas condiciones, aplicando `if`, `else if`, `else` y `switch`, incluyendo su forma moderna.

---

## 📌 ¿Qué son las sentencias condicionales?

Las **sentencias condicionales** permiten ejecutar diferentes bloques de código dependiendo del valor de una condición lógica (`true` o `false`). Son esenciales para crear programas interactivos y con lógica flexible.

---

## 💻 Ejemplo: Sistema de envío de paquetes

Supongamos que trabajas para una empresa de paquetería y quieres determinar el **costo del envío** en función del tipo de paquete seleccionado por el usuario:

```java
import java.util.Scanner;

public class EnvioPaqueteria {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Introduce el tipo de paquete (pequeño, mediano, grande): ");
        String tipo = scanner.nextLine();

        double costo = 0;

        // Condicional con if-else
        if (tipo.equalsIgnoreCase("pequeño")) {
            costo = 49.99;
        } else if (tipo.equalsIgnoreCase("mediano")) {
            costo = 89.99;
        } else if (tipo.equalsIgnoreCase("grande")) {
            costo = 149.99;
        } else {
            System.out.println("Tipo de paquete no válido.");
        }

        if (costo > 0) {
            System.out.println("Costo del envío: $" + costo);
        }

        scanner.close();
    }
}
```

---

## 🔁 Alternativa con `switch` (Java 14+)

Desde Java 14, `switch` puede utilizarse de forma más expresiva y limpia:

```java
String tipo = "mediano";

double costo = switch (tipo.toLowerCase()) {
    case "pequeño" -> 49.99;
    case "mediano" -> 89.99;
    case "grande" -> 149.99;
    default -> {
        System.out.println("Tipo no válido.");
        yield 0.0;
    }
};

System.out.println("Costo del envío: $" + costo);
```

---

### 📌 ¿Por qué usamos `yield`?

Cuando un `case` en `switch` tiene más de una línea de código (como cuando usamos `{}`), **Java necesita saber qué valor retornar**. Para eso usamos `yield`.  
Es similar a `return`, pero se usa dentro de expresiones `switch`.


| Situación                  | ¿Se necesita `yield`? | Ejemplo                                                       |
|---------------------------|------------------------|----------------------------------------------------------------|
| `case` de una sola línea  | ❌                     | `case "mediano" -> 89.99;`                                     |
| `case` con varias líneas  | ✅                     | `default -> { System.out.println(); yield 0.0; }`              |

🔎 **Tip:** Usar `yield` mejora el control y claridad cuando necesitas lógica adicional antes de devolver un valor.

---

## 🧱 Comparativa entre estructuras

| Estructura     | Características principales                             |
|----------------|----------------------------------------------------------|
| `if / else`    | Ideal para condiciones simples o que requieren evaluación lógica |
| `switch` clásico | Más legible para comparar múltiples valores exactos     |
| `switch` moderno | Sintaxis más clara, permite retornos directos (`->`)    |

---

## 🧠 ¿Y qué pasa con `break` y `continue`?

- En el `switch` **clásico**, se usaba `break` para evitar la ejecución del siguiente `case`.  
- En el `switch` **moderno**, ya **no se necesita `break`**, lo que mejora la legibilidad.  
- `continue` es más común en bucles y se usa para **saltar una iteración** (lo veremos en el siguiente ejemplo).

---

## 💡 ¿Sabías que...?  
- Puedes encadenar múltiples condiciones usando `else if`.  
- El `switch` moderno también puede devolver valores, lo que reduce líneas de código.  
- `equalsIgnoreCase()` permite comparar cadenas sin importar mayúsculas o minúsculas.

---

📘 Recursos recomendados:  
🔗 [Java if-else – W3Schools](https://www.w3schools.com/java/java_conditions.asp)  
🔗 [Java switch – Oracle Docs](https://docs.oracle.com/en/java/javase/17/language/switch-expressions.html)

---

⬅️ [**Anterior**](../Reto-02/Readme.md) | [**Siguiente**](../Reto-03/Readme.md)➡️