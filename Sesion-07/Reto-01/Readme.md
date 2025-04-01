🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 07**](../Readme.md) ➡️ / ⚡`Reto 01: Registro de parámetros de simulación`

---

## 🎯 Objetivo

🧠 Aplicar las clases `Path` y `Files` de la API `java.nio.file` (NIO.2) para crear un archivo de configuración de simulación, verificar su existencia y leer su contenido. Este ejercicio simula una tarea real del rol de **Process Simulation Engineer**, donde se documentan los parámetros antes de ejecutar una corrida de simulación.

---

## 📝 Instrucciones

⚙️ Imagina que estás trabajando como **process simulation engineer** en una planta de manufactura digital. Antes de correr cualquier modelo, debes registrar los parámetros de entrada en un archivo de configuración.

Tu misión será **crear un programa en Java que genere este archivo, valide su existencia y luego lo lea para su verificación**.

### 🧩 Actividades

1. Crea una clase principal llamada `RegistroSimulacion`.
2. Usa `Path` y `Paths.get()` para definir la ruta del archivo `parametros.txt`, dentro de una carpeta `config/`.
3. Crea un `String` con parámetros como:
   - Tiempo de ciclo: 55.8 segundos
   - Velocidad de línea: 1.2 m/s
   - Número de estaciones: 8
4. Utiliza `Files.write()` para guardar el contenido en el archivo. Si la carpeta `config/` no existe, créala previamente.
5. Usa `Files.exists()` para validar que el archivo fue creado correctamente.
6. Lee el archivo con `Files.readString()` y muestra su contenido en consola.

---

## 💡 Tip

✅ Puedes encapsular la lógica de escritura y lectura en métodos separados como `guardarParametros()` y `leerParametros()` para mejorar la legibilidad.

---

📘 ¿Quieres repasar cómo funcionan `Path`, `Files.write()` o `Files.readString()`?  
🔗 [Documentación oficial de NIO.2 – Oracle](https://docs.oracle.com/javase/tutorial/essential/io/fileio.html)

---

🏆 Este reto te acerca a un escenario real en simulación industrial, donde la trazabilidad y correcta documentación de parámetros es clave para garantizar la calidad y reproducibilidad de resultados.

---

⬅️ [**Anterior**](../Ejemplo-02/Readme.md) | [**Siguiente**](../Ejemplo-03/Readme.md)➡️
