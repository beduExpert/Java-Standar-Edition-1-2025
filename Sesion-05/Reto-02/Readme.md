🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 05**](../Readme.md) ➡️ / ⚡`Reto 02: Sistema de pago con múltiples métodos`

---

## 🎯 Objetivo

Diseñar un sistema de pagos en el que distintos métodos de pago (efectivo, tarjeta, transferencia) compartan una estructura común pero tengan comportamientos específicos. Aplicarás el uso de **interfaces**, **clases abstractas**, y **polimorfismo** para modelar un flujo flexible y extensible.

---

## 🛠️ Escenario

Estás construyendo un módulo para una tienda en línea. El sistema debe permitir **procesar pagos** mediante diferentes medios: efectivo, tarjeta bancaria o transferencia.

Cada tipo de pago debe implementar su lógica de validación y confirmación, pero todos siguen un contrato general. Además, se debe permitir que en el futuro puedan agregarse nuevos métodos sin modificar los ya existentes (principio de extensión).

---

## 📝 Instrucciones

1. 🔧 Crea una **interfaz** `Autenticable` con:
   - Método `boolean autenticar()`

2. 🧱 Crea una **clase abstracta** `MetodoPago` con:
   - Atributo `monto` (double)
   - Método abstracto `procesarPago()`
   - Método concreto `mostrarResumen()` que imprima el tipo de pago y el monto

3. 💳 Crea las clases concretas que **extiendan `MetodoPago`** y **implementen `Autenticable`**:
   - `PagoEfectivo` → `autenticar()` siempre retorna `true` (no requiere validación)
   - `PagoTarjeta` → valida si hay fondos suficientes
   - `PagoTransferencia` → simula una validación bancaria externa

4. 🧠 Cada clase debe sobrescribir `procesarPago()` y `autenticar()` usando `@Override`

5. 🧪 En la clase `CajaRegistradora`:
   - Crea un arreglo de tipo `MetodoPago` con instancias mezcladas (polimorfismo)
   - Recorre el arreglo, llama a `autenticar()` y si es válido, llama a `procesarPago()` y `mostrarResumen()`

---

## 🧩 Salida esperada

```plaintext
✅ Autenticación exitosa.
💵 Procesando pago en efectivo por $150.0
📄 Tipo: PagoEfectivo - Monto: $150.0

✅ Autenticación exitosa.
💳 Procesando pago con tarjeta por $320.0
📄 Tipo: PagoTarjeta - Monto: $320.0

❌ Fallo de autenticación. Transferencia no válida.
```

---

## ✅ Conceptos aplicados

- `interface` → Contrato común (`Autenticable`)
- `abstract class` → Base común (`MetodoPago`)
- `@Override` → Reescritura de métodos con validación
- Polimorfismo → Uso genérico de referencias para métodos variados

---

🏆 ¡Vamos! Conviértete en el arquitecto de tu propio sistema de pagos.

---

⬅️ [**Anterior**](../Ejemplo-04/Readme.md) | [**Siguiente**](../Readme.md)➡️