# 📌 Índices Simples y Compuestos en MongoDB

Los índices en MongoDB mejoran el rendimiento de las consultas al permitir búsquedas más rápidas. En esta sección, explicaremos los **índices simples** y **compuestos**, cómo crearlos, eliminarlos y cuándo utilizarlos.

---

## 🔍 Índices Simples en MongoDB

### ❓ ¿Qué es un Índice Simple?
Un **índice simple** se aplica sobre un único campo de una colección. Permite ordenar y buscar eficientemente en ese campo específico.

### 🛠️ Creación de un Índice Simple
Para crear un índice en el campo `edad` ordenado de forma descendente:
```bash
db.usuarios.createIndex({ "edad": -1 })
```
📌 **Nota:** `1` indica orden ascendente y `-1` indica orden descendente.

### 🗑️ Eliminación de un Índice Simple
Para eliminar un índice en `edad`:
```bash
db.usuarios.dropIndex("edad_-1")
```
Para eliminar **todos los índices** de la colección:
```bash
db.usuarios.dropIndexes()
```

### 🎯 ¿Cuándo Usar Índices Simples?
✅ Cuando se realizan búsquedas frecuentes en un solo campo, como `email` o `DNI`.
✅ Cuando el campo es usado en `sort()`, mejorando el rendimiento de ordenamientos.

---

## 🔗 Índices Compuestos en MongoDB

### ❓ ¿Qué es un Índice Compuesto?
Un **índice compuesto** se aplica a **varios campos** dentro de una colección, permitiendo optimizar consultas que involucren múltiples criterios de búsqueda.

### 🛠️ Creación de un Índice Compuesto
Para crear un índice en `nombre` (ascendente) y `fechaRegistro` (descendente):
```bash
db.usuarios.createIndex({ "nombre": 1, "fechaRegistro": -1 })
```
Este índice permitirá buscar usuarios por nombre y ordenarlos por fecha de registro de forma descendente.

### 🗑️ Eliminación de un Índice Compuesto
Para eliminar el índice compuesto en `nombre` y `fechaRegistro`:
```bash
db.usuarios.dropIndex("nombre_1_fechaRegistro_-1")
```

### 🎯 ¿Cuándo Usar Índices Compuestos?
✅ Cuando se realizan consultas combinadas en **dos o más campos** frecuentemente.
✅ Cuando se requiere **ordenar resultados** según más de un criterio.

---

## ✅ Tips para el Uso de Índices en MongoDB

🔹 **Evita sobrecargar la colección con índices innecesarios**, ya que pueden afectar el rendimiento en escrituras.

🔹 **Utiliza índices compuestos solo cuando las consultas requieran múltiples campos**; si solo buscas por uno, un índice simple es suficiente.

🔹 **Usa `explain()` para analizar el impacto de los índices en una consulta**:
```bash
db.usuarios.find({ "nombre": "Juan" }).explain("executionStats")
```

🔹 **Combina índices con `sort()` para optimizar la ordenación de resultados**:
```bash
db.usuarios.find().sort({ "fechaRegistro": -1 })
```

---
🚀 **Conclusión**: Los índices simples y compuestos son herramientas clave para mejorar la eficiencia de las consultas en MongoDB.

