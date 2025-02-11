# 🗑 Eliminar Datos en MongoDB

Eliminar datos en MongoDB es un proceso muy similar a la inserción. Se pueden eliminar documentos específicos o múltiples documentos que cumplan una condición.

---

## 📌 Eliminar un Solo Documento con `deleteOne()`
El método `deleteOne()` elimina **solo el primer documento** que coincida con el criterio de búsqueda.

### 🔹 Ejemplo: Eliminar un documento específico
```bash
db.personas.deleteOne({ "nombre": "Ana" })
```
Si hay varios documentos con el nombre "Ana", **solo se eliminará el primero encontrado**.

---

## 📌 Eliminar Múltiples Documentos con `deleteMany()`
El método `deleteMany()` elimina **todos los documentos** que coincidan con el criterio de búsqueda.

### 🔹 Ejemplo: Eliminar varios documentos que cumplan una condición
```bash
db.personas.deleteMany({ "curso": "Desarrollo web" })
```
Esto eliminará **todos los documentos** en los que el campo `curso` sea "Desarrollo web".

---

## ✅ Tips para Eliminar Datos en MongoDB

🔹 **Usa criterios específicos**: Evita eliminar datos accidentalmente asegurándote de usar filtros precisos.

🔹 **Verifica antes de borrar**: Puedes usar `find()` para comprobar qué datos coincidirán antes de ejecutar `deleteOne()` o `deleteMany()`.

🔹 **No puedes recuperar datos eliminados**: Asegúrate de hacer una copia de seguridad si es necesario antes de ejecutar eliminaciones masivas.

🔹 **Elimina con precaución**: Si usas `deleteMany({})`, **borrarás todos los documentos de la colección**.

---