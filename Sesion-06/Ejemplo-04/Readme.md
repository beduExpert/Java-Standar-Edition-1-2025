🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 06**](../Readme.md) ➡️ / 📝 `Ejemplo 04: Introducción a colecciones concurrentes`

## 🎯 Objetivo

Introducir el uso de colecciones seguras en entornos multihilo mediante `CopyOnWriteArrayList` y `ConcurrentHashMap`, aplicadas en una simulación simple que puede vivir un desarrollador en una aplicación con múltiples usuarios concurrentes.

---

## 💼 Escenario profesional: Servidor de monitoreo industrial

Imagina que trabajas en una planta industrial y estás desarrollando una app que:

- Registra en tiempo real los **nombres de técnicos conectados** al sistema (pueden entrar/salir en cualquier momento).

- Guarda y actualiza las **últimas lecturas de temperatura** de distintas máquinas, cada una identificada por su código.

En una aplicación real, cada lectura podría provenir de un hilo distinto. Por eso, necesitas estructuras seguras para evitar errores de concurrencia.

---

## 💻 Código en Java

```java
import java.util.List;
import java.util.concurrent.CopyOnWriteArrayList;
import java.util.concurrent.ConcurrentHashMap;

public class MonitoreoConcurrente {
    public static void main(String[] args) {

        // Lista concurrente: usuarios conectados
        List<String> tecnicosConectados = new CopyOnWriteArrayList<>();
        tecnicosConectados.add("Ana");
        tecnicosConectados.add("Luis");
        tecnicosConectados.add("Carlos");

        // Simulación de lectura de usuarios conectados desde varios hilos
        System.out.println("👥 Técnicos actualmente conectados:");
        for (String tecnico : tecnicosConectados) {
            System.out.println("- " + tecnico);
        }

        // Mapa concurrente: sensores por máquina
        ConcurrentHashMap<String, Double> sensoresTemperatura = new ConcurrentHashMap<>();
        sensoresTemperatura.put("M-01", 68.5);
        sensoresTemperatura.put("M-02", 72.3);
        sensoresTemperatura.put("M-03", 70.0);

        // Simulación de actualización concurrente (solo un hilo en este caso)
        sensoresTemperatura.put("M-01", 69.1); // Nueva lectura
        sensoresTemperatura.put("M-04", 65.7); // Nueva máquina

        System.out.println("\n🌡️ Temperaturas por máquina:");
        for (String maquina : sensoresTemperatura.keySet()) {
            System.out.println(maquina + " → " + sensoresTemperatura.get(maquina) + " °C");
        }
    }
}
```

---

## 🧠 ¿Qué conceptos se aplican aquí?

| Colección              | ¿Qué resuelve?                           |
|------------------------|-------------------------------------------|
| `CopyOnWriteArrayList` | Lectura segura de usuarios conectados     |
| `ConcurrentHashMap`    | Escritura segura de sensores en paralelo  |

---

## 💡 ¿Sabías que...?

- Las colecciones tradicionales (`ArrayList`, `HashMap`) pueden fallar en entornos multihilo.
- `CopyOnWriteArrayList` es ideal cuando hay muchas lecturas y pocas escrituras.
- `ConcurrentHashMap` divide internamente el acceso en segmentos para mayor rendimiento.

---

⬅️ [**Anterior**](../Ejemplo-03/Readme.md) | [**Siguiente**](../Reto-03/Readme.md) ➡️