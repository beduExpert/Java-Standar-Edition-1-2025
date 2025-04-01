🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 06**](../Readme.md) ➡️ / ⚡ `Reto 01: Registro y análisis de muestras genéticas`

## 🎯 Objetivo 

Practicar el uso de `ArrayList`, `HashSet` y `HashMap` en un contexto profesional relacionado con la biotecnología, para registrar muestras, identificar elementos únicos y asociar datos clave.

---

## 🧬 Escenario

Estás colaborando como desarrollador Java en un laboratorio de **biotecnología molecular**. Tu tarea es ayudar al equipo de bioinformática a organizar el registro de las muestras genéticas que llegan diariamente al laboratorio.

Deben llevar el control de:

1. 📥 El **orden de llegada** de las muestras (pueden repetirse si se replican).
2. 🧬 Las **especies únicas** que han sido procesadas.
3. 🧑‍🔬 El **ID de cada muestra** asociado con el **nombre del investigador** responsable.

---

## 📌 Instrucciones

Crea un programa Java que:

1. Use un `ArrayList<String>` para registrar el orden en que llegaron las muestras.  
   Ejemplo de especies: `"Homo sapiens"`, `"Mus musculus"`, `"Arabidopsis thaliana"`, `"Homo sapiens"`.

2. Use un `HashSet<String>` para obtener una lista de especies **únicas**.

3. Use un `HashMap<String, String>` para asociar el **ID de muestra** con el **nombre del investigador**.  
   Ejemplo: `("M-001", "Dra. López")`, `("M-002", "Dr. Hernández")`.

4. Muestre en consola:
   - La lista completa y ordenada de muestras.
   - Las especies únicas procesadas.
   - La relación de ID de muestra → investigador.
   - Una búsqueda por ID de muestra (`"M-002"` por ejemplo).

---

## 🧠 Consejos para resolver el reto

- Utiliza nombres de variables descriptivos y en español.
- Agrega comentarios para explicar cada bloque de código.
- Usa `System.out.println()` para mostrar resultados de forma clara.

---

## 💻 Estructura sugerida

```java
// Paso 1: ArrayList para registrar todas las especies en orden

// Paso 2: HashSet para filtrar especies únicas

// Paso 3: HashMap para asociar ID de muestra con investigador

// Paso 4: Mostrar resultados
```
---

🏆 Nos vemos en el siguiente reto, ¡mucho éxito!

---

⬅️ [**Anterior**](../Ejemplo-02/Readme.md) | [**Siguiente**](../Ejemplo-03/Readme.md) ➡️