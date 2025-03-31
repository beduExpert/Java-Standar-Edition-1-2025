🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 05**](../Readme.md) ➡️ / 📝 `Ejemplo 04: Polimorfismo y uso de @Override`

---

## 🎯 Objetivo

Comprender el concepto de **polimorfismo** en Java, observando cómo diferentes clases pueden redefinir el mismo método de forma personalizada. También se destaca el uso de la anotación `@Override` para asegurar que la sobrescritura sea válida y clara.

---

## 🛠️ Escenario: Animales robóticos

Imagina que estás desarrollando un software para controlar **animales robóticos**. Todos ellos deben responder a una orden común llamada `hacerSonido()`, pero el resultado debe variar según el tipo de robot.

Para esto:

- Usamos una **clase base** `AnimalRobot` con un método `hacerSonido()`.
- Creamos subclases como `PerroRobot`, `GatoRobot` y `PajaroRobot` que **sobrescriben** ese método con su propia implementación.
- Usamos el **polimorfismo** para invocar el mismo método sin importar el tipo de objeto.

---

## 1️⃣ Clase base: `AnimalRobot`

```java
public class AnimalRobot {
    public void hacerSonido() {
        System.out.println("🔊 Sonido genérico de robot animal...");
    }
}
```

---

## 2️⃣ Subclases con sobrescritura de método

### 🐶 `PerroRobot`

```java
public class PerroRobot extends AnimalRobot {
    @Override
    public void hacerSonido() {
        System.out.println("🐶 PerroRobot: Guau Guau Digital");
    }
}
```

### 🐱 `GatoRobot`

```java
public class GatoRobot extends AnimalRobot {
    @Override
    public void hacerSonido() {
        System.out.println("🐱 GatoRobot: Miau Miau Mecánico");
    }
}
```

### 🐦 `PajaroRobot`

```java
public class PajaroRobot extends AnimalRobot {
    @Override
    public void hacerSonido() {
        System.out.println("🐦 PajaroRobot: Pío Pío Cibernético");
    }
}
```

---

## 3️⃣ Clase principal: `CentroControl`

```java
public class CentroControl {
    public static void main(String[] args) {
        AnimalRobot[] zoologico = {
            new PerroRobot(),
            new GatoRobot(),
            new PajaroRobot()
        };

        for (AnimalRobot robot : zoologico) {
            robot.hacerSonido();  // Polimorfismo en acción
        }
    }
}
```

---

## 🤖 ¿Qué es el polimorfismo?

Es la capacidad que tiene una **referencia de tipo padre** de ejecutar métodos definidos en una **clase hija sobrescrita**, permitiendo escribir código más **genérico y reutilizable**.

### 🔍 ¿Y `@Override`?

La anotación `@Override`:

- Garantiza que estamos **realmente sobrescribiendo** un método de la superclase.
- Lanza error si escribimos mal el nombre del método o su firma.
- Mejora la legibilidad del código para otros desarrolladores.

---

## 💡 Buenas prácticas

- ✅ Siempre usa `@Override` al sobrescribir métodos.
- ✅ Usa referencias del tipo base (`AnimalRobot`) cuando quieras aplicar polimorfismo.
- ✅ Aprovecha la sobrescritura para adaptar el comportamiento sin duplicar código.

---

📘 Recurso recomendado:  
🔗 [Polimorfismo – W3Schools](https://www.w3schools.com/java/java_polymorphism.asp)

---

⬅️ [**Anterior**](../Ejemplo-03/Readme.md) | [**Siguiente**](../Reto-02/Readme.md)➡️  