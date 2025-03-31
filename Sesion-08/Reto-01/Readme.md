
🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 08**](../Readme.md) ➡️ / ⚡`Reto 01: Motor de lógica narrativa`

---

## 🎯 Objetivo

🧠 Aplicar **refactorización** y los **principios SOLID** en un caso práctico relacionado con videojuegos narrativos, separando responsabilidades y utilizando interfaces para lograr un sistema escalable y mantenible.

---

## 📝 Instrucciones

🎮 Imagina que formas parte del equipo de desarrollo de un videojuego narrativo. Actualmente, una clase `Narrador` concentra toda la lógica de decisiones, transiciones de historia y los diálogos, lo que dificulta su mantenimiento y evolución.

Tu misión será **refactorizar este motor narrativo** para aplicar buenas prácticas de diseño orientado a objetos.

### 🧩 Actividades

1. Crea una clase principal llamada `MainNarrativa` que simule el flujo de una escena narrativa.
2. Refactoriza el diseño original (una clase gigante llamada `Narrador`) dividiendo responsabilidades en al menos estas tres interfaces:
   - `TransicionHistoria`: para definir cómo se pasa de una escena a otra.
   - `GestorDialogo`: para imprimir o manejar diálogos.
   - `LogicaDecision`: para tomar decisiones según la acción del jugador.
3. Implementa una clase por cada interfaz que cumpla una responsabilidad específica. Puedes usar nombres como `TransicionSimple`, `DialogoTexto`, `DecisionBinaria`, etc.
4. Usa inyección de dependencias para que la clase principal dependa solo de las interfaces (DIP).
5. Aplica también el principio OCP: las clases deben estar abiertas a extenderse (nuevas transiciones, nuevos diálogos) pero cerradas a modificaciones.
6. Ejecuta una simulación simple donde el usuario toma una decisión y el sistema responde con una transición de historia y un diálogo.

---

## 💡 Tip

✅ Si tienes dudas sobre cómo dividir responsabilidades, piensa en una obra de teatro:
- El **narrador** solo cuenta lo que pasa.
- Los **actores** solo dicen su diálogo.
- El **guión** decide qué sucede según lo que hagan los personajes.

---

📘 ¿Quieres repasar los principios SOLID antes de resolver el reto?  
🔗 [Guía de SOLID en Baeldung (en inglés)](https://www.baeldung.com/solid-principles)

---

🏆 ¡Este reto te ayudará a practicar una de las habilidades más valiosas en desarrollo de software profesional: el diseño limpio y mantenible!

---
⬅️ [**Anterior**](../Ejemplo-02/Readme.md) | [**Siguiente**](../Ejemplo-03/Readme.md)➡️
