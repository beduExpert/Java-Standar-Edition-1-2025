🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 03**](../Readme.md) ➡️ / 📝 `Ejemplo 02 - Métodos, parámetros y retorno de valores`

---

## 🎯 Objetivo

Comprender cómo definir y usar métodos en Java: con o sin parámetros, con o sin retorno, cómo se comportan al pasar valores por valor o referencia, y cómo aplicar la sobrecarga de métodos.

---

## 📌 Escenario profesional

Eres parte del equipo de desarrollo de una aplicación de ventas. Necesitas programar métodos que realicen tareas como calcular totales, imprimir mensajes al usuario, y manejar descuentos, de forma **reutilizable y flexible.**

---

## 1️⃣ Estructura básica de un método

En esta sección veremos cómo se declara un método que recibe parámetros y devuelve un valor.

```java
// Clase con un método que calcula el total con IVA
public class Calculator {

    // Método que recibe un subtotal y devuelve el total con IVA
    public double calcularTotalConIVA(double subtotal) {
        return subtotal * 1.16;  // Se asume un IVA del 16%
    }
}
```

---

## 2️⃣ Uso de métodos con retorno de valor

Aquí usamos el método anterior desde el `main` y mostramos el resultado en consola.

```java
public class Main {
    public static void main(String[] args) {
        Calculator calc = new Calculator();  // Creación del objeto

        double total = calc.calcularTotalConIVA(100.0);  // Llamada al método

        System.out.println("💵 Total con IVA: $" + total);  // Mostrar resultado
    }
}
```

---

## 3️⃣ Método sin retorno y sin parámetros

Este método realiza una acción sin devolver valor, muy útil para mostrar mensajes o realizar tareas de notificación.

```java
public void mostrarBienvenida() {
    System.out.println("👋 Bienvenido a la App de Ventas");
}
```

Y su uso sería:

```java
calc.mostrarBienvenida();  // Llamada desde el main
```

---

## 4️⃣ Paso de parámetros: por valor vs por referencia

En Java, los tipos primitivos se pasan por valor, y los objetos por referencia.

```java
public void duplicarNumero(int numero) {
    numero = numero * 2;
    System.out.println("🔁 Número dentro del método: " + numero);
}
```

```java
int valor = 10;
calc.duplicarNumero(valor);  // Paso por valor
System.out.println("🔎 Número original: " + valor);  // No cambia

```
Ahora con objetos:

```java
public void cambiarNombre(Cliente c) {
    c.nombre = "Nuevo nombre";
}
```

```java
Cliente cliente1 = new Cliente("Mario");
calc.cambiarNombre(cliente1);  // Paso por referencia
System.out.println("🧾 Nombre del cliente: " + cliente1.nombre);  // Sí cambia

```
---

## 5️⃣ Sobrecarga de métodos

Cuando necesitas múltiples versiones del mismo método con diferentes parámetros.

```java
public class Descuento {

    // Descuento solo con porcentaje
    public double aplicarDescuento(double precio, double porcentaje) {
        return precio - (precio * porcentaje);
    }

    // Descuento con porcentaje + monto fijo
    public double aplicarDescuento(double precio, double porcentaje, double adicional) {
        return (precio - (precio * porcentaje)) - adicional;
    }
}
```
---

## 🔍 Revisión rápida

| Concepto            | Aplicación en el ejemplo         |
|---------------------|----------------------------------|
| Método con retorno  |	`calcularTotalConIVA()`          |
| Método sin retorno  |	`mostrarBienvenida()`            |
| Paso por valor	  | `duplicarNumero(int)`            |
| Paso por referencia |	`cambiarNombre(Cliente)`         |
| Sobrecarga	      | `aplicarDescuento(...)`          |   
---

## 💡 ¿Sabías que...?

🔹 En Java, aunque los tipos primitivos se pasan por **valor**, los objetos se pasan por **referencia**, lo que permite modificarlos directamente desde los métodos.

🔹 Puedes crear múltiples versiones de un mismo método usando la **sobrecarga**, siempre y cuando cambien los **parámetros** (en cantidad o tipo). Esto hace que tus programas sean más flexibles y fáciles de mantener.

🔹 Los métodos que no devuelven valores (`void`) son ideales para **mostrar mensajes**, **registrar logs** o **enviar acciones**, mientras que los métodos con retorno son más útiles para **realizar cálculos** o **procesar datos**.

🔹 Usar bien los métodos te permite **modularizar** tu código, lo cual es clave en proyectos reales donde trabajan varios desarrolladores.

---

⬅️ [**Anterior**](../Readme.md) | [**Siguiente**](../Reto-02/Readme.md)➡️


