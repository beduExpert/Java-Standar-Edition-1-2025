🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 03**](../Readme.md) ➡️ / ⚡`Reto 01: Reserva de vuelos`

---

## 🎯 Objetivo

Diseñar un sistema básico de **reservas de vuelo** aplicando los fundamentos de la **Programación Orientada a Objetos** en Java. Practicarás la **creación de clases y objetos**, el uso de **atributos `static` y `final`**, así como la definición de **métodos con parámetros y valores de retorno**.

---

## 📝 Instrucciones

✈️ Tu nuevo desafío es simular un sistema donde un **pasajero** puede reservar un asiento en un **vuelo**, consultar su itinerario y cancelar la reserva si así lo desea.

---

### 🧱 1. Crear la clase `Vuelo`

🔐 **Atributos**:  
- `final String codigoVuelo`: código único del vuelo ✈️  
- `String destino`: ciudad destino del vuelo 🗺️  
- `String horaSalida`: hora de salida en formato 24h ⏰  
- `Pasajero asientoReservado`: referencia al pasajero que reservó el asiento (puede ser `null`)

🛠️ **Métodos**:  
- `Vuelo(String codigo, String destino, String horaSalida)`: constructor del vuelo  
- `boolean reservarAsiento(Pasajero p)` → Asigna al pasajero si no hay reserva previa  
- `boolean reservarAsiento(String nombre, String pasaporte)` → Método sobrecargado  
- `void cancelarReserva()` → Elimina al pasajero asignado  
- `String obtenerItinerario()` → Muestra la información del vuelo y el pasajero

---

### 👤 2. Crear la clase `Pasajero`

📋 **Atributos**:  
- `String nombre`: nombre del pasajero 👤  
- `String pasaporte`: número de pasaporte ✈️

🛠️ **Métodos**:  
- `Pasajero(String nombre, String pasaporte)`  
- `String getNombre()`  
- `String getPasaporte()`

---

### 🚀 3. En la clase `Principal`

📌 Actividades:  
- Crear al menos **un pasajero** y **un vuelo**  
- Reservar el asiento en el vuelo  
- Mostrar el itinerario  
- Cancelar la reserva  
- Mostrar nuevamente el itinerario
- Reservar un asiento en el vuelo usando un nombre y pasaporte

---

## 🧩 Salida esperada

```plaintext
✅ Reserva realizada con éxito.

✈️ Itinerario del vuelo:
Código: UX123
Destino: París
Salida: 14:30
Pasajero: Ana Martínez

❌ Cancelando reserva...

✈️ Itinerario del vuelo:
Código: UX123
Destino: París
Salida: 14:30
Pasajero: [Sin reserva]

✈️ Itinerario del vuelo:
Código: UX123
Destino: París
Salida: 14:30
Pasajero: Mario Gonzalez
```

---

🏆 Nos vemos en el siguiente reto, ¡mucho éxito!  

---

⬅️ [**Anterior**](../Ejemplo-02/Readme.md) | [**Siguiente**](../Ejemplo-03/Readme.md)➡️