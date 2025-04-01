🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 08**](../Readme.md) ➡️ / 📝 `Ejemplo 01: Refactorización y Code Smells`

---

## 🎯 Objetivo

🔍 Aplicar buenas prácticas de refactorización identificando y corrigiendo code smells comunes en un caso profesional sencillo, mejorando la legibilidad y mantenimiento del código en Java.

---

## 👩‍💻 Contexto del ejemplo

Imagina que trabajas como Java developer en una empresa fintech. Te asignaron el mantenimiento de una pequeña función que calcula comisiones por ventas de productos financieros.

Al revisar el código, detectas señales de alerta: funciones muy largas, nombres poco claros y código duplicado 😩. 

Tu tarea es aplicar refactorización para mejorar su estructura y comprensión 🤓💡, pero, sin alterar su comportamiento 🤔.

---

## 🧠 Un repaso antes...

Sabemos que:

- **Refactorizar** es mejorar el diseño interno del código sin cambiar su funcionalidad.  
- Un **code smell** es una señal de que algo podría estar mal estructurado. No rompe el código, pero sí puede hacerlo difícil de mantener.
- Algunos **ejemplos comunes** de code smells:
  - Código duplicado
  - Funciones largas
  - Nombres poco descriptivos
  - Clases o funciones con muchas responsabilidades
  - Código comentado que ya no se usa

💡 Refactorizar es como limpiar tu espacio de trabajo: te hace más productivo, evita errores y facilita el trabajo en equipo.

---

## 💼 Ejemplo 

Veamos este caso realista. Este código se encuentra en un archivo que calcula comisiones de agentes de ventas para un producto financiero. El código original presenta varios problemas:

### 💻 Código antes de refactorizar

```java
public class ComisionVentas {

    public static void main(String[] args) {
        String nombre = "Carlos";
        double ventas = 30000;
        double comision;

        if (ventas >= 20000 && ventas <= 40000) {
            comision = ventas * 0.10;
            System.out.println("Comisión de " + nombre + ": $" + comision);
        } else if (ventas > 40000) {
            comision = ventas * 0.12;
            System.out.println("Comisión de " + nombre + ": $" + comision);
        } else {
            comision = ventas * 0.05;
            System.out.println("Comisión de " + nombre + ": $" + comision);
        }

        if (ventas > 25000 && ventas < 30000) {
            System.out.println("¡Carlos está cerca del siguiente nivel!");
        }
    }
}
```

### 🚨 Problemas detectados

| Code Smell                 | Explicación                                                                  |
|---------------------------|-------------------------------------------------------------------------------|
| Código duplicado          | La línea `System.out.println(...)` se repite en cada condición.               |
| Nombres poco descriptivos | `ventas` es aceptable, pero `comision` y `nombre` pueden ser más específicos.|
| Código comentado          | Hay una línea que ya no se usa.                                              |
| Lógica mezclada           | La lógica de cálculo y de impresión están en el mismo lugar.                |

---

### ✅ Código después de refactorizar

```java
public class ComisionVentasRefactor {

    public static void main(String[] args) {
        String nombreAgente = "Carlos";
        double montoVentas = 30000;

        double comisionCalculada = calcularComision(montoVentas);
        mostrarComision(nombreAgente, comisionCalculada);

        if (estaCercaDelSiguienteNivel(montoVentas)) {
            System.out.println("¡" + nombreAgente + " está cerca del siguiente nivel!");
        }
    }

    // Esta función se encarga únicamente del cálculo de la comisión
    public static double calcularComision(double ventas) {
        if (ventas >= 20000 && ventas <= 40000) {
            return ventas * 0.10;
        } else if (ventas > 40000) {
            return ventas * 0.12;
        } else {
            return ventas * 0.05;
        }
    }

    // Esta función muestra la comisión
    public static void mostrarComision(String nombre, double comision) {
        System.out.println("Comisión de " + nombre + ": $" + comision);
    }

    // Verifica si el vendedor está cerca del siguiente nivel
    public static boolean estaCercaDelSiguienteNivel(double ventas) {
        return ventas > 25000 && ventas < 30000;
    }
}
```

---

## 🔄 ¿Qué aprendimos?

✅ Separar la lógica en funciones mejora la legibilidad y mantenimiento  
✅ Evitar código duplicado facilita cambios futuros  
✅ Usar nombres descriptivos hace que otros (o tú mismo) entiendan el propósito del código  
✅ Eliminar código muerto ayuda a tener un proyecto más limpio y profesional  

---

## 💡 ¿Sabías que...?

- Existen herramientas como [SonarLint](https://www.sonarlint.org/) y [PMD](https://pmd.github.io/) que detectan code smells automáticamente en tu editor o IDE.
- En muchas entrevistas técnicas, se valora más un código limpio y bien estructurado que uno que simplemente funcione.
- Refactorizar es una práctica continua: incluso grandes empresas como Google, Netflix o Amazon refactorizan código constantemente.

---

📘 Recurso recomendado:  
🔗 [Refactoring Guru - Code Smells (en español)](https://refactoring.guru/es/smells)

---


⬅️ [**Anterior**](../Readme.md) | [**Siguiente**](../Ejemplo-02/Readme.md) ➡️