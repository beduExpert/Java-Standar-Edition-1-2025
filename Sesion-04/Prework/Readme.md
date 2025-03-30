🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 `Prework sesión 04`

<div align="center">
    <img src="../Imagenes/S00.jpg" alt="Bedu | Haz + con tu talento | JAVA STANDARD EDITION I">
</div>

##### **PREWORK**
#### **🟧 Sesión 04**
#### **Elementos de una clase**


##### 🔶 **Introducción**  

¡Felicidades! Has llegado a una de las partes más emocionantes de tu camino en Java: el diseño y desarrollo de clases. 🏗️

En esta sesión, descubrirás cómo estructurar tus clases de manera eficiente, aplicando buenas prácticas que harán tu código más limpio, mantenible y profesional. Aprenderás sobre constructores, métodos especiales como `equals()`, `hashCode()` y `toString()`, y conocerás herramientas modernas como `record` y `Objects.equals()`. Además, reforzarás los principios de encapsulación para escribir código seguro y bien organizado.

No tengas dudas de que este prework te dará una base sólida para que llegues con confianza y listo para programar. 

¡Vamos a darle! 🚀✨

---

#### 🎯 Objetivo  

- Comprender la importancia de los constructores y cómo se utilizan para inicializar objetos correctamente.
- Aprender el uso y la implementación de los métodos especiales `equals()`, `hashCode()` y `toString()` para mejorar la funcionalidad de las clases.
- Explorar el uso de `record` y `Objects.equals()` como herramientas modernas para optimizar la creación y comparación de objetos.
- Aplicar los principios de encapsulación y buenas prácticas en el diseño de clases para escribir código más seguro y mantenible.

---

#### 📋 Instrucciones  

Este Prework está diseñado para conocer el contenido que se practicará durante la sesión en vivo. **Por favor no lo omitas.**

Toma notas de lo que consideres relevante y guarda tus preguntas o dudas para resolverlas en la sesión.

Antes de arrancar, verifica que tu entorno de desarrollo esté listo. Es fundamental que tengas instalado IntelliJ IDEA Community Edition y el JDK (Java Development Kit) para trabajar sin interrupciones.

Si te surge alguna dificultad con la instalación o cualquier duda, no dudes en pedir ayuda a tu experto/a. ¡Estamos aquí para asegurarnos de que todo fluya sin problemas! 🚀

---

**Bienvenido/a**  

Bienvenid@ al cuarto Prework del módulo. A continuación, te presentamos el tiempo estimado de lectura por tema, para que puedas revisar todos los recursos al máximo: 

| **📖 Temario**                                                              | **🕰️ Tiempo sugerido** |
|-----------------------------------------------------------------------------|----------------------|
| Tema 01. Constructores e inicialización de objetos                          | 10 min               |
| Tema 02. Métodos `equals()`, `hashCode()` y `toString()`                    | 5 min                |
| Tema 03. Uso de `record` y `Objects.equals()`                               | 5 min                |
| Tema 04. Principios de encapsulación e inmutabilidad de clases             | 5 min                |

**¡Comencemos! 🏁**

---
 
#### 📚 Tema 01. Constructores e inicialización de objetos   
##### ⏳ 10 minutos de lectura  

En Java, cuando creas un objeto, necesitas asegurarte de que se inicialice correctamente. Para eso, usamos *constructores*, que son métodos especiales define cómo se crean e inicializan los objetos, asegurando que cada uno tenga los valores adecuados desde el inicio.  

💡 Imagina que un constructor es como la receta de una pizza. 🍕  
Cuando pides una pizza, el chef sigue ciertos pasos para prepararla:  
1. Elige la base (🍞 masa) → *Esto sería la estructura básica del objeto.*
2. Agrega ingredientes (🧀 🍅 salsa, queso, toppings) → *Representa los atributos del objeto.*
3. Hornea la pizza 🔥→ *Es el proceso de inicialización del objeto.*

**Tipos de constructores y su implementación**  

Los constructores pueden variar según cómo inicialicen los objetos. Los más comunes son:

📌 **Constructor por defecto**

| **Categoría**        | **Descripción**                                                                                                                                          |
|----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|
| **¿Qué es?**         | Es un constructor que no recibe parámetros y generalmente se usa para asignar valores predeterminados a los atributos de un objeto.                    |
| **¿Para qué sirve?** | - Permite crear objetos sin necesidad de especificar valores iniciales. <br> - Garantiza que un objeto tenga valores válidos desde el inicio. <br> - Es útil cuando quieres que todos los objetos de una clase tengan un estado inicial definido. |
| **Ejemplo**          | Imagina que una pizzería tiene un tipo de pizza estándar que se vende más que todas. En este caso, un constructor por defecto puede asignar esos valores sin necesidad de especificarlos manualmente. |

💻 Ejemplo en código

```java
class Pizza {
    String tamaño;
    String tipoMasa;

    // Constructor por defecto
    public Pizza() {
        this.tamaño = "Mediana";
        this.tipoMasa = "Tradicional";
    }

    void mostrarInfo() {
        System.out.println("Tamaño: " + tamaño + ", Masa: " + tipoMasa);
    }
}

public class Main {
    public static void main(String[] args) {
        Pizza pizza1 = new Pizza(); // Se usa el constructor por defecto
        pizza1.mostrarInfo();  // Salida: Tamaño: Mediana, Masa: Tradicional
    }
}
```
**✅ Beneficio**: No necesitas ingresar valores cada vez que creas un objeto. Útil cuando hay valores estándar.  

**📌 Constructor con parámetros**  

| **Categoría**        | **Descripción**                                                                                                                                      |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|
| **¿Qué es?**         | Es un constructor que recibe valores como argumentos, permitiendo personalizar la creación del objeto.                                              |
| **¿Para qué sirve?** | - Te da flexibilidad al crear objetos con datos específicos. <br> - Evita modificar valores manualmente después de crear el objeto. <br> - Facilita la personalización de los atributos del objeto desde el principio. |
| **Ejemplo**          | Siguiendo el ejemplo de la pizzería, ahora los clientes pueden elegir el tamaño y tipo de masa de su pizza.                                        |

💻 Ejemplo en código  

```java
class Pizza {
    String tamaño;
    String tipoMasa;

    // Constructor con parámetros
    public Pizza(String tamaño, String tipoMasa) {
        this.tamaño = tamaño;
        this.tipoMasa = tipoMasa;
    }

    void mostrarInfo() {
        System.out.println("Tamaño: " + tamaño + ", Masa: " + tipoMasa);
    }
}

public class Main {
    public static void main(String[] args) {
        Pizza pizza2 = new Pizza("Grande", "Delgada"); // Personalizamos la pizza
        pizza2.mostrarInfo();  // Salida: Tamaño: Grande, Masa: Delgada
    }
}
```

**✅ Beneficio**: Permite inicializar los objetos con valores específicos desde el inicio sin tener que modificarlos después.  

**📌 Constructor de copia**  

| **Categoría**        | **Descripción**                                                                                                                                     |
|----------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| **¿Qué es?**         | Es un constructor que recibe otro objeto de la misma clase y copia sus valores. Sirve para duplicar objetos fácilmente.                           |
| **¿Para qué sirve?** | - Permite clonar un objeto sin necesidad de volver a asignar valores. <br> - Es útil cuando necesitas una copia de un objeto sin afectar el original. <br> - Facilita la manipulación de objetos en memoria sin alterar los datos originales. |
| **Ejemplo**          | Siguiendo con nuestra pizzería, imagina que un cliente quiere pedir la misma pizza que otra persona. En lugar de ingresar los datos de nuevo, simplemente copiamos la pizza ya existente. |

💻 Ejemplo en código  

```java
class Pizza {
    String tamaño;
    String tipoMasa;

    // Constructor con parámetros
    public Pizza(String tamaño, String tipoMasa) {
        this.tamaño = tamaño;
        this.tipoMasa = tipoMasa;
    }

    // Constructor de copia
    public Pizza(Pizza otraPizza) {
        this.tamaño = otraPizza.tamaño;
        this.tipoMasa = otraPizza.tipoMasa;
    }

    void mostrarInfo() {
        System.out.println("Tamaño: " + tamaño + ", Masa: " + tipoMasa);
    }
}

public class Main {
    public static void main(String[] args) {
        Pizza pizzaOriginal = new Pizza("Familiar", "Pan grueso");
        Pizza pizzaCopia = new Pizza(pizzaOriginal);  // Se copia la pizza original

        pizzaOriginal.mostrarInfo(); // Salida: Tamaño: Familiar, Masa: Pan grueso
        pizzaCopia.mostrarInfo(); // Salida: Tamaño: Familiar, Masa: Pan grueso
    }
}
```
**✅ Beneficio**: Evita la necesidad de escribir valores nuevamente y permite trabajar con copias de objetos sin afectar el original.  

**✨ ¿Qué hace especial a un constructor?**  
- Tiene el mismo nombre que la clase.
- No tiene un tipo de retorno (ni siquiera `void`).
- Se ejecuta automáticamente cuando creas un objeto.

**Sobrecarga de constructores**  

A veces, necesitas distintas formas de crear un objeto según la información que tengas. Ahí entra la *sobrecarga de constructores*, que permite tener varios constructores con distintos parámetros dentro de la misma clase.  

Ejemplo  
- Un usuario puede registrarse con solo su nombre y correo.  
- Otro usuario puede incluir teléfono y dirección.  
- Un tercero puede agregar una imagen de perfil.  

Cada uno de estos casos puede representarse con un constructor diferente, dependiendo de los datos disponibles.  

Visualízalo así:
<table style="border-collapse: collapse;">
  <tr>
    <td style="border: 1px solid white; padding: 10px; vertical-align: top;">
      <img src="../Imagenes/S04_Fig01.png" alt="celular" width="60">
    </td>
    <td style="border: 1px solid white; padding: 10px;">
      Imagina que compras un celular. Puedes elegir solo el modelo básico, o agregar accesorios como audífonos y una funda.  
      Aunque todos son celulares, el paquete cambia según lo que selecciones.
    </td>
  </tr>
</table>

**Inicialización de objetos con valores por defecto**  

En algunos casos, no queremos que un objeto tenga valores vacíos. Para evitar esto, podemos asignar *valores por defecto* dentro del constructor.  

Ejemplo

<table style="border-collapse: collapse;">
  <tr>
    <td style="border: 1px solid white; padding: 10px;">
      Piensa en una cuenta bancaria. Si un usuario no especifica su saldo inicial, podríamos asignarle automáticamente un saldo de **$0.00** para que no quede sin valor.
    </td>
    <td style="border: 1px solid white; padding: 10px; vertical-align: top;">
      <img src="../Imagenes/S04_Fig02.png" alt="cuenta bancaria" width="60">
    </td>
  </tr>
</table>

✨ Esto es útil para evitar errores y asegurar que cada objeto tenga datos válidos desde el inicio.  

**✅Beneficios de los valores por defecto**  
- Evitan la creación de objetos incompletos.
- Facilitan la programación al tener datos predefinidos.
- Mejoran la estabilidad de la aplicación.

**🔎 Resumen**
- Constructor por defecto: Crea un objeto sin parámetros, asignando valores predeterminados.
- Constructor con parámetros: Permite personalizar la inicialización del objeto con valores específicos.
- Constructor de copia: Crea un nuevo objeto duplicando los valores de otro existente.
- Sobrecarga de constructores: Permite definir múltiples versiones del constructor con diferentes parámetros.
- Valores por defecto: Asegura que los objetos tengan datos iniciales para evitar errores o valores vacíos.

---

#### 📚 Tema 02. Métodos `equals()`, `hashCode()` y `toString()`  
##### ⏳ 5 minutos de lectura  

Cuando trabajas con objetos en Java, es común querer compararlos, organizarlos o imprimir su información de manera legible. Aquí es donde entran en juego estos tres métodos que serán fundamentales para escribir código eficiente, estructurado y fácil de depurar. ¡Vamos a explorarlos! 🚀  

**Importancia de estos métodos**

Java trata a los objetos como *entidades únicas en memoria*. Sin embargo, hay situaciones donde necesitamos verificar si dos objetos representan *el mismo contenido*, no solo si ocupan el mismo espacio en memoria.

**⁉️ ¿Por qué son importantes?**
| **Método**     | **¿Por qué es importante?**                                                                                     |
|----------------|-----------------------------------------------------------------------------------------------------------------|
| `equals()`     | Evita comparar direcciones de memoria y permite verificar datos.                                                |
| `hashCode()`   | Es clave en estructuras como `HashSet` o `HashMap`, donde se necesita una comparación rápida.                   |
| `toString()`   | Facilita la depuración y la visualización de datos.                                                             |

Ejemplo  
<table style="border-collapse: collapse;">
  <tr>
    <td style="border: 1px solid white; padding: 10px; vertical-align: top;">
      <img src="../Imagenes/S04_Fig03.png" alt="celular" width="60">
    </td>
    <td style="border: 1px solid white; padding: 10px;">
      Imagina que tienes dos tarjetas de identificación con el mismo nombre y número de empleado. Aunque son dos objetos físicos diferentes, representan la misma persona. 
    </td>
  </tr>
</table>


- Si comparas las tarjetas directamente, el sistema dirá que son distintas (comparación por memoria).  
- Si usas `equals()`, el sistema verificará los datos y dirá que representan a la misma persona.  
- `hashCode()` permite almacenarlas en una base de datos de forma eficiente.  
- `toString()` mostraría la información legible de la tarjeta (nombre, ID, etc.).  

**Implementación y personalización**  

📌 `equals()`  
Este método se usa para comparar el *contenido* de dos objetos. Si no se sobrescribe, usa la comparación de memoria (referencia del objeto), lo cual *no es útil en la mayoría de los casos*.  

💻 Ejemplo en código  

```java
class Persona {
    String nombre;

    public Persona(String nombre) {
        this.nombre = nombre;
    }

    `@Override`
    public boolean equals(Object obj) {
        if (this == obj) return true; // Mismo objeto en memoria
        if (obj == null || getClass() != obj.getClass()) return false;

        Persona persona = (Persona) obj;
        return this.nombre.equals(persona.nombre); // Comparamos contenido
    }
}

public class Main {
    public static void main(String[] args) {
        Persona p1 = new Persona("Fernando");
        Persona p2 = new Persona("Fernando");

        System.out.println(p1.equals(p2)); // ✅ true (compara contenido)
    }
}
```

`📌 hashCode()`  
Genera un *código único* para cada objeto. Si sobrescribes `equals()`, *también debes sobrescribir* `hashCode()`, para garantizar que objetos iguales tengan el mismo código.  

💻 Ejemplo en código  

```java
class Persona {
    String nombre;

    public Persona(String nombre) {
        this.nombre = nombre;
    }

    `@Override`
    public boolean equals(Object obj) {
        if (this == obj) return true; 
        if (obj == null || getClass() != obj.getClass()) return false;

        Persona persona = (Persona) obj;
        return this.nombre.equals(persona.nombre); 
    }

    `@Override`
    public int hashCode() {
        return nombre.hashCode(); // Genera un hash basado en el nombre
    }
}

public class Main {
    public static void main(String[] args) {
        Persona p1 = new Persona("Fernando");
        Persona p2 = new Persona("Fernando");

        System.out.println(p1.hashCode()); // ✅ Mismo hash para ambos objetos
        System.out.println(p2.hashCode()); // ✅ Mismo hash para ambos objetos
    }
}
```

**🚨 Recuerda**: Si no sobrescribimos `hashCode()`, objetos iguales podrían ser tratados como diferentes en estructuras como `HashSet` o `HashMap`, lo que podría generar errores inesperados.  

**📌 `toString()`**  
Este método convierte el objeto en un *formato legible* para los humanos. Sin sobrescribirlo, mostrará algo como Persona@3b6eb2ec (dirección de memoria), lo cual *no es útil*.  

💻 Ejemplo en código  

```java
class Persona {
    String nombre;

    public Persona(String nombre) {
        this.nombre = nombre;
    }

    `@Override`
    public String toString() {
        return "Persona {nombre='" + nombre + "'}";
    }
}

public class Main {
    public static void main(String[] args) {
        Persona p = new Persona("Fernando");
        System.out.println(p); // ✅ Persona {nombre='Fernando'}
    }
}
```

**🔎 Resumen**  
- `equals()` → Compara el contenido de los objetos para verificar si son iguales. Permite saber si dos objetos tienen los mismos datos, en lugar de solo comparar referencias de memoria.  
- `hashCode()` → Genera un código único para un objeto. Optimiza la búsqueda y almacenamiento en estructuras como `HashSet` y `HashMap`.  
- `toString()` → Convierte el objeto en una representación de texto legible. Facilita la depuración y la visualización de datos en logs y salidas de consola.  

---

#### 📚 Tema 03. Uso de de `record` y `Objects.equals()`  
##### ⏳ 5 minutos de lectura  

A medida que Java evoluciona, también lo hacen sus herramientas para hacer el código más simple y eficiente. En este apartado exploraremos dos características clave: `record` y `Objects.equals()`  

**❓ Diferencia entre `equals()` y `Objects.equals()`**  
Cuando queremos comparar objetos en Java, `equals()` es el método más utilizado. Sin embargo, hay una alternativa más segura y práctica: `Objects.equals()`. 

| **Método**          | **¿Cómo funciona?**     | **Ventaja**             |
|---------------------|-------------------------|-------------------------|
| `equals()`          | Compara el contenido de dos objetos. Si uno de ellos es `null`, lanza una excepción. | Permite personalizar la comparación, pero requiere manejo de `null`.        |
| `Objects.equals()`  | Compara los objetos y maneja `null` de forma segura. | Evita errores sin necesidad de verificaciones adicionales.  |


💻 Ejemplo en código  

```java
import java.util.Objects;

class Persona {
    String nombre;

    public Persona(String nombre) {
        this.nombre = nombre;
    }

    `@Override`
    public boolean equals(Object obj) {
        if (this == obj) return true;
        if (obj == null || getClass() != obj.getClass()) return false;

        Persona persona = (Persona) obj;
        return Objects.equals(this.nombre, persona.nombre); // ✅ Evita errores con null
    }
}

public class Main {
    public static void main(String[] args) {
        Persona p1 = new Persona(null);
        Persona p2 = new Persona(null);

        System.out.println(p1.equals(p2)); // ✅ true (sin errores)
    }
}
```

**⚡ Conclusión:**  
- Usa `Objects.equals()` para comparar objetos sin preocuparte por null.  
- Usa `equals()` cuando necesites una comparación más personalizada.  

**Ventajas de `record` en comparación con clases tradicionales**  

En Java, muchas veces creamos clases que solo almacenan datos, como *modelos* o *DTOs (Data Transfer Objects)*. Para esto, Java 14 introdujo los records, que simplifican la escritura de estas clases al reducir el código repetitivo.  

**📌Diferencias clave entre record y una clase tradicional**  

| **Característica**           | **`record`**                             | **Clase tradicional**                 |
|------------------------------|------------------------------------------|---------------------------------------|
| Código necesario             | ✨ Menos código                         | 📜 Más líneas de código               |
| Getters/Setters              | 🚀 Automáticos                          | 🏴 Se deben escribir manualmente      |
| `equals()` y `hashCode()`    | ✅ Generados automáticamente            | ⚠️ Se deben sobrescribir manualmente  |
| Mutabilidad                  | 🔒 Inmutable (los valores no cambian)   | ✏️ Se pueden modificar los atributos  |

**Ejemplo de una clase tradicional**

Antes de `record`, para crear una clase de Usuario tenías que escribir mucho código:

```java
class Usuario {
    private String nombre;
    private int edad;

    public Usuario(String nombre, int edad) {
        this.nombre = nombre;
        this.edad = edad;
    }

    public String getNombre() { return nombre; }
    public int getEdad() { return edad; }

    `@Override`
    public boolean equals(Object o) {
        if (this == o) return true;
        if (o == null || getClass() != o.getClass()) return false;
        Usuario usuario = (Usuario) o;
        return edad == usuario.edad && Objects.equals(nombre, usuario.nombre);
    }

    `@Override`
    public int hashCode() {
        return Objects.hash(nombre, edad);
    }

    `@Override`
    public String toString() {
        return "Usuario{nombre='" + nombre + "', edad=" + edad + "}";
    }
}
```
👀 Mucho código solo para una clase de datos…

**Ahora, con `record` 😍**

```java
record Usuario(String nombre, int edad) {}
```

🎉 ¡Eso es todo!  

- Java *automáticamente* genera los métodos `getNombre()`, `getEdad()`, `equals()`, `hashCode()` y `toString()`.  
- No necesitas escribir setters porque los `record` son *inmutables* (sus valores no pueden cambiar después de la creación).  

**❓¿Cuándo usar record y cuándo una clase tradicional?**  

| **Usa `record` si…**                                      | **Usa una clase tradicional si…**                                  |
|-----------------------------------------------------------|--------------------------------------------------------------------|
| Solo necesitas almacenar datos sin lógica adicional.      | Necesitas métodos adicionales, setters o lógica extra en la clase. |
| No quieres modificar los valores de los atributos.        | Necesitas modificar los valores después de la creación.            |
| Quieres reducir el código repetitivo y mantenerlo limpio. | Necesitas herencia o comportamientos más complejos.                |


**🔎 Resumen**  
- `Objects.equals()` es una forma más segura de comparar objetos sin riesgo de `NullPointerException`.  
- `equals()` debe sobrescribirse manualmente para personalizar la comparación de objetos.  
- `record` permite escribir clases de solo datos con menos código y más eficiencia.  
- Los `records` son inmutables, lo que evita cambios inesperados en los valores de los atributos.  
- Las clases tradicionales siguen siendo útiles cuando necesitas métodos adicionales o mutabilidad.  

---

#### 📚 Tema 04. Principios de encapsulación e inmutabilidad de clases
##### ⏳ 5 minutos de lectura

Si recordamos un poco, la *encapsulación* es uno de los principios fundamentales de la programación orientada a objetos (POO). Su objetivo es *proteger los datos de una clase* para evitar modificaciones no controladas y mejorar la seguridad del código.

📌 ¿Por qué es importante?  
- Evita el acceso directo a los atributos de una clase.
- Permite controlar cómo se modifican los datos.
- Facilita el mantenimiento y la seguridad del código.
- Ayuda a prevenir errores al restringir el acceso a la información interna de los objetos.  

**Getters y Setters**  

Los `getters` y `setter` permiten acceder y modificar los atributos privados de una clase de forma controlada.

➡️ Ejemplo sin encapsulación (❌ mala práctica)

```java
class Persona {
    public String nombre;
}

public class Main {
    public static void main(String[] args) {
        Persona p = new Persona();
        p.nombre = "Fernando"; // ❌ Cualquiera puede modificarlo sin restricciones
        System.out.println(p.nombre);
    }
}
```
⚠️ Problema:
El atributo `nombre` está expuesto, lo que puede generar cambios inesperados o datos inválidos.  

➡️ Ejemplo con encapsulación usando getters y setters (✅ buena práctica)  

```java
class Persona {
    private String nombre; // 🔒 Ahora es privado

    // Getter para obtener el nombre
    public String getNombre() {
        return nombre;
    }

    // Setter para modificar el nombre con control
    public void setNombre(String nombre) {
        if (nombre != null && !nombre.isEmpty()) { // ✅ Validación antes de asignar
            this.nombre = nombre;
        } else {
            System.out.println("❌ El nombre no puede estar vacío.");
        }
    }
}

public class Main {
    public static void main(String[] args) {
        Persona p = new Persona();
        p.setNombre("Fernando"); // ✅ Se asigna de forma controlada
        System.out.println(p.getNombre()); // Salida: Fernando
    }
}
```
✅ Beneficios de usar getters y setters:  
- Permiten validar datos antes de modificarlos.
- Protegen los atributos de cambios inesperados.
- Mejoran la seguridad del código.

**Inmutabilidad de clases**  

Una clase inmutable es aquella cuyos objetos no pueden cambiar una vez creados. Esto significa que:  
- Todos sus atributos son private y final.
- No tiene métodos setters.
- La única forma de asignar valores es a través del constructor.

✅ Ventajas de la inmutabilidad:    
- Mayor seguridad y estabilidad del código.
- Evita modificaciones inesperadas en los datos.
- Facilita la programación concurrente al evitar estados inconsistentes.

**🔎 Resumen**   
- Encapsulación protege los datos de una clase y evita modificaciones no controladas. 
- Buenas prácticas: Usar `private` para atributos, proporcionar `getters` y `setters`, y validar valores antes de asignarlos. 
- Getters y setters permiten acceder y modificar atributos privados de manera controlada.

---

#### 🧠 Actividad de reforzamiento  

**Relación de Columnas**  
Relaciona cada término de la columna A con su definición correspondiente en la columna B. Usa las letras para indicar la opción correcta.

| **Columna A (Términos)**              | **Columna B (Definiciones)** |
|---------------------------------------|-------------------------------|
| (____) 1. `equals()`                  | A. Genera un número único para representar un objeto. |
| (____) 2. `hashCode()`                | B. Método que convierte un objeto en una representación de texto legible. |
| (____) 3. `toString()`                | C. Permite comparar dos objetos y determinar si son iguales basándose en su contenido. |
| (____) 4. Encapsulación               | D. Concepto que impide el acceso directo a los atributos de una clase. |
| (____) 5. Getters y Setters           | E. Métodos utilizados para acceder y modificar atributos privados de manera controlada. |
| (____) 6. `record`                    | F. Estructura en Java 14 que permite definir clases de datos inmutables con menos código. |
| (____) 7. `Objects.equals()`          | G. Método de comparación que evita errores por valores `null`. |
| (____) 8. Inmutabilidad               | H. Principio que establece que un objeto no puede modificarse después de su creación. |
| (____) 9. Sobrecarga de constructores | I. Técnica que permite definir múltiples constructores en una misma clase con diferentes parámetros. |
| (____) 10. Constructor de copia       | J. Tipo de constructor que crea un nuevo objeto copiando los valores de otro existente. |

Utiliza este cuadro para reforzar tu comprensión de los términos y conceptos clave revisados en el prework.

*Respuestas*: 1-C, 2-A, 3-B, 4-D, 5-E, 6-F, 7-G, 8-H, 9-I, 10-J

---

#### 📝 Cierre  

¡Felicidades! Has completado el prework de esta sesión y ahora tienes una base sólida sobre los elementos fundamentales de una clase en Java. 🚀  

A lo largo de esta sesión, exploraste la importancia de los constructores y su correcta inicialización, comprendiste cómo los métodos `equals()`, `hashCode()` y `toString()` mejoran la gestión de objetos, y conociste herramientas modernas como `record` y `Objects.equals()` para escribir código más limpio y eficiente. Además, reforzaste los principios de encapsulación y aprendiste cómo aplicar buenas prácticas para estructurar clases de manera segura y mantenible.  

**✨ Recuerda:** La clave para dominar la programación en Java es la práctica constante. Experimenta con los conceptos, explora nuevas formas de aplicarlos y no dudes en preguntar.

**💡 ¿Listo para el siguiente nivel?** ¡Nos vemos en la sesión en vivo para seguir aprendiendo juntos! 🚀

---

⬅️ [**Anterior**](../../Sesion-03/Prework/Readme.md) | [**Siguiente**](../../Sesion-05/Prework/Readme.md)➡️