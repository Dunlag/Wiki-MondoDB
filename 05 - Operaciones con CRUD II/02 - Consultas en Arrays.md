# 📌 Consultas en Arrays en MongoDB

MongoDB permite realizar consultas dentro de **arrays** almacenados en documentos. Podemos buscar documentos que contengan valores específicos, arrays completos o que cumplan ciertas condiciones.

---

## 🔍 Consultas Básicas en Arrays

### 🔹 Obtener Profesores que Imparten Exactamente Matemáticas y Física
Para encontrar documentos donde el array `especialidad` contenga **exactamente** estos valores en el mismo orden:
```bash
db.profesores.find({ especialidad: ["matemáticas", "física"] }).pretty()
```
📌 **Nota**: Si el orden o la cantidad de elementos no es idéntica, el documento no será devuelto.

### 🔹 Obtener Profesores que Imparten Matemáticas y Física (en cualquier orden)
Para encontrar documentos donde `especialidad` contenga **ambas materias, sin importar el orden**:
```bash
db.profesores.find({ especialidad: { $all: ["física", "matemáticas"] } }).pretty()
```
📌 **Diferencia**: `$all` busca documentos donde el array **contenga todos** los valores especificados, sin importar el orden ni si hay otros valores adicionales en el array.

### 🔹 Obtener Profesores que Imparten Química
Para buscar documentos donde **uno de los valores** en `especialidad` sea "química":
```bash
db.profesores.find({ especialidad: "química" }).pretty()
```
📌 **Importante**: MongoDB busca en el array si el campo es de tipo `array`, devolviendo documentos que contengan ese valor en cualquier posición.

### 🔹 Número Total de Profesores que Imparten Biología
Para contar cuántos profesores imparten "biología":
```bash
db.profesores.find({ especialidad: "biología" }).count()
```

### 🔹 Obtener Solo 1 Profesor que Imparta Física
Si solo queremos **un profesor** que imparta física, usamos `limit(1)`:
```bash
db.profesores.find({ especialidad: "física" }).limit(1).pretty()
```

---

## ✅ Tips para Consultas en Arrays en MongoDB

🔹 **Usa `$all`** cuando necesites encontrar documentos que contengan **varios valores dentro del array** sin importar el orden.

🔹 **Evita buscar arrays completos directamente** si los elementos no siempre están en el mismo orden o pueden contener valores adicionales.

🔹 **Usa `count()`** para obtener el número total de coincidencias en lugar de `find()` si solo necesitas saber cuántos documentos cumplen la condición.

🔹 **Combina `$in` y `$all`** si necesitas más flexibilidad:
```bash
db.profesores.find({ especialidad: { $in: ["matemáticas", "física"] } }).pretty()
```
Esto devuelve profesores que imparten al menos una de esas materias.

🔹 **Usa `limit(n)`** para reducir la cantidad de documentos devueltos y mejorar el rendimiento de las consultas.

---
🚀 **Conclusión**: MongoDB ofrece múltiples formas de consultar arrays, desde búsquedas exactas hasta filtrados flexibles con operadores avanzados como `$all`, `$in` y `count()`.

