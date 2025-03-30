🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 03**](../Readme.md) ➡️ / 📝 `Ejemplo 01: Creación y uso de clases y objetos`

---

## 🎯 Objetivo

Comprender cómo se **define una clase**, cómo se **crean objetos** a partir de ella, y cómo se **utilizan métodos**, aplicando estos conceptos en un contexto real de desarrollo en Java.

---

## 📌 Escenario profesional

Imagina que trabajas como **Java backend developer** para una empresa que gestiona proyectos de software. Necesitas modelar una clase que represente los proyectos activos de los clientes, con sus respectivos atributos y comportamientos.

---

## 🧱 Clase `Proyecto`

En esta sección definimos la clase `Proyecto`, que servirá como plantilla para crear proyectos con atributos clave y comportamientos típicos de un entorno profesional.

```java
public class Proyecto {

    // Atributos del proyecto
    private String nombre;
    private String cliente;
    private int duracionSemanas;
    private boolean estaActivo;

    // static - Atributo estático: número total de proyectos creados
    public static int totalProyectos = 0;

    // final - Constante: nombre del sistema
    public static final String NOMBRE_SISTEMA = "GestorProyectos v1.0";

    // Constructor
    public Proyecto(String nombre, String cliente, int duracionSemanas, boolean estaActivo) {
        this.nombre = nombre;
        this.cliente = cliente;
        this.duracionSemanas = duracionSemanas;
        this.estaActivo = estaActivo;
        totalProyectos++;  // Se incrementa cada vez que se crea un nuevo proyecto
    }

    // Método para mostrar información del proyecto
    public void mostrarInformacion() {
        System.out.println("📁 Proyecto: " + nombre);
        System.out.println("👨‍💼 Cliente: " + cliente);
        System.out.println("⏳ Duración: " + duracionSemanas + " semanas");
        System.out.println("✅ ¿Activo?: " + (estaActivo ? "Sí" : "No"));
    }

    // Método para marcar el proyecto como inactivo
    public void cerrarProyecto() {
        estaActivo = false;
        System.out.println("🚫 El proyecto '" + nombre + "' ha sido cerrado.");
    }
}

```

---

## 🧪 Uso de la clase `Proyecto`

Aquí creamos y usamos objetos de la clase `Proyecto`, ejecutando sus métodos y accediendo a atributos estáticos (`static`) y constantes (`final`).

```java
public class Principal {
    public static void main(String[] args) {

        // Uso de atributo final : Accedemos al nombre del sistema definido como constante
        System.out.println("🖥️ Sistema: " + Proyecto.NOMBRE_SISTEMA);

        // Creación de objetos: Instanciamos dos proyectos con datos reales
        Proyecto p1 = new Proyecto("Sitio Web Corporativo", "Cliente A", 12, true);
        Proyecto p2 = new Proyecto("Aplicación Móvil", "Cliente B", 20, true);

        // Uso de métodos: Mostramos los detalles de cada proyecto
        p1.mostrarInformacion();
        System.out.println();
        p2.mostrarInformacion();
        System.out.println();

        // Simulamos el cierre de un proyecto
        p1.cerrarProyecto();

        // Mostramos nuevamente los datos del proyecto cerrado
        System.out.println();
        p1.mostrarInformacion();

        // Uso de atributo static: Total de proyectos creados
        System.out.println("\n📊 Total de proyectos creados: " + Proyecto.totalProyectos);
    }
}
```

---

## 🔍 Revisión rápida

| Concepto           | Aplicación en el ejemplo                      |
|--------------------|-----------------------------------------------|
| Clase              | `Proyecto`                                    |
| Atributos          | `nombre`, `cliente`, `duracionSemanas`, etc.  |
| Atributo `static`  | `totalProyectos`                              |
| Constante `final`  | `NOMBRE_SISTEMA`                              |
| Métodos            | `mostrarInformacion()`, `cerrarProyecto()`    |
| Objetos            | `p1`, `p2`                                     |


---

## 💡 ¿Sabías que...?

🔹 En Java, los miembros `static` existen **incluso antes** de que se cree algún objeto. Por eso puedes usarlos para contar objetos o acceder a utilidades sin instanciar nada.

🔹 El modificador `final` no solo se usa en variables. También puedes tener métodos `final` (que no pueden ser sobrescritos) o clases `final` (que no pueden ser heredadas). ¡Una excelente forma de proteger tu código!

---

⬅️ [**Anterior**](../Readme.md) | [**Siguiente**](../Ejemplo-02/Readme.md)➡️
