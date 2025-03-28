🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 02**](../Readme.md) ➡️ / 📝 `Ejemplo 02: Operaciones y expresiones`

## 🎯 Objetivo

🔍 Aplicar operadores aritméticos, relacionales, de asignación e incremento usando la regla de precedencia en un ejemplo completo, para entender cómo construir expresiones útiles en Java.

---

## 📌 Contexto del ejemplo

Imagina que estás programando un sistema de facturación para una **cafetería**. Un cliente compró varios productos y se desea calcular el **total de su compra**, verificar si **supera cierto límite para aplicar descuento**, y mostrar el **resultado final** de forma clara.

---

## 🧾 Escenario

El cliente compró lo siguiente:

- ☕ 2 cafés a $45.50 cada uno
- 🧁 1 pastel a $80.00
- 💧 1 botella de agua a $20.00

Hay una **promoción**:  
> Si el total supera los **$150**, se aplica un **10% de descuento**.

---

## 💻 Código en Java

```java
public class FacturaCafeteria {
    public static void main(String[] args) {
        // Precios unitarios
        double precioCafe = 45.50;
        double precioPastel = 80.00;
        double precioAgua = 20.00;

        // Cantidades
        int cantidadCafe = 2;
        int cantidadPastel = 1;
        int cantidadAgua = 1;

        // El cliente decidió agregar otro pastel 🧁
        cantidadPastel++; // Incrementamos en 1

        // Cálculo del total (con prioridad de operadores)
        double total = (precioCafe * cantidadCafe) + (precioPastel * cantidadPastel) + (precioAgua * cantidadAgua);

        // Descuento si el total supera $150
        boolean aplicaDescuento = total > 150;

        // Asignación del descuento (10%)
        double descuento = aplicaDescuento ? total * 0.10 : 0;

        // Cálculo final
        double totalFinal = total - descuento;

        // Salida formateada
        System.out.println("Total de la compra: $" + total);
        System.out.println("¿Aplica descuento? " + aplicaDescuento);
        System.out.println("Descuento aplicado: $" + descuento);
        System.out.println("Total a pagar: $" + totalFinal);
    }
}
```

---

## 🧠 ¿Qué conceptos se aplican aquí?

| Concepto                  | Aplicación en el código                              |
|---------------------------|------------------------------------------------------|
| Aritméticos               | Suma y multiplicación en el cálculo del total        |
| Relacionales              | `total > 150` para saber si aplica descuento         |
| Asignación                | `=`, `+=`, y uso del operador ternario (`? :`)       |
| Incremento (`++`)         | `cantidadPastel++` al agregar otro pastel            |
| Precedencia (PEMDAS)      | Paréntesis usados para agrupar operaciones clave     |

---

## 📌 Regla de precedencia (PEMDAS)

Java sigue esta jerarquía al evaluar expresiones:

1. **Paréntesis** `()`
2. **Exponenciación** (no existe como `**`, pero se puede usar `Math.pow()`)
3. **Multiplicación**, **División**, **Módulo** (`*`, `/`, `%`)
4. **Suma y resta** (`+`, `-`)
5. **Relacionales** (`>`, `<`, `==`, `!=`, etc.)
6. **Lógicos** (`&&`, `||`, `!`)
7. **Asignación** (`=`, `+=`, `-=`, etc.)

💡 Siempre puedes usar paréntesis para aclarar el orden de evaluación.

---

## 💡 ¿Sabías que...?

- Puedes usar `++` o `--`para aumentar disminuir el valor de una variable en uno `Ej: --x, z++`. 
- El operador ternario `? :` es una forma abreviada de usar `if-else` para asignar valores y se puede utilizar de la siguiente manera: 
`(condition) ? expressionTrue :  expressionFalse;`.
- En operaciones largas, es buena práctica **dividir los cálculos en pasos legibles**.
- Aunque no vimos operadores lógicos en este ejemplo, se usan frecuentemente en validaciones más complejas (lo veremos pronto 😉).

---

📘 Recurso recomendado:  
🔗 [Java Operators – W3Schools](https://www.w3schools.com/java/java_operators.asp)

---

⬅️ [**Anterior**](../Reto-01/Readme.md) | [**Siguiente**](../Reto-02/Readme.md)➡️