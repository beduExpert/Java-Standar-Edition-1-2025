
🏠 [**Inicio**](../../Readme.md) ➡️ / 📖 [**Sesión 04**](../Readme.md) ➡️ / ⚡`Reto 02: Comparación de declaraciones de impuestos`

## 🎯 Objetivo

📄 Modelar una declaración de impuestos con `record` y validarla contra una cuenta fiscal usando encapsulación y comparación segura con `Objects.equals()`.

---

## 📝 Instrucciones

👤 Este reto se puede resolver de forma individual.

1. 📄 Crea un `record` llamado `DeclaracionImpuestos` con los siguientes campos:
   - `String rfcContribuyente`
   - `double montoDeclarado`

2. 💼 Crea una clase tradicional llamada `CuentaFiscal` con:
   - Un atributo privado `String rfc` (no modificable una vez asignado).
   - Un atributo privado `double saldoDisponible`.

3. Implementa lo siguiente en `CuentaFiscal`:
   - Constructor con validación para que el saldo no sea negativo.
   - Getters para ambos atributos.
   - Un método `validarRFC(DeclaracionImpuestos d)` que compare el RFC de la cuenta con el de la declaración, usando `Objects.equals()`.

4. 💻 En la clase `Main`:
   - Crea una declaración de impuestos.
   - Crea una cuenta fiscal.
   - Muestra la información de ambas.
   - Valida si el RFC coincide y muestra el resultado.

---

### 📌 Ejemplo de ejecución

```plaintext
📄 Declaración enviada por RFC: XAXX010101000 por $8700.0
🏦 Cuenta fiscal registrada con RFC: XAXX010101000, saldo disponible: $9500.0
✅ ¿RFC válido para esta cuenta?: true
```

---

## 💡 ¿Sabías que...?

- En sistemas fiscales, validar el RFC del contribuyente es crucial para evitar fraudes o errores.
- `Objects.equals()` permite comparar campos sin lanzar errores si alguno es `null`.
- Usar clases inmutables y encapsuladas mejora la seguridad de las aplicaciones que manejan datos fiscales.

---

🧾 ¡Una forma útil de aplicar tus conocimientos Java en el contexto de declaraciones fiscales!

⬅️ [**Anterior**](../Ejemplo-04/Readme.md) | [**Siguiente**](../../Sesion-05/Readme.md)➡️
