# 🔄 Actualizar Datos en MongoDB

Actualizar documentos en MongoDB es una operación clave en la gestión de bases de datos. Se pueden modificar documentos individuales o múltiples dentro de una colección.

---

## 📌 Métodos de Actualización

### 🔹 `updateOne()` - Modificar un solo documento
Este método actualiza **el primer documento** que coincida con el filtro.

#### Ejemplo:
```bash
db.personas.updateOne(
  { "nombre": "Ana" },
  { $set: { "edad": 31 } }
)
```
Esto actualizará el campo `edad` del primer documento donde `nombre` sea "Ana".

---

### 🔹 `updateMany()` - Modificar varios documentos
Si queremos actualizar **todos los documentos** que cumplan una condición, usamos `updateMany()`.

#### Ejemplo:
```bash
db.personas.updateMany(
  { "curso": "Desarrollo web" },
  { $set: { "estado": "Graduado" } }
)
```
Esto añadirá o modificará el campo `estado` en todos los documentos donde `curso` sea "Desarrollo web".

---

### 🔹 `replaceOne()` - Reemplazar un documento completo
Si queremos **sustituir completamente** un documento por otro nuevo, usamos `replaceOne()`.

#### Ejemplo:
```bash
db.personas.replaceOne(
  { "nombre": "Carlos" },
  { "nombre": "Carlos", "edad": 26, "curso": "Ciencia de Datos" }
)
```
Esto reemplazará **todo el documento** donde `nombre` sea "Carlos", eliminando cualquier otro campo previo.

---

## 🎯 Condiciones para Actualizar Datos

MongoDB permite filtrar documentos usando condiciones avanzadas en sus consultas de actualización. Algunas de las más utilizadas son:

🔹 **Mayor que (`$gt`)**
```bash
db.personas.updateMany(
  { "edad": { "$gt": 30 } },
  { $set: { "categoria": "Senior" } }
)
```
Esto añadirá el campo `categoria` con el valor "Senior" a todos los documentos donde `edad` sea mayor que 30.

🔹 **Menor que (`$lt`)**
```bash
db.personas.updateMany(
  { "edad": { "$lt": 25 } },
  { $set: { "categoria": "Junior" } }
)
```
Esto añadirá `categoria: "Junior"` a los documentos donde `edad` sea menor de 25.

🔹 **Mayor o igual (`$gte`) y Menor o igual (`$lte`)**
```bash
db.personas.updateMany(
  { "edad": { "$gte": 18, "$lte": 30 } },
  { $set: { "categoria": "Joven Adulto" } }
)
```
Esto asignará la categoría "Joven Adulto" a las personas cuya edad esté entre 18 y 30 años.

🔹 **Igualdad (`$eq`) y Diferente (`$ne`)**
```bash
db.personas.updateMany(
  { "curso": { "$eq": "Desarrollo web" } },
  { $set: { "especializacion": "Frontend" } }
)
```
```bash
db.personas.updateMany(
  { "curso": { "$ne": "Marketing digital" } },
  { $set: { "estado": "Activo" } }
)
```
El primer caso actualizará a quienes estudian "Desarrollo web", mientras que el segundo excluye a quienes cursan "Marketing digital".

🔹 **Combinación de condiciones (`$and`, `$or`)**
```bash
db.personas.updateMany(
  { $and: [ { "edad": { "$gte": 25 } }, { "curso": "Ciencia de Datos" } ] },
  { $set: { "beca": "Aprobada" } }
)
```
Este ejemplo asigna una beca a quienes tengan 25 años o más y estudien "Ciencia de Datos".

---

## ✅ Tips para Actualizar Datos en MongoDB

🔹 **Usa `$set` para modificar solo campos específicos**, sin afectar el resto del documento.

🔹 **Evita perder datos** con `replaceOne()`, ya que sobrescribe el documento entero.

🔹 **Usa filtros precisos** para evitar actualizar más documentos de los necesarios.

🔹 **Verifica los cambios** con `find()` antes y después de una actualización.

🔹 **Combina operadores de actualización**, como `$inc` para incrementar valores numéricos:
```bash
db.personas.updateOne(
  { "nombre": "Miguel" },
  { $inc: { "edad": 1 } }
)
```

---


