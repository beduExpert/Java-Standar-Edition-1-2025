🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 01**](../Readme.md) ➡️ / 📝 `Ejemplo 01: Mi primer programa en Java`

## 🎯 Objetivo

🔍 Escribir y ejecutar nuestro primer programa en **Java**, comprendiendo su estructura básica y el proceso de compilación y ejecución, tanto desde la terminal como desde un entorno de desarrollo (IDE).

---

## 📌 Introducción a Java

Java es un lenguaje de programación moderno, robusto y multiplataforma, ampliamente utilizado en la industria del software para crear aplicaciones web, móviles, de escritorio y sistemas embebidos.

> 📘 Nota: En Java, todo gira en torno a las **clases**. En el siguiente ejemplo, aprenderás qué es una clase y qué es un objeto, fundamentos clave de la Programación Orientada a Objetos (POO).

---

## 🧱 Estructura básica de un programa en Java

Todo programa en Java debe contener al menos **una clase** con un método `main`, que representa el **punto de entrada** del programa.

```java
public class HolaMundo {
    public static void main(String[] args) {
        System.out.println("¡Hola, Java!");
    }
}
```

### 🔍 Explicación del código
- `public class HolaMundo` → Define una clase pública llamada `HolaMundo`. El nombre del archivo debe coincidir (`HolaMundo.java`).
- `public static void main(String[] args)` → Método principal desde donde se ejecuta el programa.
- `System.out.println(...)` → Muestra un mensaje en la consola.

---

## 📦 Compilación y ejecución desde la terminal

En Java, el código fuente debe **compilarse** antes de ejecutarse. Esto se realiza en dos pasos:

### 1️⃣ Compilar el programa
```sh
javac HolaMundo.java
```
Esto generará un archivo llamado `HolaMundo.class`.

### 2️⃣ Ejecutar el programa compilado
```sh
java HolaMundo
```

📌 **Nota:** No incluyas la extensión `.class` al ejecutar.

---

## 💻 Ejecución desde IntelliJ IDEA

Si usas **IntelliJ IDEA**, sigue estos pasos:

1. Crea un nuevo proyecto en Java.
2. Agrega una clase nueva llamada `HolaMundo`.
3. Copia el código anterior en el archivo.
4. Haz clic en el botón **Run** ▶ o presiona `Shift + F10`.

---

## 🧾 Palabras clave usadas en este ejemplo

| Palabra clave | Significado |
|---------------|-------------|
| `class`       | Define una clase en Java. |
| `public`      | Permite que el método o clase sea accesible desde cualquier lugar. |
| `static`      | El método pertenece a la clase, no a una instancia. |
| `void`        | El método no devuelve ningún valor. |
| `main`        | Es el punto de entrada del programa. |

---

## 💡 ¿Sabías que...?

- Java es un lenguaje **compilado e interpretado**: se transforma a bytecode y luego es ejecutado por la **JVM**.
- El método `main()` es **obligatorio** para ejecutar un programa Java.
- Gracias a la **Máquina Virtual de Java (JVM)**, el mismo programa puede correr en **Windows, Linux o Mac** sin necesidad de cambiar el código.

---

⬅️ [**Anterior**](../Readme.md) | [**Siguiente**](../Ejemplo-02/Readme.md)➡️