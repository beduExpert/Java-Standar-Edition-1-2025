🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 02**](../Readme.md) ➡️ / 📝 `Ejemplo 01: Declaración de variables y uso de var`

## 🎯 Objetivo

🔍 Comprender cómo declarar variables en Java, diferenciar entre tipos de datos primitivos y de referencia, utilizar `var` para inferencia de tipos y aplicar conversiones de tipos mediante **casting**.

---

## 📌 ¿Qué es una variable en Java?

Una **variable** es como una caja donde guardamos un valor. En Java, cada variable debe tener un **tipo de dato**, que indica qué tipo de valor puede guardar. Aunque las versiones modernas permiten inferir el tipo con `var`, seguir definiendo el tipo ayuda a que el código sea más seguro, claro y eficiente.

---

## 🧩 Tipos de datos primitivos

Java incluye ocho tipos primitivos que almacenan datos simples:

| Tipo     | Descripción                         | Ejemplo      |
|----------|-------------------------------------|--------------|
| `int`    | Números enteros                     | `int edad = 25;` |
| `double` | Números decimales                   | `double altura = 1.75;` |
| `boolean`| Valores lógicos `true` o `false`    | `boolean activo = true;` |
| `char`   | Un solo carácter Unicode             | `char inicial = 'A';` |

```java
int edad = 30;
double precio = 1299.99;
boolean disponible = true;
char letra = 'J';
```

---

## 🧩 Inferencia de tipo con `var`

Desde Java 10, se puede usar `var` para que el compilador infiera el tipo de dato automáticamente:

```java
var mensaje = "Hola, mundo";
var numero = 10;
var activo = true;
```

📌 El tipo se infiere en tiempo de compilación y **no puede cambiarse**. Aunque `var` hace el código más limpio, el tipo real sigue existiendo y debe ser claro para evitar confusiones. No se recomienda usar `var` cuando el tipo no sea evidente, con `null` o sin inicializar.

---

## 🔁 Conversión de tipos y casting

A veces es necesario **convertir un tipo de dato a otro**. Esto puede hacerse de manera **implícita** o **explícita**:

```java
int numero = 10;
double resultado = numero; // conversión implícita

double precio = 19.99;
int precioEntero = (int) precio; // conversión explícita (casting)
```

⚠️ Al hacer casting, podrías perder precisión (por ejemplo, perder decimales).

---

## 💻 Ejemplo completo

```java
public class EjemploVariables {
    public static void main(String[] args) {
        int edad = 28;
        double salario = 15499.50;
        boolean activo = true;
        char inicial = 'M';
        var ciudad = "Guadalajara";

        // Imprimir los valores almacenados en las variables
        System.out.println("Edad: " + edad);
        System.out.println("Salario: $" + salario);
        System.out.println("Activo: " + activo);
        System.out.println("Inicial: " + inicial);
        System.out.println("Ciudad: " + ciudad);

        // Conversiónes
        double precio = 199.99;
        int precioRedondeado = (int) precio;
        System.out.println("Precio original: " + precio);
        System.out.println("Precio redondeado: " + precioRedondeado);
    }
}
```

---

## 💡 ¿Sabías que...?

- El uso de `var` mejora la legibilidad en declaraciones simples, pero no se recomienda en casos ambiguos.
- Java es un **lenguaje fuertemente tipado**, por lo que cada variable mantiene su tipo una vez declarado.
- Los tipos primitivos **no son objetos**, pero pueden convertirse en objetos usando wrappers como `Integer`, `Double`, `Boolean`, etc.

---

📘 Puedes repasar estos temas con más ejemplos aquí:  
🔗 [Java Data Types – W3Schools](https://www.w3schools.com/java/java_data_types.asp)  
🔗 [Java Data Types – Ionos](https://www.ionos.mx/digitalguide/paginas-web/desarrollo-web/java-data-types/)  

---

⬅️ [**Anterior**](../Readme.md) | [**Siguiente**](../Ejemplo-02/Readme.md)➡️