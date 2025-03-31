
🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 08**](../Readme.md) ➡️ / ⚡`Reto 02: Monitoreo de consumo de recursos en servidores`

---

## 🎯 Objetivo

🧠 Desarrollar una herramienta en Java que permita leer registros de consumo de CPU por servidor, identifique duplicados, valide entradas numéricas y lance una excepción personalizada si se supera un umbral crítico. Se deben aplicar las buenas prácticas de rendimiento, manejo de errores y excepciones personalizadas.

---

## 📝 Instrucciones

🚀 Imagina que trabajas como **DevOps Engineer** en una empresa de servicios financieros. Tu tarea es crear una utilidad para el monitoreo de servidores.

### 🧩 Actividades

1. Crea una clase principal llamada `MonitorCPU` donde se ejecuta el flujo general.
2. Solicita al usuario ingresar el consumo de CPU de varios servidores (valores en porcentaje).
3. Aplica validación:
   - El valor debe ser numérico.
   - No se deben permitir registros duplicados (usa `HashSet`).
   - No se permiten valores negativos ni mayores a 100%.
4. Si el valor ingresado es mayor a 95%, lanza una excepción personalizada llamada `ConsumoCriticoException`.
5. Muestra mensajes informativos en consola si hay errores o si todo marcha correctamente.
6. Cierra cualquier recurso utilizado adecuadamente (`finally`).
7. Puedes simular la entrada con datos fijos o usando `Scanner`.

---

## 💡 Tip

✅ Recuerda que una excepción personalizada debe:
- Heredar de `Exception` (checked).
- Tener un constructor que reciba un mensaje.

---

📘 Recurso de apoyo:  
🔗 [Guía rápida de manejo de excepciones en Java – W3Schools](https://www.w3schools.com/java/java_try_catch.asp)

---

🏁 Este reto pone a prueba tu capacidad para integrar distintos enfoques de desarrollo limpio y seguro en un contexto real de automatización de infraestructura.

⬅️ [**Anterior**](../Ejemplo-05/Readme.md) | [**Siguiente**](../Readme.md)➡️
