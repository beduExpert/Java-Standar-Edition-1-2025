🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 05**](../Readme.md) ➡️ / 📝 `Ejemplo 03: Interfaces y Clases Abstractas`

---

## 🎯 Objetivo

Comprender la diferencia entre una **interfaz** y una **clase abstracta** en Java, aplicando ambos conceptos para estructurar el comportamiento de objetos con jerarquías complejas y funciones específicas.

---

## 🛠️ Escenario: Sistema de drones multifuncionales

Estás desarrollando un sistema para gestionar **drones autónomos**. Todos los drones comparten una estructura básica: tienen un identificador, deben despegar y aterrizar, y pueden realizar tareas específicas como vigilancia, entrega de paquetes o mapeo de terreno.

🔍 Para modelar este comportamiento, usaremos:

- Una **clase abstracta** `Drone`, que define la estructura y comportamientos comunes (atributos, métodos concretos y abstractos).
- Una **interfaz** `Vigilancia`, que define un comportamiento especializado opcional que ciertos drones pueden implementar.
- Otra **interfaz** `Entrega`, para drones de paquetería.

Este diseño nos permite usar **herencia simple con clase abstracta** y **herencia múltiple con interfaces** al mismo tiempo.

---

## 1️⃣ Clase abstracta: `Drone`

```java
public abstract class Drone {
    String id;

    public Drone(String id) {
        this.id = id;
    }

    public void despegar() {
        System.out.println("🚁 Drone " + id + " despegando...");
    }

    public void aterrizar() {
        System.out.println("🛬 Drone " + id + " aterrizando...");
    }

    // Método abstracto que cada tipo de drone debe implementar
    public abstract void ejecutarMision();
}
```

---

## 2️⃣ Interfaces: `Vigilancia` y `Entrega`

```java
public interface Vigilancia {
    void escanearArea();
}
```

```java
public interface Entrega {
    void entregarPaquete(String destino);
}
```

---

## 3️⃣ Clases concretas que implementan los comportamientos

### 🛰️ `DroneVigilancia`

```java
public class DroneVigilancia extends Drone implements Vigilancia {

    public DroneVigilancia(String id) {
        super(id);
    }

    @Override
    public void ejecutarMision() {
        System.out.println("🔍 Drone " + id + " iniciando misión de vigilancia.");
        escanearArea();
    }

    @Override
    public void escanearArea() {
        System.out.println("📷 Escaneando área en 360°...");
    }
}
```

### 📦 `DroneReparto`

```java
public class DroneReparto extends Drone implements Entrega {

    public DroneReparto(String id) {
        super(id);
    }

    @Override
    public void ejecutarMision() {
        System.out.println("📦 Drone " + id + " iniciando misión de entrega.");
        entregarPaquete("Zona 5B");
    }

    @Override
    public void entregarPaquete(String destino) {
        System.out.println("📍 Entregando paquete en: " + destino);
    }
}
```

---

## 4️⃣ Clase principal: `CentroControl`

```java
public class CentroControl {
    public static void main(String[] args) {
        Drone drone1 = new DroneVigilancia("DR-001");
        Drone drone2 = new DroneReparto("DR-002");

        drone1.despegar();
        drone1.ejecutarMision();
        drone1.aterrizar();

        System.out.println();

        drone2.despegar();
        drone2.ejecutarMision();
        drone2.aterrizar();
    }
}
```

---

## 🤔 ¿Cuándo usar una interfaz y cuándo una clase abstracta?

| Característica                       | Clase abstracta         | Interfaz                   |
|-------------------------------------|--------------------------|-----------------------------|
| Define atributos comunes            | ✅ Sí                    | ❌ No                      |
| Tiene métodos implementados         | ✅ Sí                    | ✅ Desde Java 8 (`default`) |
| Permite herencia múltiple           | ❌ No                    | ✅ Sí                      |
| Se usa para...                      | Estructura base común    | Contratos de comportamiento |

---

## 💡 Buenas prácticas

- ✅ Usa **clases abstractas** para compartir estructura y comportamiento general.
- ✅ Usa **interfaces** cuando diferentes clases deban compartir capacidades específicas pero no estructura.
- ✅ Una clase puede heredar de una clase abstracta **y** implementar múltiples interfaces sin problema.

---

📘 Recursos adicionales:

🔗 [Interfaces – W3Schools](https://www.w3schools.com/java/java_interface.asp)  
🔗 [Abstract Classes – Oracle Docs](https://docs.oracle.com/javase/tutorial/java/IandI/abstract.html)

---

⬅️ [**Anterior**](../Ejemplo-02/Readme.md) | [**Siguiente**](../Ejemplo-04/Readme.md)➡️