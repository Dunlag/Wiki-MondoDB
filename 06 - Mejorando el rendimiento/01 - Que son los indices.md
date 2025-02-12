# 📌 Introducción a los Índices en MongoDB

Los **índices** en MongoDB son estructuras de datos especiales que permiten optimizar la ejecución de las consultas, reduciendo el tiempo de búsqueda de documentos dentro de una colección.

---

## 🔍 ¿Qué son los Índices?
Los índices en MongoDB:
- Son estructuras de datos gestionadas por MongoDB.
- Almacenan una pequeña porción de los datos de la colección en un formato ordenado.
- Pueden basarse en uno o varios campos de un documento.

Cuando una consulta se ejecuta sobre un campo indexado, MongoDB puede encontrar los documentos de manera eficiente sin necesidad de recorrer toda la colección.

---

## ⚡ ¿Para Qué Sirven los Índices?
Los índices **mejoran significativamente el rendimiento** de las consultas en MongoDB, ya que:
- Permiten buscar documentos sin necesidad de escanear toda la colección.
- Aceleran la recuperación de datos al reducir el número de operaciones de lectura.
- Son especialmente útiles en grandes volúmenes de datos.

📌 **Sin un índice**, MongoDB debe escanear **todos** los documentos de la colección para encontrar coincidencias, lo que ralentiza la consulta.

---

## 📑 Tipos de Índices en MongoDB
MongoDB permite varios tipos de índices según la necesidad:

### 🔹 **Índices Simples** (Un solo campo)
Ordenan los documentos según un único campo:
```bash
db.usuarios.createIndex({ "nombre": 1 })
```
📌 **Nota:** `1` indica orden ascendente, `-1` indica orden descendente.

### 🔹 **Índices Compuestos** (Múltiples campos)
Permiten ordenar por más de un campo simultáneamente:
```bash
db.usuarios.createIndex({ "nombre": 1, "edad": -1 })
```

### 🔹 **Índices Únicos**
Evitan que se inserten valores duplicados en un campo específico:
```bash
db.usuarios.createIndex({ "email": 1 }, { unique: true })
```

### 🔹 **Índices Sparse**
Solo indexan documentos donde el campo existe:
```bash
db.usuarios.createIndex({ "telefono": 1 }, { sparse: true })
```

### 🔹 **Otros Índices**
MongoDB también soporta:
- **Hashed Index** (Índices de hash)
- **Índices geoespaciales** (`2dsphere`)
- **Índices de texto** (para búsquedas avanzadas)

---

## 📌 Listar Índices en una Colección
Para ver los índices creados en una colección:
```bash
db.usuarios.getIndexes()
```
MongoDB **crea automáticamente** un índice en el campo `_id` de cada colección:
```json
[
  { "v": 2, "key": { "_id": 1 }, "name": "_id_" }
]
```
Este índice garantiza que cada documento tenga un identificador único y optimiza las búsquedas por `_id`.

---

## ✅ Tips sobre Índices en MongoDB

🔹 **Usa índices en campos que se consulten frecuentemente** para mejorar el rendimiento.

🔹 **Evita indexar en exceso**, ya que los índices ocupan espacio y pueden ralentizar las escrituras.

🔹 **Usa índices compuestos** cuando las consultas filtren por múltiples campos.

🔹 **Recuerda que MongoDB crea automáticamente un índice en `_id`** en cada colección.

🔹 **Revisa los índices existentes** con `db.collection.getIndexes()` antes de crear nuevos.

---
