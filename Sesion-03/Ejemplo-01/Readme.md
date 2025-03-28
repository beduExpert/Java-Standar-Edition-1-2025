🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 03**](../Readme.md) ➡️ / 📝 `Ejemplo 01: Creación y uso de clases y objetos`

---

## 🎯 Objetivo

Comprender cómo se **define una clase**, cómo se **crean objetos** a partir de ella, y cómo se **utilizan métodos**, aplicando estos conceptos en un contexto real de desarrollo en Java.

---

## 📌 Escenario profesional

Imagina que trabajas como **desarrollador backend Java** para una empresa que gestiona proyectos de software. Necesitas modelar una clase que represente los proyectos activos de los clientes, con sus respectivos atributos y comportamientos.

---

## 🧱 Clase `Project`

En esta sección definimos la clase `Project`, que servirá como plantilla para crear proyectos con atributos clave y comportamientos típicos de un entorno profesional.

```java
public class Project {

    // Atributos del proyecto
    private String name;
    private String client;
    private int durationWeeks;
    private boolean isActive;

    // static - Atributo estático: número total de proyectos creados
    public static int totalProjects = 0;

    // final - Constante: nombre del sistema
    public static final String SYSTEM_NAME = "GestorProyectos v1.0";

    // Constructor
    public Project(String name, String client, int durationWeeks, boolean isActive) {
        this.name = name;
        this.client = client;
        this.durationWeeks = durationWeeks;
        this.isActive = isActive;
        totalProjects++;  // Se incrementa cada vez que se crea un nuevo proyecto
    }

    // Método para mostrar información del proyecto
    public void showInfo() {
        System.out.println("📁 Proyecto: " + name);
        System.out.println("👨‍💼 Cliente: " + client);
        System.out.println("⏳ Duración: " + durationWeeks + " semanas");
        System.out.println("✅ ¿Activo?: " + (isActive ? "Sí" : "No"));
    }

    // Método para marcar el proyecto como inactivo
    public void closeProject() {
        isActive = false;
        System.out.println("🚫 El proyecto '" + name + "' ha sido cerrado.");
    }
}
```

---

## 🧪 Uso de la clase `Project`

Aquí creamos y usamos objetos de la clase `Project`, ejecutando sus métodos y accediendo a atributos estáticos (`static`) y constantes (`final`).

```java
public class Main {
    public static void main(String[] args) {

        // Uso de atributo final : Accedemos al nombre del sistema definido como constante
        System.out.println("🖥️ Sistema: " + Project.SYSTEM_NAME);

        // Creación de objetos: Instanciamos dos proyectos con datos reales, como lo haría un desarrollador en un sistema empresarial
        Project p1 = new Project("Sitio Web Corporativo", "Cliente A", 12, true);
        Project p2 = new Project("Aplicación Móvil", "Cliente B", 20, true);

        // Uso de métodos: Llamamos al método showInfo() para mostrar los detalles de cada proyecto
        p1.showInfo();
        System.out.println();
        p2.showInfo();
        System.out.println();

        // Uso de métodos: Simulamos el cierre de un proyecto usando un método que modifica su estado interno
        p1.closeProject();

        // Mostramos nuevamente los datos del proyecto cerrado
        System.out.println();
        p1.showInfo();

        // Uso de atributo static: Accedemos a una variable compartida entre todas las instancias para saber cuántos proyectos se han creado
        System.out.println("\n📊 Total de proyectos creados: " + Project.totalProjects);
    }
}
```

---

## 🔍 Revisión rápida

| Concepto         | Aplicación en el ejemplo                 |
|------------------|-------------------------------------------|
| Clase            | `Project`                                |
| Atributos        | `name`, `client`, `durationWeeks`, etc. |
| Atributo `static`| `totalProjects`                          |
| Constante `final`| `SYSTEM_NAME`                            |
| Métodos          | `showInfo()`, `closeProject()`           |
| Objetos          | `p1`, `p2`                               |

---

## 💡 ¿Sabías que...?

🔹 En Java, los miembros `static` existen **incluso antes** de que se cree algún objeto. Por eso puedes usarlos para contar objetos o acceder a utilidades sin instanciar nada.

🔹 El modificador `final` no solo se usa en variables. También puedes tener métodos `final` (que no pueden ser sobreescritos) o clases `final` (que no pueden ser heredadas). ¡Una excelente forma de proteger tu código!

---

⬅️ [**Anterior**](../Readme.md) | [**Siguiente**](../Reto-01/Readme.md)➡️
