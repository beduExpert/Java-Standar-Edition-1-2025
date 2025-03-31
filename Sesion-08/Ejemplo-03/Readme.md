
🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 08**](../Readme.md) ➡️ / 📖 `Ejemplo 03: Técnicas para mejorar el rendimiento`

---

## 🎯 Objetivo

🚀 Aplicar buenas prácticas para optimizar el rendimiento de programas en Java mediante el uso eficiente de estructuras de datos, simplificación de lógica y correcta gestión de memoria.

---

## 🧠 No olvidemos

En el desarrollo profesional, el rendimiento importa tanto como la funcionalidad. No se trata de hacer “trucos mágicos” 🔮 sino de tomar decisiones inteligentes 💡 desde el inicio.

### ⚙️ Claves para mejorar el rendimiento

| Técnica | Qué implica | Ejemplo práctico |
|--------|-------------|------------------|
| ✅ Estructuras eficientes | Usar `HashMap`, `HashSet`, `ArrayList`, según la situación | Buscar usuarios por ID → `HashMap` |
| 🧼 Lógica limpia | Dividir métodos, eliminar bucles innecesarios | Salir temprano de un `for` cuando se cumple la condición |
| 💾 Uso de memoria | Reutilizar objetos, cerrar recursos | Cerrar un archivo con `try-with-resources` |

---

## 💼 Ejemplo 

Eres parte del equipo de desarrollo que da soporte al área de sostenibilidad en una empresa manufacturera. Como **Sustainability Manager**, tu trabajo implica analizar datos de emisiones de CO₂ generadas por distintos procesos de la planta, y determinar si se repiten registros, si hay valores duplicados o inconsistentes, o si algún proceso excede el límite permitido.

Tu herramienta se vuelve lenta al procesar los datos diarios de cada línea de producción. Necesitamos optimizar el sistema.

### 💻 Código inicial poco eficiente

```java
import java.util.ArrayList;
import java.util.List;

public class RegistroEmisiones {
    public static void main(String[] args) {
        List<Double> emisiones = new ArrayList<>();
        emisiones.add(123.5);
        emisiones.add(200.0);
        emisiones.add(123.5); // Duplicado
        emisiones.add(300.0);
        emisiones.add(200.0); // Duplicado

        for (int i = 0; i < emisiones.size(); i++) {
            for (int j = i + 1; j < emisiones.size(); j++) {
                if (emisiones.get(i).equals(emisiones.get(j))) {
                    System.out.println("⚠️ Registro duplicado de emisión: " + emisiones.get(i));
                }
            }
        }
    }
}
```

---

### 🚨 Problemas detectados

- Uso de `ArrayList` para verificar duplicados → complejo y lento.
- Búsquedas O(n²) → **muy costoso** cuando se manejan miles de registros.
- Duplicación de lógica → poco mantenible.

---

### ✅ Código optimizado usando `HashSet`

```java
import java.util.HashSet;
import java.util.Set;

public class RegistroEmisionesOptimizado {
    public static void main(String[] args) {
        // Datos simulados de emisiones de CO₂ por línea de producción (kg)
        double[] emisiones = {123.5, 200.0, 123.5, 300.0, 200.0};

        // HashSet evita duplicados y permite búsqueda rápida
        Set<Double> emisionesRegistradas = new HashSet<>();

        for (double valor : emisiones) {
            if (!emisionesRegistradas.add(valor)) {
                System.out.println("⚠️ Duplicado detectado: " + valor + " kg de CO₂");
            }
        }
    }
}
```


### 💡 ¿Qué hicimos mejor?

- Usamos `HashSet`, que no permite valores duplicados.
- Eliminamos el segundo bucle anidado.
- Ahora el sistema puede escalar fácilmente a **miles de líneas de emisión por día** sin colapsar.

---

### 🌱 Y en la vida real...

Como **Sustainability Manager**, tu objetivo es reducir huella de carbono y asegurar calidad de los datos. Tener herramientas optimizadas te permite:
- Detectar inconsistencias rápidamente
- Generar reportes de forma más fluida
- Cumplir con auditorías y certificaciones ambientales sin errores

---

## 🔄 ¿Qué aprendimos?

✅ Usar la estructura adecuada puede mejorar radicalmente el rendimiento  
✅ Menos líneas no significa mejor código: lo importante es que sea **simple y claro**  
✅ Una pequeña decisión (como cambiar un tipo de colección) puede **ahorrar miles de ciclos de CPU**

---

## 💡 ¿Sabías que...?

- El uso incorrecto de estructuras de datos es una de las causas más comunes de cuellos de botella en producción.

- Herramientas como [VisualVM](https://visualvm.github.io/) te permiten ver el consumo de memoria y CPU de tus programas Java.

---

📘 Recurso extra:  
🔗 https://www.w3schools.com/java/java_hashset.asp

---

⬅️ [**Anterior**](../Reto-01/Readme.md) | [**Siguiente**](../Ejemplo-04/Readme.md)➡️
