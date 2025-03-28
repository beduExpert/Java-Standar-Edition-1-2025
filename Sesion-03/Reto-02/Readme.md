🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 03**](../Readme.md) ➡️ / ⚡`Reto 02: Operaciones bancarias básicas`

---

### 🎯 Objetivo

🏦 Diseñar un sistema bancario sencillo que permita a los usuarios **consultar su saldo**, **realizar depósitos**, **simular transferencias**, y aplicar **sobrecarga de métodos** en operaciones comunes.

---

### 📝 Instrucciones

Imagina que estás desarrollando un módulo básico para una app de banca digital. Sigue estos pasos:

1. Crea una clase `CuentaBancaria` con los siguientes atributos:
   - `titular` (String)
   - `saldo` (double)

2. Agrega los siguientes métodos:
   - `consultarSaldo()` – muestra el saldo actual. *(sin retorno)*
   - `depositar(double monto)` – suma el monto al saldo. *(sin retorno, recibe un parámetro por valor)*
   - `transferir(double monto)` – devuelve `true` si hay fondos suficientes. *(con retorno)*
   - `transferir(double monto, String destinatario)` – sobrecarga que muestra a quién se transfiere el dinero.

3. En la clase `Main`, crea una cuenta con saldo inicial, realiza un depósito, y prueba las dos versiones del método `transferir`.

---

### 🧩 Salida esperada

```plaintext
👤 Titular: Mario
💰 Saldo actual: $500.0

📥 Depósito: $200.0
💰 Nuevo saldo: $700.0

🔁 Transferencia de $300.0 exitosa.
📤 Enviando $100.0 a: Ana

💰 Saldo final: $300.0
```

---


### 📚 Recursos recomendados 

🔗 [Métodos en Java – W3Schools](https://www.w3schools.com/java/java_methods.asp)
> Explicación clara sobre métodos, cómo se declaran, cómo se llaman, y la diferencia entre void y métodos con retorno.

🔗 [Paso de parámetros en Java – Programiz](https://www.programiz.com/java-programming/methods)
> Recurso interactivo que explica con ejemplos cómo funcionan los parámetros y el paso por valor en Java.

🔗 [Sobrecarga de métodos – JavaTPoint](https://www.javatpoint.com/method-overloading-in-java)
> Buena explicación sobre sobrecarga de métodos (method overloading) con múltiples ejemplos paso a paso.

🔗 [Java Methods Quiz – Tutorialspoint](https://www.tutorialspoint.com/java/java_online_quiz.htm)
> Pequeños quizzes interactivos para repasar métodos, clases, objetos, y más.

---

🏆 Nos vemos en el siguiente reto, ¡mucho éxito!  

---

⬅️ [**Anterior**](../Readme.md) | [**Siguiente**](../Ejemplo-03/Readme.md)➡️
