🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 03**](../Readme.md) ➡️ / 📝 `Ejemplo 02 - Métodos, parámetros y retorno de valores`

---

## 🎯 Objetivo

Comprender cómo se definen y utilizan los **métodos en Java**, diferenciando entre métodos con o sin parámetros, con o sin retorno de valor. También se explora cómo se comportan los datos al ser pasados a métodos (por valor o por referencia), y cómo aplicar **sobrecarga de métodos**.

---

## 📖 Introducción

Los métodos permiten organizar el código en **bloques reutilizables**.  
Un método puede:

- Recibir parámetros para trabajar con datos.
- Devolver un valor al programa principal.
- Ejecutar una acción sin devolver nada.

---

## 1️⃣ Método sin parámetros y sin retorno

Un método simple que solo muestra un mensaje. No recibe datos ni devuelve nada.

```java
public void mostrarBienvenida() {
    System.out.println("👋 Bienvenido al sistema");
}
```

🧪 Implementación: 

```java
mostrarBienvenida(); // Se realiza la llamada al método. 
```

---

## 2️⃣ Método con parámetros y sin retorno

Este método recibe dos valores y **muestra el resultado de una operación**.

```java
public void mostrarSuma(int a, int b) {
    int resultado = a + b;
    System.out.println("➕ La suma es: " + resultado);
}
```

🧪 Implementación:

```java
mostrarSuma(10, 20); // Se establecen dos argumentos.
```

---

## 3️⃣ Método con parámetros y con retorno

Ahora el método **devuelve el resultado** de la suma en lugar de solo mostrarlo.

```java
public int obtenerSuma(int a, int b) {
    return a + b;
}
```

🧪 Implementación:

```java
int suma = obtenerSuma(5, 7);
System.out.println("🧮 Resultado: " + suma);
```

---

## 4️⃣ Paso por valor (tipos primitivos)

Los datos primitivos se pasan **por valor**, es decir, se copia el valor original.

```java
public void duplicar(int numero) {
    numero = numero * 2;
    System.out.println("Dentro del método: " + numero);
}
```

🧪 Implementación:

```java
int x = 10;
duplicar(x);
System.out.println("Fuera del método: " + x);  // x no cambia
```

---

## 5️⃣ Paso por referencia (objetos)

Los objetos se pasan **por referencia**, lo que permite modificar sus atributos.

```java
public class Persona {
    String nombre;

    public Persona(String nombre) {
        this.nombre = nombre;
    }
}
```

```java
public void cambiarNombre(Persona p) {
    p.nombre = "Nuevo nombre";
}
```

🧪 Implementación:

```java
Persona persona = new Persona("Mario");
cambiarNombre(persona);
System.out.println("Nombre actualizado: " + persona.nombre);
```

---

## 6️⃣ Sobrecarga de métodos

Puedes definir **varias versiones** del mismo método con diferentes parámetros.

```java
public void saludar() {
    System.out.println("👋 Hola");
}

public void saludar(String nombre) {
    System.out.println("👋 Hola, " + nombre);
}
```

🧪 Implementación:

```java
saludar();              // Hola
saludar("Mario");       // Hola, Mario
```

---

## 🧠 Resumen rápido

| Tipo de método         | Ejemplo                        |
|------------------------|--------------------------------|
| Sin parámetros/retorno | `mostrarBienvenida()`          |
| Con parámetros          | `mostrarSuma(int, int)`        |
| Con retorno             | `obtenerSuma(int, int)`        |
| Paso por valor          | `duplicar(int)`                |
| Paso por referencia     | `cambiarNombre(Persona)`       |
| Sobrecarga              | `saludar()` / `saludar(String)`|

---

## 💡 ¿Sabías que...?

🔹 En Java, los métodos `void` se usan para **acciones sin retorno**, como imprimir.  
🔹 Puedes usar métodos con retorno para **calcular resultados** y reutilizarlos en otras operaciones.  
🔹 La **sobrecarga** permite tener múltiples versiones de un método con el mismo nombre, siempre que los parámetros sean distintos.  
🔹 Entender el **paso por valor y por referencia** es clave para trabajar con datos en memoria correctamente.

---

⬅️ [**Anterior**](../Readme.md) | [**Siguiente**](../Reto-01/Readme.md)➡️  