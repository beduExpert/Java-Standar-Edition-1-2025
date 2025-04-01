🏠 [**Inicio**](../Readme.md) ➡️ / 📖 `Sesión 10`/ 🧠 `Sesión 10: Repaso integral y Mentorship Final`
---

## 🎯 Objetivo general
Reflexionar, preguntar y reforzar conocimientos clave adquiridos en el módulo **Java Standard Edition**, a través de preguntas detonadoras, ejecución de ejemplos prácticos y acompañamiento grupal.

---

## 🧩 Sesión 01: Introducción a la programación orientada a objetos en Java

✅ **Recordatorio rápido**  
- Java es un lenguaje multiplataforma, orientado a objetos y seguro.  
- Fundamentos de POO: clases, objetos, encapsulamiento, herencia, polimorfismo, abstracción.  
- Herramientas utilizadas: JDK + IntelliJ.  

💬 **Preguntas detonadoras**
- ¿Qué beneficios te dio pensar en objetos en lugar de funciones sueltas?
- ¿Qué parte de la POO se te hizo más retadora?

⚙️ **Ejercicio: Clase `Libro`**

Crear una clase `Libro` con atributos y un método `mostrarInfo()`.

```java
// Definición de la clase Libro con dos atributos: título y autor
public class Libro {
    String titulo; // Atributo que representa el título del libro
    String autor;  // Atributo que representa el autor del libro

    // Método para mostrar la información del libro
    public void mostrarInfo() {
        System.out.println("Título: " + titulo + ", Autor: " + autor);
    }

    // Método principal que se ejecuta al iniciar el programa
    public static void main(String[] args) {
        Libro libro1 = new Libro();     // Se crea una nueva instancia de Libro
        libro1.titulo = "1984";         // Se asigna el título
        libro1.autor = "George Orwell"; // Se asigna el autor
        libro1.mostrarInfo();           // Se llama al método para mostrar los datos
    }
}
```

---

## 🔄 Sesión 02: Tipos de datos y sentencias de control

🧵 **Recordatorio rápido**  
- Tipos primitivos, `var`, operadores aritméticos y lógicos.  
- Estructuras de control: `if`, `switch`, `for`, `while`, `do-while`, `for-each`.

💬 **Preguntas detonadoras**
- ¿En qué situaciones usaste `for` y en cuáles `while`?
- ¿Recuerdas alguna confusión que tuviste con operadores lógicos?

⚙️ **Ejercicio: Pares e impares**

Crear un programa que imprima los números del 1 al 10 y diga si son pares o impares.

```java
// Clase para imprimir si los números del 1 al 10 son pares o impares
public class Numeros {
    public static void main(String[] args) {
        for (int i = 1; i <= 10; i++) { // Bucle del 1 al 10
            if (i % 2 == 0) {           // Verifica si el número es divisible por 2
                System.out.println(i + " es par");
            } else {
                System.out.println(i + " es impar");
            }
        }
    }
}
```

---

## 🧱 Sesión 03: Clases y objetos: crea aplicaciones que permitan el ingreso de información

🧵 **Recordatorio rápido**  
- Creación de clases personalizadas, atributos, constructores, `static`, `final`, `Optional`.

💬 **Preguntas detonadoras**
- ¿Cuándo usaste `static` y cuándo decidiste no usarlo?
- ¿Lograste aplicar `Optional` en tus programas?

⚙️ **Ejercicio: Clase `Estudiante`**

Definir una clase `Estudiante` con método `saludar()` y ejecutarlo.

```java
// Clase que representa un estudiante
public class Estudiante {
    String nombre; // Atributo del nombre del estudiante

    // Constructor que inicializa el nombre
    public Estudiante(String nombre) {
        this.nombre = nombre;
    }

    // Método que imprime un saludo
    public void saludar() {
        System.out.println("Hola, soy " + nombre);
    }

    // Método principal
    public static void main(String[] args) {
        Estudiante e = new Estudiante("Ana"); // Crear estudiante
        e.saludar(); // Llamar al método saludar
    }
}
```
---

## 📦 Sesión 04: Elementos de una clase: implementa validación de datos

🧵 **Recordatorio rápido**  
- Métodos sobrescritos: `equals()`, `hashCode()`, `toString()`  
- `record` para clases inmutables y limpias  
- Encapsulamiento e inmutabilidad con `private final`, sin setters

💬 **Preguntas detonadoras**
- ¿Cuándo necesitaste comparar objetos y qué problemas enfrentaste?
- ¿Usaste `record`? ¿Qué te pareció?

⚙️ **Ejercicio: Uso de `record`**

Crear un `record` llamado `Producto` y mostrarlo por consola.

```java
// Clase principal que utiliza un record
public class DemoRecord {
    public static void main(String[] args) {
        Producto p1 = new Producto("Laptop", 1200.0); // Crear producto
        System.out.println(p1); // Imprimir detalles del producto
    }
}

// Record que representa un producto con nombre y precio
record Producto(String nombre, double precio) {}
```

---

## 🧬 Sesión 05: Diseño de clases (herencia y polimorfismo): reutiliza código existente por medio de herencia y polimorfismo

✅ **Recordatorio rápido**  
- `extends`, `implements`, `@Override`, clases abstractas e interfaces  
- Diferencia entre **herencia** ("es un") y **composición** ("tiene un")

💬 **Preguntas detonadoras**
- ¿Cuándo elegiste herencia y cuándo composición?
- ¿Te costó implementar interfaces?

⚙️ **Ejercicio: `Animal` y `Perro`**

Crear una clase `Animal`, subclase `Perro` y método `hacerSonido()` sobrescrito.

```java
// Clase base Animal con un método genérico
public class Animal {
    public void hacerSonido() {
        System.out.println("Sonido genérico");
    }
}

// Subclase Perro que sobrescribe el método hacerSonido
class Perro extends Animal {
    @Override
    public void hacerSonido() {
        System.out.println("Ladrido");
    }

    public static void main(String[] args) {
        Animal miAnimal = new Perro(); // Polimorfismo: Animal apunta a Perro
        miAnimal.hacerSonido(); // Ejecuta el método de Perro
    }
}
```

---

## 🧰 Sesión 06: Colecciones: utiliza diversas estructuras de datos de acuerdo al tipo de aplicación a desarrollar

✅ **Recordatorio rápido**  
- Estructuras dinámicas: `ArrayList`, `HashSet`, `HashMap`  
- Ordenamiento con `Comparable` y `Comparator`

💬 **Preguntas detonadoras**
- ¿Cuál colección usaste más y por qué?
- ¿Lograste ordenar tus objetos con `Comparator`?

⚙️ **Ejercicio: Lista ordenada**

Crear una `ArrayList` de nombres y ordenarla alfabéticamente.

```java
import java.util.*;

// Clase que demuestra cómo ordenar una lista
public class ListaOrdenada {
    public static void main(String[] args) {
        List<String> nombres = new ArrayList<>(); // Crear lista de nombres
        nombres.add("Luis");
        nombres.add("Ana");
        nombres.add("Carlos");

        Collections.sort(nombres); // Ordenar alfabéticamente

        System.out.println("Nombres ordenados:");
        for (String nombre : nombres) {
            System.out.println(nombre); // Imprimir cada nombre
        }
    }
}
```

---

## 📂 Sesión 07: Manejo de archivos: guarda información en un archivo de manera persistente

✅ **Recordatorio rápido**  
- `Path`, `Files.readString()`, `Files.write()`  
- Buenas prácticas con `try-with-resources` y validación de rutas

💬 **Preguntas detonadoras**
- ¿Pudiste leer o escribir un archivo con éxito?
- ¿Qué dudas tuviste sobre rutas relativas o absolutas?

⚙️ **Ejercicio: Escritura y lectura de archivo**

Escribir un texto en un archivo `notas.txt` y luego leerlo.

```java
import java.io.IOException;
import java.nio.file.*;

// Clase que escribe y lee un archivo usando NIO.2
public class Archivos {
    public static void main(String[] args) {
        Path ruta = Path.of("notas.txt"); // Definir la ruta del archivo

        try {
            // Escribir contenido en el archivo
            Files.write(ruta, "Primera nota desde Java".getBytes());

            // Leer el contenido del archivo
            String contenido = Files.readString(ruta);
            System.out.println("Contenido del archivo:\n" + contenido);
        } catch (IOException e) {
            System.out.println("Error de archivo: " + e.getMessage());
        }
    }
}
```

---

## 🛠️ Sesión 08: Buenas prácticas y manejo de errores en Java

✅ **Recordatorio rápido**  
- Refactorización, `code smells`, principios SOLID  
- Manejo de errores con `try-catch`, `throws`, excepciones personalizadas

💬 **Preguntas detonadoras**
- ¿Cuál principio SOLID aplicarías en tu código?
- ¿Cómo decidiste cuándo capturar una excepción?

⚙️ **Ejercicio: Excepción personalizada**

Crear una excepción personalizada `EdadNoValidaException` y lanzar un error si edad < 0.

```java
// Excepción personalizada para validar edad negativa
class EdadNoValidaException extends Exception {
    public EdadNoValidaException(String mensaje) {
        super(mensaje);
    }
}

// Clase que verifica si una edad es válida
public class VerificadorEdad {
    public static void verificarEdad(int edad) throws EdadNoValidaException {
        if (edad < 0) {
            throw new EdadNoValidaException("La edad no puede ser negativa.");
        } else {
            System.out.println("Edad válida: " + edad);
        }
    }

    public static void main(String[] args) {
        try {
            verificarEdad(-5); // Prueba con una edad inválida
        } catch (EdadNoValidaException e) {
            System.out.println("Error: " + e.getMessage());
        }
    }
}
```
---

### 🎤 Espacio abierto 

- Resolver dudas específicas de código o conceptos.
- Compartir aprendizajes, experiencias, errores comunes.
- Tips de práctica y siguientes pasos: ¿qué seguir estudiando?

---

⬅️ [**Anterior**](../Sesion-09/Readme.md)