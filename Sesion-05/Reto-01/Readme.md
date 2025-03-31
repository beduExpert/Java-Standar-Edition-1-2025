🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 05**](../Readme.md) ➡️ / ⚡`Reto 01: Sistema de emergencia`

---

## 🎯 Objetivo

Construir un sistema que modele diferentes tipos de **unidades de emergencia**, aplicando los principios de **herencia** y **composición** en Java. Reforzarás el uso de `extends`, `super`, y el diseño modular usando clases auxiliares.

---

## 🛠️ Escenario

Estás diseñando un sistema que permite registrar y activar diferentes **unidades de respuesta a emergencias**, como ambulancias, patrullas y camiones de bomberos. Aunque todas comparten ciertas funciones (como responder a una emergencia), cada una puede tener un comportamiento específico.

Además, todas las unidades están equipadas con tecnología como **sistemas GPS**, **sirenas**, y son operadas por personal capacitado. Estos componentes serán modelados mediante composición.

---

## 📝 Instrucciones

1. 🧱 Crea una clase abstracta `UnidadEmergencia` con:
   - Un atributo `nombre` (String)
   - Un método `responder()` → abstracto
   - Un método concreto `activarUnidad()` que imprima un mensaje de activación

2. 🚑 Crea las subclases:
   - `Ambulancia`
   - `Patrulla`
   - `UnidadBomberos`

   Cada clase debe:
   - Extender `UnidadEmergencia`
   - Sobrescribir el método `responder()` con un mensaje propio

3. 🧩 Crea las clases auxiliares para composición:
   - `SistemaGPS` → método `localizar()`
   - `Sirena` → método `activarSirena()`
   - `Operador` → atributo `nombre`, método `reportarse()`

4. 🔁 En cada subclase (`Ambulancia`, `Patrulla`, `UnidadBomberos`), **agrega los componentes por composición** y un método llamado `iniciarOperacion()` que invoque:
   - `activarUnidad()` (heredado)
   - `localizar()`
   - `activarSirena()`
   - `reportarse()`
   - `responder()` (implementación propia)

5. 🧪 En la clase `CentralEmergencias` (main):
   - Crea una instancia de cada tipo de unidad
   - Llama al método `iniciarOperacion()` en cada una

---

## 🧩 Salida esperada

```plaintext
🚨 Activando unidad: Ambulancia
📍 GPS: Ubicación actual detectada.
🔊 Sirena: Activada.
👷 Operador Juan reportándose.
🩺 Ambulancia en camino al hospital más cercano.

🚨 Activando unidad: Patrulla
📍 GPS: Ubicación actual detectada.
🔊 Sirena: Activada.
👮 Operador Laura reportándose.
🚓 Patrulla atendiendo situación de seguridad ciudadana.

🚨 Activando unidad: UnidadBomberos
📍 GPS: Ubicación actual detectada.
🔊 Sirena: Activada.
👨‍🚒 Operador Marco reportándose.
🔥 Unidad de bomberos respondiendo a incendio estructural.
```

---

## ✅ Conceptos que reforzarás

- 🔁 Herencia simple (`extends`) y uso de `super`
- 🧩 Composición para estructuras internas (`has-a`)
- 🧠 Uso de clases abstractas y métodos sobrescritos
- 💡 Organización modular y separación de responsabilidades

---

🏆 ¡Mucho éxito y que comience la misión de rescate!  

---

⬅️ [**Anterior**](../Ejemplo-02/Readme.md) | [**Siguiente**](../Ejemplo-03/Readme.md)➡️