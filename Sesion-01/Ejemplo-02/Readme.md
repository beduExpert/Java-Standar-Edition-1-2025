🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 01**](../Readme.md) ➡️ / 📝 `Ejemplo 02: Programación orientada a objetos`

## 🎯 Objetivo

🔍 Comprender los conceptos fundamentales de la **Programación Orientada a Objetos (POO)** en Java mediante la creación de una clase simple y la instancia de objetos.

---

## 📌 ¿Qué es la programación orientada a objetos?

La **Programación Orientada a Objetos (POO)** es un estilo de programación que organiza el código en **clases** y **objetos**, inspirándose en el mundo real.

---

## 📌 ¿Qué es una clase?

Una **clase** es una plantilla que describe las características (**atributos**) y comportamientos (**métodos**) que puede tener un objeto.

```java
public class Estudiante {
    // Caracteristicas del estudiante
    String nombre;
    int edad;

    // Método que muestra un saludo con los datos del estudiante
    public void saludar() {
        System.out.println("Hola, mi nombre es " + nombre + " y tengo " + edad + " años.");
    }
}

```

---

## 🧱 ¿Qué es un objeto?

Un **objeto** es una instancia de una clase, es decir, un ejemplar concreto con valores específicos.

```java
public class Principal {
    public static void main(String[] args) {
        // Crear un nuevo objeto de tipo Estudiante
        Estudiante estudiante1 = new Estudiante();

        // Asignar valores a los atributos
        estudiante1.nombre = "Ana";
        estudiante1.edad = 20;

        // Llamar al método saludar() del objeto
        estudiante1.saludar();
    }
}
```

---

## 💡 ¿Sabías que...?

- Puedes crear **varios objetos** de una misma clase, cada uno con diferentes valores.
- En Java, todo gira en torno a las clases: incluso tipos como `String`, `Scanner` y `System` son clases.
- El **método main** (`public static void main`) es el punto de entrada de todo programa Java.

---

📘 Recurso adicional para repaso:  
🔗 [POO en Java – W3Schools](https://www.w3schools.com/java/java_oop.asp)

---

⬅️ [**Anterior**](../Reto-01/Readme.md) | [**Siguiente**](../Reto-02/Readme.md)➡️