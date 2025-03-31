
🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 04**](../Readme.md) ➡️ / ⚡`Reto 01: Registro y comparación de facturas`


## 🎯 Objetivo

💼 Modelar facturas emitidas para un sistema contable, reforzando el uso de **constructores**, `equals()`, `hashCode()` y `toString()`.

---

## 📝 Instrucciones

👤 Este reto se puede resolver de forma individual.

1. 📄 Crea una clase llamada `Factura`.

2. Declara los siguientes atributos:
   - `String folio`
   - `String cliente`
   - `double total`

3. Implementa lo siguiente:
   - Un constructor con parámetros para inicializar todos los atributos.
   - El método `toString()` para mostrar la información de la factura con este formato:  

     ```plaintext
     🧾 Factura [folio=..., cliente=..., total=$...]
     ```
   - El método `equals()` para que dos facturas se consideren iguales si tienen el **mismo folio**.
   - El método `hashCode()` basado en el atributo `folio`.

4. 💻 En la clase `Main`:
   - Crea dos facturas con el mismo folio pero diferentes clientes o totales.
   - Muestra ambas con `toString()`.
   - Compara si son iguales con `equals()`.

---

### 📌 Ejemplo de ejecución

```plaintext
🧾 Factura [folio=FAC001, cliente=Juan Pérez, total=$1450.0]
🧾 Factura [folio=FAC001, cliente=Comercial XYZ, total=$1450.0]
¿Las facturas son iguales?: true
```

---

## 💡 ¿Sabías que...?

- En contabilidad, el **folio fiscal** es único por cada comprobante, por lo que debe usarse como identificador clave.
- Este tipo de modelado se aplica en sistemas de facturación electrónica y contabilidad empresarial.

---

📊 ¡Una excelente forma de practicar lógica Java con aplicación real en el mundo financiero!

⬅️ [**Anterior**](../Ejemplo-02/Readme.md) | [**Siguiente**](../Ejemplo-03/Readme.md)➡️
