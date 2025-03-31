🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 05**](../Readme.md) ➡️ / 📝 `Ejemplo 01: Herencia en Java`

---

## 🎯 Objetivo

👨‍💻 Comprender cómo funciona la **herencia** en Java mediante la creación de una clase base y una subclase que hereda sus atributos y métodos. Exploraremos también el uso de `super` para acceder al constructor de la clase padre.

---

## 🧱 ¿Qué es la herencia?

La **herencia** permite que una clase (subclase) herede las características (atributos y métodos) de otra clase (superclase). Esto promueve la reutilización de código y favorece una estructura más organizada.

---

## 🛠️ Ejemplo: sistema de notificaciones

Imagina que estás desarrollando un sistema que envía diferentes tipos de notificaciones: correos electrónicos, mensajes SMS, y alertas en la app. Todos estos comparten una estructura común, pero tienen comportamientos muy específicos.

---

## 1️⃣ Clase base: `Notificacion`

Creamos una clase base que contiene atributos y un método común:

```java
public class Notificacion {
    String mensaje;

    public Notificacion(String mensaje) {
        this.mensaje = mensaje;
    }

    public void enviar() {
        System.out.println("📢 Enviando notificación: " + mensaje);
    }
}
```

---

## 2️⃣ Subclase: `NotificacionEmail`

Ahora creamos una clase que **hereda** de `Notificacion` usando `extends` y sobrecargamos el comportamiento:

```java
public class NotificacionEmail extends Notificacion {
    String destinatario;

    public NotificacionEmail(String mensaje, String destinatario) {
        super(mensaje); // Llamamos al constructor de la clase base
        this.destinatario = destinatario;
    }

    public void enviarEmail() {
        System.out.println("📧 Enviando email a " + destinatario + ": " + mensaje);
    }
}
```

---

## 3️⃣ Clase principal: `Sistema`

Aquí probamos la herencia creando una instancia de `NotificacionEmail`:

```java
public class Sistema {
    public static void main(String[] args) {
        NotificacionEmail email = new NotificacionEmail("Tu pedido ha sido enviado", "ana@correo.com");

        // Llamamos a métodos heredados y propios
        email.enviar();        // Método heredado
        email.enviarEmail();   // Método propio
    }
}
```

---

## 📌 Observaciones clave

- Usamos `extends` para establecer herencia.
- Con `super()` llamamos al constructor de la clase base.
- Podemos acceder a métodos y atributos de la clase base directamente desde la subclase.

---

## 💡 ¿Sabías que...?

- Puedes tener múltiples niveles de herencia, aunque Java **no permite herencia múltiple directa** (una clase no puede extender de dos clases).
- Las clases en Java extienden implícitamente de `Object` si no se indica lo contrario.
- El modificador `protected` permite a las subclases acceder a miembros de la superclase desde otro paquete.

---

📘 Recurso adicional para repaso:  
🔗 [Herencia en Java – W3Schools](https://www.w3schools.com/java/java_inheritance.asp)

---

⬅️ [**Anterior**](../Readme.md) | [**Siguiente**](../Ejemplo-02/Readme.md)➡️  