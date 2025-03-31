
🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 08**](../Readme.md) ➡️ / 📖 `Ejemplo 05: Uso de throw, throws y excepciones personalizadas`

---

## 🎯 Objetivo

⚠️ Aplicar el uso de `throw`, `throws` y la creación de excepciones personalizadas en Java para manejar errores específicos del negocio, mejorando la claridad del código y la experiencia del usuario.

---

## 🧠 Recordemos

En Java, puedes **crear y lanzar tus propias excepciones** cuando las situaciones de error no se ajustan a las clases de error predefinidas del lenguaje.

#### 🔹 `throw`  
Se usa para **lanzar una excepción** desde una parte específica del código.  

#### 🔹 `throws`  
Se usa para **declarar** que un método puede lanzar una excepción, permitiendo que otro método sea responsable de manejarla.

#### 🔹 Excepciones personalizadas  
Te permiten definir errores específicos para tu lógica de negocio, con nombres y mensajes claros.

---

## 💼 Ejemplo 

Imagina que trabajas como **Customer Experience (CX) Manager**. Estás desarrollando una herramienta interna que mide la satisfacción del cliente con base en encuestas (puntajes del 1 al 5). Si alguien ingresa un valor fuera de rango, quieres lanzar una excepción personalizada llamada `CalificacionInvalidaException`.

Esto permite que otros desarrolladores del equipo comprendan de inmediato qué está ocurriendo sin depender de mensajes genéricos o errores del sistema.

---

### 💻 Código completo

```java
// Paso 1: Crear la excepción personalizada
public class CalificacionInvalidaException extends Exception {
    public CalificacionInvalidaException(String mensaje) {
        super(mensaje);
    }
}
```

```java
// Paso 2: Clase que lanza la excepción
public class EncuestaSatisfaccion {

    // Este método valida que la calificación esté entre 1 y 5
    public static void registrarCalificacion(int calificacion) throws CalificacionInvalidaException {
        if (calificacion < 1 || calificacion > 5) {
            throw new CalificacionInvalidaException("La calificación debe estar entre 1 y 5.");
        }

        System.out.println("✅ Calificación registrada: " + calificacion);
    }
}
```

```java
// Paso 3: Clase principal que maneja la excepción
import java.util.Scanner;

public class CXManagerApp {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        try {
            System.out.print("Ingrese la calificación del cliente (1 a 5): ");
            int input = scanner.nextInt();

            EncuestaSatisfaccion.registrarCalificacion(input);

        } catch (CalificacionInvalidaException e) {
            System.out.println("❌ Error de validación: " + e.getMessage());

        } catch (Exception e) {
            System.out.println("❌ Error inesperado: " + e.getMessage());

        } finally {
            scanner.close();
            System.out.println("📦 Recurso liberado correctamente.");
        }
    }
}
```

### 🧠 ¿Qué hicimos?

- Creamos una clase de excepción personalizada para casos específicos  
- Lanzamos la excepción con `throw` dentro del método que valida  
- Declaramos el uso de `throws` para advertir que ese método puede fallar  
- Capturamos y mostramos el error de manera clara y amigable

---

## 🔄 ¿Qué aprendimos?

✅ `throw` sirve para **lanzar** errores personalizados  
✅ `throws` sirve para **declarar** que un método puede lanzar errores  
✅ Las excepciones personalizadas hacen el código más **legible, mantenible y profesional**

---

## 💡 ¿Sabías que...?

- Muchas API modernas utilizan excepciones personalizadas para representar errores del negocio como `PagoInvalidoException`, `UsuarioNoAutorizadoException`, etc.

- Un buen mensaje de error puede ser la diferencia entre una buena y una mala experiencia para otros desarrolladores o usuarios.

---

📘 Recurso recomendado:  
🔗 https://www.baeldung.com/java-new-custom-exception

---

⬅️ [**Anterior**](../Ejemplo-04/Readme.md) | [**Siguiente**](../Reto-02/Readme.md)➡️