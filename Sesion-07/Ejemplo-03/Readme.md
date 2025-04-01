🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 07**](../Readme.md) ➡️ / 📝 `Ejemplo 03: Manejo avanzado de archivos`

---

## 🎯 Objetivo

Aprender a usar las funciones avanzadas de la API `java.nio.file` para **copiar, mover, crear carpetas** y **verificar permisos de archivos**. Estas operaciones son esenciales en sistemas automatizados, como aquellos utilizados en entornos de **Industria 4.0** o aplicaciones con dispositivos inteligentes.

---

## 🧠 Escenario aplicado: robots de inspección en una planta 4.0

Imagina una **línea de producción automatizada**, donde **robots de inspección** generan reportes de calidad en archivos `.txt`. Tu sistema debe:

- Mover archivos temporales a carpetas de almacenamiento.
- Crear respaldos de forma organizada.
- Validar permisos de acceso a los archivos.
- Crear nuevas carpetas para clasificar por fecha, turno o tipo de evento.

Este tipo de tareas es común en entornos donde conviven la automatización, la trazabilidad de datos y la supervisión por inteligencia artificial o sistemas autónomos.

---

## 🧪 Código de ejemplo: mover, copiar, crear y validar archivos

```java
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;
import java.io.IOException;
import java.nio.file.StandardCopyOption;
import java.nio.charset.StandardCharsets;

public class GestorDeReportes {
    public static void main(String[] args) {
        try {
            // Crear directorios dentro de este package si no existen
            Path base = Paths.get("src/Ejemplo_03");
            Path dirTemporal = base.resolve("temporal");
            Path dirAlmacenamiento = base.resolve("almacenamiento");
            Path dirRespaldo = base.resolve("respaldo");
            Path dirHistoricos = base.resolve("archivos-historicos");

            Files.createDirectories(dirTemporal);
            Files.createDirectories(dirAlmacenamiento);
            Files.createDirectories(dirRespaldo);
            Files.createDirectories(dirHistoricos);

            // Crear archivo de ejemplo en temporal
            Path archivoTemporal = dirTemporal.resolve("reporte_inspeccion.txt");

            if (!Files.exists(archivoTemporal)) {
                Files.writeString(archivoTemporal, "🔍 Reporte de inspección inicial.\nFecha: 2025-03-31", StandardCharsets.UTF_8);
                System.out.println("📄 Archivo de reporte creado en carpeta temporal.");
            }

            // Mover archivo a almacenamiento
            Path archivoAlmacenado = dirAlmacenamiento.resolve("reporte_inspeccion.txt");
            Files.move(archivoTemporal, archivoAlmacenado, StandardCopyOption.REPLACE_EXISTING);
            System.out.println("📦 Archivo movido a carpeta de almacenamiento.");

            // Copiar archivo a respaldo
            Path archivoRespaldo = dirRespaldo.resolve("reporte_inspeccion.txt");
            Files.copy(archivoAlmacenado, archivoRespaldo, StandardCopyOption.REPLACE_EXISTING);
            System.out.println("🗂️ Copia de respaldo creada.");

            // Verificar permisos del archivo de respaldo
            System.out.println("✅ ¿Se puede leer?: " + Files.isReadable(archivoRespaldo));
            System.out.println("✏️ ¿Se puede escribir?: " + Files.isWritable(archivoRespaldo));

        } catch (IOException e) {
            System.err.println("❌ Error al manejar archivos: " + e.getMessage());
        }
    }
}
```

---

📌 **Importante**:  
Este código no utiliza manejo de errores (`try-catch`) porque el tema de excepciones será abordado en el **Ejemplo 04**. Si los archivos o carpetas no existen, se generará un error al ejecutar.  
Puedes simular correctamente el ejemplo creando previamente las carpetas `temporal`, `almacenamiento`, y el archivo `reporte-inspeccion.txt`.

---

## 🧰 Funciones clave utilizadas

| Método                          | Función                                                                 |
|----------------------------------|--------------------------------------------------------------------------|
| `Files.move()`                  | Mueve un archivo a otra ubicación                                       |
| `Files.copy()`                  | Copia un archivo                                                        |
| `Files.createDirectory()`       | Crea una nueva carpeta                                                  |
| `Files.isReadable() / isWritable()` | Verifica si el archivo tiene permisos de lectura/escritura         |

---

## 💡 ¿Sabías que...?

- Puedes usar `Files.createDirectories()` si deseas crear múltiples carpetas anidadas.
- Estas operaciones son muy comunes en software que trabaja con archivos generados automáticamente por sistemas como **robots**, **sensores**, **drones**, o **IA** que produce reportes en tiempo real.
- `java.nio.file` es portable y compatible con Linux, Windows o macOS, por lo que puedes usar estas operaciones en servidores industriales o entornos embebidos.

---

📘 Recurso adicional para repaso:  
🔗 [Clase Files – Oracle Docs](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/nio/file/Files.html)

---

⬅️ [**Anterior**](../Reto-01/Readme.md) | [**Siguiente**](../Ejemplo-04/Readme.md)➡️  