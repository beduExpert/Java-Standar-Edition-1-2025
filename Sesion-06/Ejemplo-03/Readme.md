🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 06**](../Readme.md) ➡️ / 📝 `Ejemplo 03: Ordenamiento con Comparator y Comparable`

## 🎯 Objetivo

Aplicar las interfaces `Comparable` y `Comparator` para ordenar una colección de objetos en Java, usando criterios como nombre y prioridad en un entorno profesional.

---

## 🏭 Ejemplo

Imagina que eres ingeniero industrial y estás desarrollando una aplicación para gestionar **órdenes de producción** en planta.  
Cada orden contiene:

- Un código de orden
- El nombre del producto
- La prioridad de la orden (donde 1 = alta, 2 = media, 3 = baja)

Necesitas:

- Ordenar alfabéticamente por nombre del producto (orden natural).
- Ordenar por prioridad, de forma personalizada.

## 🧾 Escenario

La clase `OrdenProduccion` implementa `Comparable` para permitir ordenamiento por **nombre del producto**.  

Además, se aplica un `Comparator` anónimo para ordenar por **prioridad ascendente**.

---

## 💻 Código en Java

```java
import java.util.*;

// Clase que representa una orden de producción
class OrdenProduccion implements Comparable<OrdenProduccion> {
    String codigo;
    String producto;
    int prioridad;

    public OrdenProduccion(String codigo, String producto, int prioridad) {
        this.codigo = codigo;
        this.producto = producto;
        this.prioridad = prioridad;
    }

    // Orden natural: por nombre del producto (alfabético)
    @Override
    public int compareTo(OrdenProduccion otra) {
        return this.producto.compareTo(otra.producto);
    }

    @Override
    public String toString() {
        return "Código: " + codigo + " | Producto: " + producto + " | Prioridad: " + prioridad;
    }
}

public class OrdenamientoProduccion {
    public static void main(String[] args) {
        // Lista de órdenes
        List<OrdenProduccion> ordenes = new ArrayList<>();
        ordenes.add(new OrdenProduccion("OP-003", "Tornillo M6", 2));
        ordenes.add(new OrdenProduccion("OP-001", "Tuerca M8", 1));
        ordenes.add(new OrdenProduccion("OP-002", "Arandela 10mm", 3));

        // Orden natural: por producto (Comparable)
        Collections.sort(ordenes);
        System.out.println("📦 Órdenes ordenadas por producto (orden natural):");
        for (OrdenProduccion op : ordenes) {
            System.out.println(op);
        }

        // Orden personalizado: por prioridad (Comparator)
        ordenes.sort(new Comparator<OrdenProduccion>() {
            @Override
            public int compare(OrdenProduccion a, OrdenProduccion b) {
                return Integer.compare(a.prioridad, b.prioridad);
            }
        });

        System.out.println("\n🔥 Órdenes ordenadas por prioridad (1 = alta):");
        for (OrdenProduccion op : ordenes) {
            System.out.println(op);
        }
    }
}
```

---

## 🧠 ¿Qué conceptos se aplican aquí?

| Técnica       | Aplicación práctica                          |
|---------------|-----------------------------------------------|
| `Comparable`  | Ordenar por nombre de producto (natural)      |
| `Comparator`  | Ordenar por prioridad (externo/personalizado) |

---

## 💡 ¿Sabías que...?

- Puedes usar `Collections.sort()` directamente si tu clase implementa `Comparable`.
- `Comparator` te permite tener múltiples criterios de ordenamiento sin modificar la clase original.
- También puedes usar expresiones lambda para simplificar comparadores.

---

⬅️ [**Anterior**](../Reto-01/Readme.md) | [**Siguiente**](../Ejemplo-04/Readme.md) ➡️