🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 03**](../Readme.md) ➡️ / ⚡`Reto 04: Información de contacto (con Optional)`

---

## 🎯 Objetivo

📇 Implementar una clase `Empleado` que almacene información de contacto, usando la clase `Optional` para manejar datos que pueden estar ausentes (como teléfono o correo).

---

## 📝 Instrucciones

1. Crea una clase `Empleado` con los siguientes atributos:
   - `nombre` (String) — obligatorio
   - `telefono` (Optional<String>) — puede ser nulo
   - `correo` (Optional<String>) — puede ser nulo

2. Implementa:
   - Un **constructor** que reciba el nombre, teléfono y correo (pueden ser `null`).
   - Un método `mostrarContacto()` que:
     - Muestre el nombre del empleado.
     - Muestre el teléfono si está presente o diga “No disponible”.
     - Muestre el correo si está presente o diga “No disponible”.

3. En la clase `Main`:
   - Crea dos objetos de tipo `Empleado`:
     - Uno con todos los datos.
     - Otro sin teléfono ni correo.
   - Llama al método `mostrarContacto()` en ambos casos.

---

## 🧩 Salida esperada

```plaintext
👤 Empleado: Sandra
📞 Teléfono: 555-7890
✉️ Correo: sandra@empresa.com

👤 Empleado: Luis
📞 Teléfono: No disponible
✉️ Correo: No disponible
```

---

## ✅ Lo que se practica

- Creación y uso de objetos `Optional`
- Uso de `orElse()` para valores por defecto
- Diseño de clases con datos opcionales
- Evitar errores de `NullPointerException`

---

## 💡 ¿Sabías que...?

🧠 En entornos reales, muchos campos de un formulario pueden quedar vacíos. Usar `Optional` te permite programar pensando en esos casos sin errores.

🔒 En sistemas empresariales, controlar si una información está disponible ayuda a mantener integridad y seguridad en las operaciones.

---

## 📚 Recursos recomendados

🔗 [Java Optional - W3Schools](https://www.w3schools.com/java/java_optional.asp)

> Una guía clara y directa para entender qué es Optional y cómo se usa.

🔗 [Java Optional - Baeldung](https://www.baeldung.com/java-optional)

> Artículo profundo con ejemplos reales y buenas prácticas.

🔗 [Java Optional en Programiz](https://www.programiz.com/java-programming/optional)

> Recurso interactivo con ejercicios básicos y explicación sencilla.

--- 

🏆 Nos vemos en el siguiente reto, ¡mucho éxito!  

---

⬅️ [**Anterior**](../Ejemplo-04/Readme.md) | [**Siguiente**](../../Sesion-04/Readme.md)➡️