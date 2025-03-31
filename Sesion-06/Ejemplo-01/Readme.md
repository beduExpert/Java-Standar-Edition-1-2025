🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 06**](../Readme.md) ➡️ / 📝 `Ejemplo 01: Introducción a las colecciones`

## 🎯 Objetivo

Aplicar los conceptos de `List`, `Set` y `Map` en un escenario práctico de control de materiales, identificando cuándo es útil cada tipo de colección en entornos reales de ingeniería industrial.

---

## 🏭 Ejemplo:  Gestión de materiales en línea de producción

Imagina que trabajas como **industrial engineer** en una planta de manufactura, y necesitas desarrollar una herramienta en Java que te ayude a:

- Registrar el **orden de llegada** de materiales.
- Validar que no haya **lotes duplicados**.
- Asociar **códigos de pieza con su descripción**.

Para esto, usaremos colecciones como `List`, `Set` y `Map`, cada una resolviendo un problema distinto de manera eficiente.


## 🧾 Escenario

El sistema debe cumplir con los siguientes puntos:

- Guardar los nombres de materiales conforme van llegando.
- Asegurar que cada lote registrado sea **único**.
- Permitir búsquedas rápidas de piezas mediante su **código**.

---

## 💻 Código en Java

```java
import java.util.*;

public class GestionMateriales {
    public static void main(String[] args) {

        // 📦 List: Registrar orden de llegada de materiales
        List<String> materialesRecibidos = new ArrayList<>();
        materialesRecibidos.add("Tornillo M6");
        materialesRecibidos.add("Arandela 8mm");
        materialesRecibidos.add("Tornillo M6"); // Llega repetido
        materialesRecibidos.add("Tuerca M6");

        System.out.println("📋 Orden de llegada de materiales:");
        for (String material : materialesRecibidos) {
            System.out.println("- " + material);
        }

        // 🧪 Set: Validar lotes únicos (sin duplicados)
        Set<String> lotesUnicos = new HashSet<>();
        lotesUnicos.add("Lote-001");
        lotesUnicos.add("Lote-002");
        lotesUnicos.add("Lote-001"); // Duplicado que será ignorado

        System.out.println("\n✅ Lotes registrados (sin duplicados):");
        for (String lote : lotesUnicos) {
            System.out.println("- " + lote);
        }

        // 🗃️ Map: Código de pieza asociado a descripción
        Map<String, String> catalogoPiezas = new HashMap<>();
        catalogoPiezas.put("PZ-1001", "Tornillo M6 x 20mm");
        catalogoPiezas.put("PZ-1002", "Tuerca M6");
        catalogoPiezas.put("PZ-1003", "Arandela 8mm");

        System.out.println("\n📇 Catálogo de piezas (Código -> Descripción):");
        for (Map.Entry<String, String> entrada : catalogoPiezas.entrySet()) {
            System.out.println(entrada.getKey() + " → " + entrada.getValue());
        }

        // 🔎 Buscar descripción a partir del código
        String codigoBuscado = "PZ-1002";
        System.out.println("\n🔍 Descripción de la pieza " + codigoBuscado + ": " + catalogoPiezas.get(codigoBuscado));
    }
}
```

---

## 🧩 ¿Qué es `import java.util.*;`?

En Java, la instrucción `import` le dice al compilador qué clases o paquetes quieres **usar en tu programa**.

El paquete `java.util` contiene muchas clases **útiles para trabajar con estructuras de datos**, como:

- `ArrayList` → Listas dinámicas.
- `HashSet` → Conjuntos sin duplicados.
- `HashMap` → Asociaciones clave-valor.

También incluye otras herramientas como `Date`, `Collections`, `Scanner`, etc.

Cuando escribes:

```java
import java.util.*;
```

Estás diciendo:

👉 *“Quiero importar todas las clases del paquete java.util.”*

Esto te permite usarlas directamente, sin tener que escribir la ruta completa cada vez 🤓.

---

## 🤔 y aqui no necesito `main`?

✅ Sí, sí necesitas el método `main`, ¡y de hecho ya está incluido en el código!

En Java, el punto de entrada para que un programa se ejecute es este bloque:

```java
public static void main(String[] args) {
    // Aquí va el código que se ejecuta
}
```
**¿Recuerdas qué hace cada parte?**

- `public`: permite que el método sea accesible desde fuera de la clase (el sistema lo necesita así).
- `static`: significa que no necesitas crear una instancia (objeto) de la clase para ejecutar este método.
- `void`: indica que el método no devuelve ningún valor.
- `main`: es el nombre obligatorio para que Java lo reconozca como punto de inicio.
- `String[] args`: es un parámetro que permite recibir argumentos desde la línea de comandos (aunque no lo usamos aquí, es obligatorio ponerlo).

🔍En resumen: **sin `main`, el programa no corre**, a menos que estés trabajando con pruebas unitarias (`JUnit`) o frameworks especiales.

Y como puedes ver en tu código:

```java
public class GestionMateriales {
    public static void main(String[] args) {
        // tu código aquí...
    }
}
```
---



⬅️ [**Anterior**](../Prework/Readme.md) | [**Siguiente**](../Ejemplo-02/Readme.md) ➡️