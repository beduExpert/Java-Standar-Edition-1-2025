🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 06**](../Readme.md) ➡️ / 📝 `Ejemplo 02: Diferencias entre ArrayList, HashSet y HashMap`

## 🎯 Objetivo

Comprender las diferencias prácticas entre `ArrayList`, `HashSet` y `HashMap` al manipular datos en un entorno de control de calidad o inventarios industriales.

---

## 🏭 Ejemplo 

Imagina que trabajas como **ingeniero industrial** en una planta de manufactura y estás desarrollando un sistema que te ayude a:

- Registrar el orden de llegada de reportes de materiales defectuosos.
- Identificar los tipos únicos de defectos que han ocurrido.
- Relacionar cada ID de lote con su causa principal de rechazo.

Este ejemplo te permitirá ver las **diferencias clave entre estas tres estructuras** y cuándo usar cada una de manera efectiva.


## 🧾 Escenario

Necesitamos:

- Guardar los reportes en el **orden en que llegan**, incluso si están repetidos.
- Registrar solo los **tipos únicos de defecto**.
- Asociar el **ID del lote con la causa del defecto**.

---

## 💻 Código en Java

```java
import java.util.*;

public class ControlDefectos {
    public static void main(String[] args) {

        // 📝 ArrayList: registrar reportes de defectos (puede haber repetidos)
        ArrayList<String> reportes = new ArrayList<>();
        reportes.add("Falla en rosca");
        reportes.add("Golpe en superficie");
        reportes.add("Falla en rosca"); // Repetido
        reportes.add("Pintura irregular");

        System.out.println("🗂️ Reportes de defectos (ordenados, con duplicados):");
        for (int i = 0; i < reportes.size(); i++) {
            System.out.println(i + 1 + ". " + reportes.get(i));
        }

        // ✅ HashSet: registrar defectos únicos
        HashSet<String> tiposDefecto = new HashSet<>(reportes); // Elimina duplicados

        System.out.println("\n✅ Tipos únicos de defecto encontrados:");
        for (String defecto : tiposDefecto) {
            System.out.println("- " + defecto);
        }

        // 🗃️ HashMap: asociar ID de lote con la causa del rechazo
        HashMap<String, String> lotesRechazados = new HashMap<>();
        lotesRechazados.put("L-001", "Falla en rosca");
        lotesRechazados.put("L-002", "Golpe en superficie");
        lotesRechazados.put("L-003", "Pintura irregular");

        System.out.println("\n📇 Lotes rechazados (ID → Causa):");
        for (Map.Entry<String, String> entry : lotesRechazados.entrySet()) {
            System.out.println(entry.getKey() + " → " + entry.getValue());
        }

        // 🔍 Buscar causa de rechazo por ID
        String idBuscar = "L-002";
        System.out.println("\n🔍 Causa del rechazo para " + idBuscar + ": " + lotesRechazados.get(idBuscar));
    }
}
```

---

## 🧠 ¿Qué conceptos se aplican aquí?

| Estructura  | Permite duplicados | Mantiene orden | Clave-valor | Ejemplo aplicado                              |
|-------------|--------------------|----------------|-------------|----------------------------------------------|
| `ArrayList` | ✅ Sí              | ✅ Sí         | ❌ No       | Registro cronológico de defectos              |
| `HashSet`   | ❌ No              | ❌ No         | ❌ No       | Registro de tipos únicos de defecto           |
| `HashMap`   | ✅ (en valores)    | ❌ No         | ✅ Sí       | Relación entre ID de lote y causa del defecto |

---

## 💡 ¿Sabías que...?

- `ArrayList` es útil cuando necesitas mantener el orden y tener acceso rápido por índice.
- `HashSet` es ideal cuando quieres eliminar duplicados automáticamente.
- `HashMap` permite búsquedas rápidas por clave, ideal para manejar relaciones uno a uno (como ID → dato).
- Puedes convertir fácilmente un `ArrayList` en un `HashSet` si quieres eliminar duplicados.

---

⬅️ [**Anterior**](../Ejemplo-01/Readme.md) | [**Siguiente**](../Reto-01/Readme.md) ➡️