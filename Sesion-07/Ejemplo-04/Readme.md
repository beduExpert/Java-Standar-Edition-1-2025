🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 07**](../Readme.md) ➡️ / 📝 `Ejemplo 04: Buenas prácticas en manejo de archivos`

---

## 🎯 Objetivo

Aplicar buenas prácticas en el manejo de archivos en Java, usando **excepciones (`try-catch`)**, el bloque `try-with-resources` para liberar recursos automáticamente, y el uso de `BufferedReader` para una lectura más eficiente.

---

## 📌 ¿Por qué aplicar buenas prácticas?

Trabajar con archivos puede provocar errores comunes como:

- El archivo no existe
- No se tienen permisos para leerlo
- El archivo está dañado o vacío

Para evitar que tu programa se detenga abruptamente, es importante **capturar las excepciones** y manejar los recursos correctamente.

---

## 1️⃣ Uso básico de `try-catch` para leer un archivo

```java
import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;

public class LectorBasico {
    public static void main(String[] args) {
        Path ruta = Paths.get("datos.txt");

        try {
            String contenido = Files.readString(ruta);
            System.out.println("📄 Contenido del archivo:");
            System.out.println(contenido);
        } catch (IOException e) {
            System.out.println("❌ No se pudo leer el archivo: " + e.getMessage());
        }
    }
}
```

🔍 Este ejemplo:

- Intenta leer el contenido completo del archivo `datos.txt`.
- Si no existe o hay un problema, el error se muestra en consola.
- Es una forma segura y sencilla de **evitar que el programa se rompa**.

---

## 2️⃣ Uso de `try-with-resources` con `BufferedReader`

Cuando trabajamos con archivos grandes, conviene leer **línea por línea** con `BufferedReader`, y cerrar el recurso automáticamente.

```java
import java.io.BufferedReader;
import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;

public class LectorEficiente {
    public static void main(String[] args) {
        Path ruta = Paths.get("log-operaciones.txt");

        try (BufferedReader lector = Files.newBufferedReader(ruta)) {
            String linea;

            while ((linea = lector.readLine()) != null) {
                System.out.println("➡️ " + linea);
            }
        } catch (IOException e) {
            System.out.println("❌ Error al procesar el archivo: " + e.getMessage());
        }
    }
}
```

🧠 En este ejemplo:

- Se abre el archivo con `BufferedReader`, ideal para archivos largos.
- `try-with-resources` garantiza que el lector se cierre automáticamente.
- Se lee cada línea de forma eficiente y segura.

---

## ✅ Recomendaciones clave

| Práctica                     | ¿Por qué se usa?                                                  |
|-----------------------------|--------------------------------------------------------------------|
| `try-catch`                 | Captura errores como archivo no encontrado o sin permisos         |
| `BufferedReader`            | Optimiza lectura en archivos con muchas líneas                    |
| `try-with-resources`        | Libera el recurso automáticamente (no necesitas cerrar manualmente) |

---

## 💡 ¿Sabías que...?

- Si no manejas errores con `try-catch`, tu programa puede fallar por completo.
- `BufferedReader` es muy útil para leer logs, archivos de sensores, bitácoras, etc.
- Estas técnicas son comunes en sistemas industriales o automatizados que generan archivos de forma continua.

---

📘 Recurso adicional para repaso:  
🔗 [BufferedReader – Oracle Docs](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/io/BufferedReader.html)  
🔗 [try-with-resources – Baeldung](https://www.baeldung.com/java-try-with-resources)

---

⬅️ [**Anterior**](../Ejemplo-03/Readme.md) | [**Siguiente**](../Reto-04/Readme.md)➡️  