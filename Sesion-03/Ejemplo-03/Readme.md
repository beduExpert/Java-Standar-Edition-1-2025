🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 03**](../Readme.md) ➡️ / 📝 `Ejemplo 03 - Modificadores de acceso y encapsulación`

---

## 🎯 Objetivo

Comprender cómo se usan los **modificadores de acceso** (`private`, `protected`, `public`) para controlar la visibilidad de atributos y métodos, y cómo aplicar la **encapsulación** para proteger datos dentro de una clase.

---

## 📌 Escenario profesional

Imagina que estás desarrollando una clase `Usuario` en una aplicación bancaria. Necesitas proteger los datos sensibles del usuario como el número de cuenta y su saldo, mientras permites mostrar su nombre públicamente. Para ello, usarás modificadores de acceso.

---

## 🔒 1. Modificador `private`

Se usa para proteger atributos internos que no deben ser accesibles directamente desde fuera de la clase.

```java
public class Usuario {
    private String nombre;
    private double saldo;  // 🔒 No debe accederse directamente

    public Usuario(String nombre, double saldo) {
        this.nombre = nombre;
        this.saldo = saldo;
    }
}
```

---

## 🔑 2. Métodos `public` para acceder a atributos privados (encapsulación)

Permitimos acceso indirecto a través de métodos públicos (`getters` y `setters`).

```java
public String getNombre() {
    return nombre;
}

public double getSaldo() {
    return saldo;
}

public void depositar(double monto) {
    saldo += monto;
}
```

---

## 🚀 3. Clase principal que usa los métodos públicos

```java
public class Main {
    public static void main(String[] args) {
        Usuario u = new Usuario("Mario", 500.0);

        // Accedemos al nombre (método público)
        System.out.println("👤 Usuario: " + u.getNombre());

        // Accedemos al saldo usando método getter
        System.out.println("💰 Saldo inicial: $" + u.getSaldo());

        // Usamos un método público para modificar saldo
        u.depositar(250.0);
        System.out.println("💰 Saldo después del depósito: $" + u.getSaldo());
    }
}
```

---

## 🧠 ¿Y `protected`?

Aunque `protected` se usa más en herencia, aquí te mostramos su uso básico:

```java
public class Persona {
    protected String nacionalidad = "México";
}
```

```java
public class Empleado extends Persona {
    public void mostrarNacionalidad() {
        System.out.println("🌎 Nacionalidad: " + nacionalidad);
    }
}
```

---

## 🔍 Revisión rápida

| Modificador | Accesible desde misma clase | Mismo paquete | Subclases | Otras clases |
|-------------|------------------------------|---------------|-----------|--------------|
| `private`   | ✅                            | ❌            | ❌        | ❌           |
| `protected` | ✅                            | ✅            | ✅        | ❌           |
| `public`    | ✅                            | ✅            | ✅        | ✅           |

---

## 💡 ¿Sabías que...?

🔐 El uso de `private` junto con métodos `get` y `set` es el corazón de la **encapsulación**: protege tus datos y controla cómo se modifican.

🛡️ Un buen diseño orientado a objetos evita que los atributos sean públicos. En cambio, se accede a ellos mediante métodos controlados.

🏗️ Encapsular te permite cambiar la lógica interna sin afectar a quienes usan la clase, ideal para **escalabilidad y mantenimiento**.

---

📘 ¡Recuerda! Encapsular no es ocultar por completo, sino **dar acceso controlado**.

---

⬅️ [**Anterior**](../Reto-01/Readme.md) | [**Siguiente**](../Ejemplo-04/Readme.md)➡️
