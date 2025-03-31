🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 05**](../Readme.md) ➡️ / 📝 `Ejemplo 02: Herencia vs. Composición`

---

## 🎯 Objetivo

Diferenciar y aplicar los conceptos de **herencia** y **composición** en Java a través de un caso práctico, destacando cómo cada enfoque modela relaciones entre clases y cómo pueden combinarse para lograr sistemas más flexibles y reutilizables.

---

## 🛠️ Escenario: Vehículo autónomo

Imagina que trabajas en una empresa de ingeniería que desarrolla vehículos autónomos. Este tipo de vehículo combina las propiedades básicas de un vehículo tradicional con sistemas inteligentes que le permiten conducir sin intervención humana.

Para modelar este sistema, aplicaremos dos enfoques fundamentales de la programación orientada a objetos:

### ⚙️ Herencia: relación **“es un”**
El vehículo autónomo **es un** tipo especial de vehículo, por lo que puede heredar sus atributos y comportamientos generales. Usamos `extends` para establecer esta relación.

### 🧩 Composición: relación **“tiene un”**
El vehículo autónomo **tiene** componentes como un sensor GPS, una cámara, un sistema de inteligencia artificial, y un motor. Estos elementos no deberían heredarse, sino **componerse** como objetos internos. Así logramos un diseño más **modular, flexible y fácil de mantener**.

---

## 1️⃣ Clase base: `Vehiculo` (superclase)

```java
public class Vehiculo {
    String marca;

    public Vehiculo(String marca) {
        this.marca = marca;
    }

    public void encender() {
        System.out.println("🔑 El vehículo " + marca + " está encendido.");
    }
}
```

---

## 2️⃣ Subclase: `AutoAutonomo` hereda de `Vehiculo` y usa composición

```java
public class AutoAutonomo extends Vehiculo {
    SensorGPS gps;
    Camara camara;
    SistemaIA ia;
    Motor motor;

    public AutoAutonomo(String marca) {
        super(marca);
        this.gps = new SensorGPS();
        this.camara = new Camara();
        this.ia = new SistemaIA();
        this.motor = new Motor();
    }

    public void iniciarAutonomia() {
        System.out.println("🤖 Modo autónomo activado.");
        gps.localizar();
        camara.detectarObstaculos();
        ia.tomarDecision();
        motor.arrancar();
    }
}
```

---

## 3️⃣ Clases internas (composición)

```java
public class SensorGPS {
    public void localizar() {
        System.out.println("📍 GPS: posición actual obtenida.");
    }
}

public class Camara {
    public void detectarObstaculos() {
        System.out.println("📷 Cámara: obstáculos detectados en el camino.");
    }
}

public class SistemaIA {
    public void tomarDecision() {
        System.out.println("🧠 IA: trayectoria calculada.");
    }
}

public class Motor {
    public void arrancar() {
        System.out.println("🚗 Motor: velocidad regulada y marcha iniciada.");
    }
}
```

---

## 4️⃣ Clase principal: `Simulador`

```java
public class Simulador {
    public static void main(String[] args) {
        AutoAutonomo tesla = new AutoAutonomo("Tesla");

        tesla.encender();          // Método heredado de Vehiculo
        tesla.iniciarAutonomia();  // Método propio con composición
    }
}
```

---

## 🤔 Reflexión: ¿cuándo usar herencia y cuándo composición?

| Característica                    | Herencia (`extends`)            | Composición (`tiene un`)         |
|----------------------------------|----------------------------------|----------------------------------|
| Relación semántica               | "es un tipo de..."               | "tiene un..."                    |
| Flexibilidad                     | Menor (más rígida)               | Mayor (modular, reemplazable)    |
| Acoplamiento                     | Alto (hereda todo)               | Bajo (solo usa lo necesario)     |
| Cambios en clase base afectan...| Todas las subclases              | Solo si se usan directamente     |

---

## 💡 Buenas prácticas

- ✅ Usa **herencia** solo cuando la relación sea inequívoca y natural (ej. `Un Gato es un Animal`).
- ✅ Usa **composición** cuando una clase deba tener funcionalidades modulares y puedas reutilizarlas en diferentes contextos (ej. `Un Auto tiene un Motor`).
- ✅ **Prefiere composición sobre herencia** en diseño moderno orientado a objetos, por su bajo acoplamiento y mejor mantenibilidad.

---

📘 Recurso recomendado:  
🔗 [Preferir Composición sobre Herencia – Clean Code](https://en.wikipedia.org/wiki/Composition_over_inheritance)

---

⬅️ [**Anterior**](../Ejemplo-01/Readme.md) | [**Siguiente**](../Reto-01/Readme.md)➡️