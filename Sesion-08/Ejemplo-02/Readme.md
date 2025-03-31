
🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 08**](../Readme.md) ➡️ / 📝 `Ejemplo 02: Principios SOLID en Java`

---

## 🎯 Objetivo

🔍 Aplicar los principios SOLID para mejorar el diseño de clases en Java, generando estructuras más limpias, mantenibles y escalables, usando ejemplos del mundo profesional actual.

---

## 👩‍💻 Contexto 

Trabajas programando en Java dentro de una startup logística enfocada en desarrollar un sistema de tracking de paquetes. El sistema comenzó simple, pero ha ido creciendo, y las clases ya están empezando a mezclarse con múltiples responsabilidades 😖.

Tu tarea es aplicar los **principios SOLID**✨ para reorganizar el diseño y asegurar que sea más claro y flexible para futuras mejoras.

---

## 🧠 Recordemos que...

Los principios **SOLID** te ayudan a mantener el código organizado, modular y fácil de modificar:

| Letra | Principio | ¿Qué busca? | Ejemplo práctico |
|-------|-----------|-------------|------------------|
| S | **Responsabilidad Única** | Una clase debe hacer solo una cosa. | `Cliente` guarda datos, `ImpresoraCliente` imprime. |
| O | **Abierto/Cerrado** | El código debe permitir extensiones, sin modificar lo existente. | Nuevas reglas de descuento se agregan con nuevas clases. |
| L | **Sustitución de Liskov** | Las subclases deben funcionar igual que sus clases padre. | `Perro` y `Gato` deben comportarse como `Animal`. |
| I | **Segregación de Interfaces** | No obligar a implementar lo que no se necesita. | `Imprimible` solo tiene `imprimir()`. |
| D | **Inversión de Dependencias** | Depender de abstracciones, no implementaciones. | Usar `IMotor` en lugar de una clase `MotorElectrico`. |

---

## 💼 Ejemplo 

Queremos modelar un sistema de seguimiento de paquetes. Inicialmente, tenemos una clase que **almacena datos del paquete, imprime su estado, y calcula el costo del envío**. Veamos cómo luce:

### 💻 Código sin aplicar SOLID

```java
public class Paquete {
    private String destinatario;
    private double peso;

    public Paquete(String destinatario, double peso) {
        this.destinatario = destinatario;
        this.peso = peso;
    }

    public void imprimirEtiqueta() {
        System.out.println("Enviando a: " + destinatario);
    }

    public double calcularCostoEnvio() {
        return peso * 10.5; // tarifa fija por kilo
    }
}
```

### 🚨 Problemas detectados

- 🔴 Incumple **SRP**: imprime e implementa lógica de negocio.
- 🔴 Incumple **OCP**: si cambian las reglas de costos, hay que modificar esta clase.
- 🔴 Incumple **DIP**: la clase usa lógica concreta de cálculo sin permitir flexibilidad.

---

### ✅ Código refactorizado aplicando SOLID

```java
// SRP: Clase solo para datos
public class Paquete {
    private String destinatario;
    private double peso;

    public Paquete(String destinatario, double peso) {
        this.destinatario = destinatario;
        this.peso = peso;
    }

    public String getDestinatario() {
        return destinatario;
    }

    public double getPeso() {
        return peso;
    }
}

// ISP: Interfaz específica para impresión
interface Imprimible {
    void imprimirEtiqueta(Paquete paquete);
}

// Clase que imprime el estado del paquete
public class ImpresoraEtiqueta implements Imprimible {
    public void imprimirEtiqueta(Paquete paquete) {
        System.out.println("📦 Envío a: " + paquete.getDestinatario());
    }
}

// DIP + OCP: Interfaz para estrategia de costo de envío
interface EstrategiaCostoEnvio {
    double calcularCosto(Paquete paquete);
}

// Implementación concreta de la estrategia estándar
public class CostoEnvioEstandar implements EstrategiaCostoEnvio {
    public double calcularCosto(Paquete paquete) {
        return paquete.getPeso() * 10.5;
    }
}

// Clase de servicio que aplica inversión de dependencias
public class ServicioEnvio {
    private EstrategiaCostoEnvio estrategia;

    public ServicioEnvio(EstrategiaCostoEnvio estrategia) {
        this.estrategia = estrategia;
    }

    public double obtenerCostoEnvio(Paquete paquete) {
        return estrategia.calcularCosto(paquete);
    }
}
```

---

### 🧪 Uso en el método `main`

```java
public class Main {
    public static void main(String[] args) {
        Paquete paquete = new Paquete("Fernanda Loera", 2.5);

        Imprimible impresora = new ImpresoraEtiqueta();
        impresora.imprimirEtiqueta(paquete);

        EstrategiaCostoEnvio estrategia = new CostoEnvioEstandar();
        ServicioEnvio servicio = new ServicioEnvio(estrategia);

        double costo = servicio.obtenerCostoEnvio(paquete);
        System.out.println("💰 Costo de envío: $" + costo);
    }
}
```

---

## 🔄 ¿Qué aprendimos?

✅ **Separar responsabilidades** mejora el diseño  
✅ **Abrir a extensión y cerrar a modificación** previene errores futuros  
✅ **Usar interfaces** permite flexibilidad y escalabilidad  
✅ **Invertir dependencias** facilita el cambio de comportamiento sin tocar la lógica principal

---

## 💡 ¿Sabías que...?

- Los principios SOLID te ayudan a evitar el “código espagueti 🍝”, facilitando que nuevos desarrolladores entiendan y mantengan tu proyecto desde el primer día.

- Aplicar SOLID desde etapas tempranas del desarrollo reduce drásticamente el costo de mantenimiento y retrabajo a largo plazo. 💸

- Empresas como Amazon 🛒 y Google 🌐 suelen evaluar el conocimiento de SOLID en entrevistas técnicas para roles de desarrollo backend y arquitectura de software.

---

📘 Recurso recomendado:  
🔗 https://www.baeldung.com/solid-principles

---


⬅️ [**Anterior**](../Ejemplo-01/Readme.md) | [**Siguiente**](../Reto-01/Readme.md) ➡️