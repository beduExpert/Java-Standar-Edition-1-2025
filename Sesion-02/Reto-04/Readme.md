🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 02**](../Readme.md) ➡️ / ⚡`Reto 04: Cajero automático simple`

## 🎯 Objetivo

💻 Implementar un programa que simule un **cajero automático básico**, aplicando estructuras de control como `while`, `switch`, `break` y `continue` para navegar entre opciones y validar operaciones del usuario.

---

## 📝 Instrucciones

👥 Puedes resolver este reto de forma individual o en parejas.

1. 🏗️ Crea una **clase** llamada `CajeroAutomatico`.

2. 💸 En el método `main`, define un **saldo inicial** (por ejemplo: `saldo = 1000.0`).

3. 📋 Muestra un **menú interactivo** en consola con las siguientes opciones:
   ```
   Bienvenido al cajero automático
   1. Consultar saldo
   2. Depositar dinero
   3. Retirar dinero
   4. Salir
   ```

4. 🔁 El programa debe repetirse usando un `while` hasta que el usuario elija salir (`opción 4`).

5. 🧠 Utiliza un `switch` para manejar las opciones:
   - ✅ **1. Consultar saldo** → Mostrar el saldo actual.
   - 💰 **2. Depositar dinero** → Pedir monto a depositar y sumarlo al saldo.
   - 💸 **3. Retirar dinero** → Pedir monto a retirar y:
     - ⚠️ Validar si hay saldo suficiente.
     - ❌ Si no hay suficiente, mostrar un mensaje y continuar sin restar.
   - 👋 **4. Salir** → Mostrar mensaje de despedida y terminar el programa.

6. 🧭 Controla el flujo con `break` y `continue` donde sea necesario.

---

## 🎯 Desafío adicional (opcional)

🧠 Si el usuario ingresa una **opción inválida**, muestra un mensaje de error y vuelve a mostrar el menú sin detener el programa.

---

💡 Este reto te ayudará a practicar el uso de ciclos `while`, control de flujo, validación de condiciones y entradas básicas del usuario en un contexto realista.

---

🏆 Nos vemos en el siguiente reto, ¡mucho éxito! 🎉

---

⬅️ [**Anterior**](../Ejemplo-04/Readme.md) | [**Siguiente**](../../Sesion-03/Readme.md)➡️