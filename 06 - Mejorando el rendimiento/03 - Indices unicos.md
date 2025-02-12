# 🔑 Índices Únicos en MongoDB

Los **índices únicos** en MongoDB garantizan que los valores de un campo específico no se repitan en una colección, asegurando integridad y consistencia en los datos.

---

## ❓ ¿Qué es un Índice Único?
Un índice único impide la inserción de documentos con valores duplicados en un campo determinado. Si intentamos insertar un valor duplicado, MongoDB generará un error.

📌 **Ejemplo de Uso**: Garantizar que los correos electrónicos de los usuarios sean únicos.

---

## 🛠️ Creación de un Índice Único
Para crear un índice único en el campo `email` de la colección `usuarios`:
```bash
db.usuarios.createIndex({ "email": 1 }, { unique: true })
```
📌 **Nota:** El `1` indica orden ascendente, pero en un índice único el orden no afecta su funcionalidad.

---

## 🚨 Requisitos para Índices Únicos

🔹 **Los valores del campo indexado deben ser únicos en todos los documentos.**

🔹 **No se permiten valores duplicados**, cualquier intento de inserción de un duplicado generará un error.

🔹 **Los valores nulos (`null`) también son considerados únicos**, lo que significa que solo puede haber **un solo documento con `null`** en ese campo.

---

## 🗑️ Eliminación de un Índice Único
Si queremos eliminar el índice único de `email`, usamos:
```bash
db.usuarios.dropIndex("email_1")
```
Para eliminar **todos los índices** de la colección:
```bash
db.usuarios.dropIndexes()
```

---

## ✅ Tips para Usar Índices Únicos en MongoDB

🔹 **Antes de crear un índice único, asegúrate de que no existen valores duplicados en el campo**, de lo contrario, el índice no se creará.

🔹 **Si un campo puede ser nulo pero debe ser único en los casos en los que tiene un valor, usa índices parciales con `sparse: true`**:
```bash
db.usuarios.createIndex({ "telefono": 1 }, { unique: true, sparse: true })
```

🔹 **Usa índices únicos en campos que realmente deban ser únicos**, como `email`, `DNI` o `número de empleado`.

🔹 **Si necesitas actualizar valores en un campo con un índice único, verifica que el nuevo valor no esté duplicado antes de hacer la actualización.**

---
🚀 **Conclusión**: Los índices únicos en MongoDB son esenciales para mantener la integridad de los datos y prevenir valores duplicados en campos críticos. Utilízalos estratégicamente para mejorar la seguridad y confiabilidad de tus bases de datos.

