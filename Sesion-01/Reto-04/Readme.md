🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 01**](../Readme.md) ➡️ / ⚡`Reto 04: Definición de roles en una empresa`

## 🎯 Objetivo

⚒️ Utilizar una **`sealed class`** en Java para representar jerarquías de roles dentro de una empresa, controlando qué clases pueden heredar de una clase base. Este reto te ayudará a practicar conceptos modernos de diseño orientado a objetos.

---

## 📝 Instrucciones

👥 Este reto puede resolverse de forma individual o en equipo.

1. 🧱 Crea una **`sealed class`** llamada `Empleado` que represente un rol genérico dentro de la empresa.

2. 🚧 Especifica que solo se puede extender desde tres clases:
   - `Gerente`
   - `Desarrollador`
   - `Diseñador`

3. ✅ Marca las clases derivadas como `final` para evitar que puedan ser heredadas nuevamente.

4. 🖨️ En cada clase (`Gerente`, `Desarrollador`, `Diseñador`), crea un método llamado `mostrarRol()` que imprima un mensaje representando el rol del empleado. Por ejemplo:
   ```plaintext
   Rol: Desarrollador – Encargado de escribir y mantener el código fuente.
   ```

5. 🧪 En la clase `Principal`, crea un objeto de cada rol y llama al método `mostrarRol()`.

---

## 🎯 Desafío adicional (opcional)

🧠 Crea al menos **dos objetos de cada tipo de rol** (`Gerente`, `Desarrollador`, `Diseñador`) con nombres diferentes y llama al método `mostrarRol()` de cada uno. Esto reforzará la creación de múltiples objetos y el uso de métodos en clases concretas.

---

✅ Este reto te permite experimentar con las **sealed class**, reforzar jerarquías de herencia controlada y preparar el terreno para trabajar con estructuras más complejas en sesiones posteriores.

📘 Si necesitas repasar el uso de sealed classes, puedes consultar este recurso:  
🔗 [Sealed Classes – Oracle Docs](https://docs.oracle.com/en/java/javase/17/language/sealed-classes-and-interfaces.html)

---

🏆 ¡Buen trabajo! Con este reto estás aplicando una de las herramientas más modernas del lenguaje Java.

---

⬅️ [**Anterior**](../Ejemplo-04/Readme.md) | [**Siguiente**](../../Sesion-02/Readme.md)➡️