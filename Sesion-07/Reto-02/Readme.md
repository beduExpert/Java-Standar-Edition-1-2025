🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 07**](../Readme.md) ➡️ / ⚡`Reto 02: Procesamiento eficiente de logs de errores`

---

## 🎯 Objetivo

🧠 Aplicar el uso de `BufferedReader`, `try-with-resources` y manejo de excepciones para analizar grandes archivos de logs generados por pruebas automatizadas. Este reto simula una tarea del rol de **Automated Testing Engineer (QA)**, enfocada en el procesamiento eficiente de información y la trazabilidad de errores.

---

## 📝 Instrucciones

🧪 Imagina que eres parte del equipo de QA en una empresa que ejecuta pruebas automáticas durante la madrugada. Al amanecer, debes revisar un archivo `errores.log` que contiene miles de líneas con mensajes de error, advertencia y éxito.

Tu misión será **analizar el archivo de forma eficiente, detectar la frecuencia de errores y advertencias, y generar un resumen del análisis**.

### 🧩 Actividades

1. Crea una clase principal llamada `AnalizadorDeLogs`.
2. Usa `try-with-resources` para abrir el archivo `errores.log` con `BufferedReader`.
3. Lee el archivo línea por línea y cuenta cuántas veces aparece:
   - La palabra `"ERROR"`
   - La palabra `"WARNING"`
4. Al finalizar, imprime un resumen en consola con:
   - Total de líneas leídas
   - Cantidad de errores
   - Cantidad de advertencias
   - Porcentaje de líneas con errores y advertencias
5. Si el archivo no existe o hay algún problema, captura la excepción con `try-catch` y guarda el mensaje de error en un archivo `registro_fallos.txt`.

---

## 💡 Tip

✅ Usa `linea.contains("ERROR")` o `linea.contains("WARNING")` para facilitar el conteo de patrones.

---

📘 ¿Quieres repasar cómo funciona `BufferedReader` y `try-with-resources`?  
🔗 [BufferedReader – Oracle Docs](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/io/BufferedReader.html)  
🔗 [try-with-resources – Baeldung](https://www.baeldung.com/java-try-with-resources)

---

🏆 Este reto pone en práctica habilidades fundamentales para asegurar la calidad en entornos automatizados, mejorando la eficiencia y la gestión de errores en sistemas complejos.

---

⬅️ [**Anterior**](../Ejemplo-04/Readme.md) | [**Siguiente**](../../Sesion-08/Readme.md)➡️
