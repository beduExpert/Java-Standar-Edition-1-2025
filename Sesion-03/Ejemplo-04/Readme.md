🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 03**](../Readme.md) ➡️ / 📝 `Ejemplo 04: Optional y manejo seguro de valores nulos`

---

## 🎯 Objetivo

Evitar errores comunes como `NullPointerException` usando la clase `Optional` de Java para manejar valores que pueden estar ausentes.

---

## 📌 Escenario profesional

Estás desarrollando una aplicación de contacto con clientes. Algunos usuarios registran su número telefónico, pero otros no. Necesitas acceder a esa información sin que tu programa se rompa si no hay dato.

---

## 🧪 1. ¿Qué es `Optional`?

`Optional` es una clase contenedor que puede tener un valor o estar vacía. Así evitamos acceder directamente a `null`.

```java
import java.util.Optional;

public class Contacto {
    private Optional<String> telefono;

    public Contacto(String telefono) {
        this.telefono = Optional.ofNullable(telefono);
    }

    public Optional<String> getTelefono() {
        return telefono;
    }
}
```
---

## 🛠️ 2. Uso de `isPresent()` y `ifPresent()`

Detectamos si hay valor, y ejecutamos algo solo si existe.

```java
Contacto c1 = new Contacto("555-1234");
Contacto c2 = new Contacto(null);

// Usando isPresent (menos recomendado)
if (c1.getTelefono().isPresent()) {
    System.out.println("📞 Teléfono: " + c1.getTelefono().get());
}

// Mejor: usando ifPresent
c2.getTelefono().ifPresent(tel -> System.out.println("📞 Teléfono: " + tel));
```
---

## ⚙️ 3. Uso de `orElse()` y `orElseThrow()`

Devolvemos un valor por defecto o lanzamos una excepción si no hay valor.

```java
// orElse devuelve el valor si existe, o el alternativo si no
String tel1 = c1.getTelefono().orElse("No registrado");
String tel2 = c2.getTelefono().orElse("No registrado");

System.out.println("📞 Teléfono 1: " + tel1);
System.out.println("📞 Teléfono 2: " + tel2);

// orElseThrow lanza una excepción si no hay valor
String telSeguro = c1.getTelefono().orElseThrow(() -> new RuntimeException("⚠️ Teléfono obligatorio"));
```
---

## 📦 Buenas prácticas  

✔️ Usa `Optional` como retorno de métodos, no como atributo de clase (este ejemplo es con fines didácticos).

✔️ Prefiere `ifPresent()` sobre `isPresent()` + `get()`  

✔️ Usa `orElseGet()` si el valor alternativo es costoso de calcular.  

---

## 🔍 Revisión rápida

| Método         | ¿Que hace?                            |
|----------------|---------------------------------------|
| `isPresent()`	 | ¿Hay valor? Devuelve true o false.    |
| `ifPresent()`	 | Ejecuta código solo si hay valor.     |
| `orElse(valor)`| Devuelve el valor o uno por defecto.  |
| `orElseThrow()`| Lanza excepción si no hay valor.      |

---

## 💡 ¿Sabías que...?

🧠 `Optional` se introdujo en Java 8 para ayudarte a escribir código más seguro y legible.  
🚫 Ya no necesitas llenar tu código de `if (obj != null)`, ahora puedes usar flujos claros y expresivos.  
📚 Muchas APIs modernas de Java y frameworks como Spring usan `Optional` para devolver resultados de forma segura.  

---

⬅️ [**Anterior**](../Ejemplo-03/Readme.md) | [**Siguiente**](../Reto-02/Readme.md)➡️

