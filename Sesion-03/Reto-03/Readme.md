🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 03**](../Readme.md) ➡️ / ⚡`Reto 04: Registro de paciente (Encapsulación y privacidad)`

---

## 🎯 Objetivo

🩺 Diseñar una clase que represente a un **paciente** en una aplicación médica, aplicando **modificadores de acceso (`private`, `public`)** y el principio de **encapsulación** para proteger datos sensibles como edad y diagnóstico.

---

## 📝 Instrucciones

1. Crea una clase `Paciente` con los siguientes atributos:
   - `nombre` (String) → debe ser **público**
   - `edad` (int) → debe ser **privado**
   - `diagnostico` (String) → debe ser **privado**

2. Agrega un **constructor** que inicialice todos los atributos.

3. Implementa métodos públicos para:
   - Mostrar el nombre del paciente.
   - Mostrar la edad y el diagnóstico.
   - Modificar la edad del paciente.
   - Cambiar el diagnóstico.

4. Crea una clase `Main` para:
   - Instanciar un paciente.
   - Mostrar sus datos (usando métodos públicos).
   - Modificar su edad y diagnóstico (también mediante métodos públicos).
   - Mostrar nuevamente los datos modificados.

---

## 🧩 Salida esperada

```plaintext
👤 Paciente: Laura
🎂 Edad: 30
🩺 Diagnóstico: Hipertensión

🔄 Actualizando datos...

🎂 Edad: 31
🩺 Diagnóstico: Controlado
```

---

## ✅ Lo que se practica

- Uso de `private` para proteger atributos.
- Implementación de `getters` y `setters`.
- Encapsulación de datos sensibles.
- Separación entre lógica interna y acceso externo.

---

## 💡 ¿Sabías que...?

🔐 En el desarrollo de software médico, los datos de pacientes deben protegerse por normativas como la **Ley General de Protección de Datos Personales**. Java ayuda a implementar esa seguridad desde el diseño del código.

🔍 Encapsular no es solo buena práctica técnica, sino también una forma de **proteger la privacidad de los usuarios**.

---

🏆 Nos vemos en el siguiente reto, ¡mucho éxito!  

---

⬅️ [**Anterior**](../Readme.md) | [**Siguiente**](../Ejemplo-04/Readme.md)➡️
