🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 04**](../Readme.md) ➡️ / ⚡`Reto 02: Factura con RFC opcional`

---

## 🎯 Objetivo

Diseñar una clase `Factura` aplicando los principios de **encapsulación con modificadores de acceso** y utilizando la clase **`Optional`** para manejar valores que pueden ser nulos, como el RFC del cliente.

---

## 📝 Instrucciones

🧾 Tu reto será modelar una factura sencilla, que contenga los datos básicos de una compra y, opcionalmente, el RFC del cliente. Se deberá proteger el acceso a los atributos y permitir el uso seguro de `null` a través de `Optional`.

---

### 🧱 1. Crear la clase `Factura`

🔐 **Atributos privados**:  
- `double monto`: cantidad total de la factura 💵  
- `String descripcion`: breve concepto de lo facturado 🧾  
- `Optional<String> rfc`: RFC del cliente (puede estar presente o no)

🛠️ **Métodos públicos**:  
- `Factura(double monto, String descripcion, String rfc)`  
  - Si el RFC es `null`, debe almacenarse usando `Optional.empty()`  
- `String getResumen()` → Devuelve una cadena con los datos de la factura  
  - Si el RFC está presente, se muestra  
  - Si no, se muestra `"RFC: [No proporcionado]"`

---

### 🚀 2. En la clase `Principal`

📌 Actividades:  
- Crear al menos **2 facturas**:  
  - Una **con RFC**  
  - Otra **sin RFC** (`null`)  
- Imprimir el resumen de ambas facturas usando el método `getResumen()`

---

## 🧩 Salida esperada

```plaintext
📄 Factura generada:
Descripción: Servicio de consultoría
Monto: $2500.0
RFC: ABCC010101XYZ

📄 Factura generada:
Descripción: Reparación de equipo
Monto: $1800.0
RFC: [No proporcionado]
```

---

📌 **Nota importante:**  
En este reto deberás aplicar:
- Encapsulación (`private` + métodos públicos)
- Uso de `Optional` para evitar errores con valores nulos

---

🏆 ¡Sigue así! Este reto te ayudará a consolidar buenas prácticas de desarrollo orientado a objetos en Java.

---

⬅️ [**Anterior**](../Ejemplo-04/Readme.md) | [**Siguiente**](../../Sesion-04/Readme.md)➡️  