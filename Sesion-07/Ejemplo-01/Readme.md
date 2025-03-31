🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 07**](../Readme.md) ➡️ / 📝 `Ejemplo 01: Introducción a java.nio.file (NIO.2)`

---

## 🎯 Objetivo

Comprender los fundamentos del paquete `java.nio.file`, utilizando las clases `Path` y `Files` para trabajar con rutas y archivos de forma más practica, moderna y segura que con la antigua API de `java.io`.

---

## 📌 ¿Qué es `java.nio.file`?

A partir de Java 7, se introdujo **NIO.2** (New I/O), una actualización importante del sistema de entrada/salida que permite:

- Manipular rutas de archivo como objetos (`Path`)
- Realizar operaciones sobre archivos y directorios con utilidades (`Files`)
- Mejorar el manejo de errores, rendimiento y portabilidad entre sistemas

---

## 📦 Clases clave en este ejemplo

| Clase         | Descripción breve                                           |
|---------------|-------------------------------------------------------------|
| `Path`        | Representa rutas en el sistema de archivos                  |
| `Paths`       | Clase de utilidad para construir objetos `Path`             |
| `Files`       | Métodos estáticos para operaciones con archivos y carpetas  |

---

## 🧪 Código de ejemplo: Creación y verificación de rutas

```java
import java.nio.file.Path;
import java.nio.file.Paths;
import java.nio.file.Files;
import java.io.IOException;

public class ExploradorArchivos {
    public static void main(String[] args) {
        // 1. Crear un objeto Path que apunte a un archivo
        Path rutaArchivo = Paths.get("documentos/ejemplo.txt");

        // 2. Imprimir la ruta absoluta del archivo
        System.out.println("📁 Ruta absoluta: " + rutaArchivo.toAbsolutePath());

        // 3. Verificar si el archivo existe
        if (Files.exists(rutaArchivo)) {
            System.out.println("✅ El archivo existe.");
        } else {
            System.out.println("❌ El archivo NO existe.");
        }

        // 4. Verificar si es un archivo o directorio
        if (Files.isDirectory(rutaArchivo)) {
            System.out.println("📂 Es un directorio.");
        } else {
            System.out.println("📄 Es un archivo.");
        }

        // 5. Verificar permisos
        System.out.println("🔒 ¿Se puede leer?: " + Files.isReadable(rutaArchivo));
        System.out.println("✏️ ¿Se puede escribir?: " + Files.isWritable(rutaArchivo));
    }
}
```

---

## 🧠 Explicación del ejemplo

- Se construye una ruta relativa usando `Paths.get("documentos/ejemplo.txt")`
- Se imprimen propiedades como:
  - Ruta absoluta
  - Existencia
  - Tipo (archivo o directorio)
  - Permisos (lectura y escritura)

---

## 📦 Recomendaciones al trabajar con rutas

- Usa `Path` y `Files` en lugar de `File` de `java.io`
- Siempre verifica si el archivo existe antes de manipularlo
- Prefiere rutas **relativas** en desarrollo, y **absolutas** si el archivo no cambia de ubicación

✅ Diferencia entre ruta relativa y ruta absoluta

| Tipo de ruta     | Descripción                                                                 | Ejemplo |
|------------------|-----------------------------------------------------------------------------|---------|
| **Ruta relativa** | Es una ruta que **parte desde la ubicación actual** del programa (proyecto). | `documentos/archivo.txt` |
| **Ruta absoluta** | Es una ruta que **especifica la ubicación completa** del archivo en el sistema operativo. | `C:/Users/mario/Documents/archivo.txt` |

---

## 💡 ¿Sabías que...?

- Puedes usar `Paths.get()` con múltiples argumentos:  
  `Paths.get("carpeta", "subcarpeta", "archivo.txt")`
- `Files.exists(path)` lanza menos excepciones que `File.exists()` (más robusto)
- Con NIO.2 puedes manejar rutas tanto en sistemas Windows como UNIX sin problemas de compatibilidad

---

📘 Recurso adicional para repaso:  
🔗 [NIO.2 (java.nio.file) – Oracle Docs](https://docs.oracle.com/javase/tutorial/essential/io/fileio.html)

---

⬅️ [**Anterior**](../Readme.md) | [**Siguiente**](../Ejemplo-02/Readme.md)➡️  