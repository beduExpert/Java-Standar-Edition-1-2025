🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 07**](../Readme.md) ➡️ / 📝 `Ejemplo 02: Lectura y escritura con Files.readString() y Files.write()`

---

## 🎯 Objetivo

Aprender a utilizar los métodos `Files.readString()` y `Files.write()` para realizar operaciones de lectura y escritura de archivos de texto de forma sencilla, aprovechando las mejoras de la API NIO.2.

---

## 📌 ¿Por qué usar `Files.readString()` y `Files.write()`?

Estas funciones introducidas en Java 11 simplifican el manejo de archivos en comparación con versiones anteriores. Son ideales cuando:

- Solo necesitas leer o escribir texto completo.
- No requieres flujo por líneas ni procesamiento complejo.

---

## 📚 Métodos clave

| Método              | Descripción                                                          |
|---------------------|----------------------------------------------------------------------|
| `Files.readString()`| Lee el contenido completo de un archivo como una cadena (`String`)  |
| `Files.write()`     | Escribe una cadena en un archivo. Si no existe, lo crea; si existe, lo sobrescribe |

---

## 🧪 Código de ejemplo: Escribir y luego leer un archivo de texto

```java
import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;

public class LecturaEscrituraArchivos {
    public static void main(String[] args) {
        // 1. Definir la ruta del archivo
        Path ruta = Paths.get("src/Ejemplo_02/notas.txt");

        // 2. Contenido a escribir en el archivo
        String contenido = "📘 Este es un archivo de prueba.\nAquí aprendemos a escribir y leer en Java.";

        try {
            // 3. Escribir contenido en el archivo (crea o sobrescribe)
            Files.write(ruta, contenido.getBytes());
            System.out.println("✅ Archivo escrito exitosamente.");

            // 4. Leer el contenido completo como String
            String textoLeido = Files.readString(ruta);
            System.out.println("📄 Contenido leído:");
            System.out.println(textoLeido);

        } catch (IOException e) {
            System.out.println("❌ Error al trabajar con el archivo: " + e.getMessage());
        }
    }
}
```

---

## 🧠 ¿Qué se está haciendo?

- `Files.write()` convierte el texto a bytes y lo guarda en el archivo especificado.
- `Files.readString()` devuelve el contenido completo como una cadena de texto.
- Se usa `try-catch` para capturar errores como permisos o rutas inválidas.

---

## 📌 Consideraciones importantes

- Si el archivo **no existe**, `Files.write()` lo crea automáticamente.
- Si **ya existe**, su contenido será reemplazado (¡cuidado!).
- Para evitar sobrescribir, puedes usar una validación previa con `Files.exists(ruta)`.

---

## 💡 ¿Sabías que...?

- Puedes usar `StandardOpenOption.APPEND` para **agregar contenido** sin borrar lo anterior:
  ```java
  Files.write(ruta, "Otra línea\n".getBytes(), StandardOpenOption.APPEND);
  ```

- `Files.readString()` es ideal para archivos pequeños o medianos. Para archivos grandes, es mejor `BufferedReader`.

---

📘 Recurso adicional para repaso:  
🔗 [Clase Files – Oracle Docs](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/nio/file/Files.html)

---

⬅️ [**Anterior**](../Ejemplo-01/Readme.md) | [**Siguiente**](../Reto-01/Readme.md)➡️