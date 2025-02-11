# 🔍 Consultas con `find()` en MongoDB

El método `find()` en MongoDB nos permite realizar consultas sobre una colección y obtener los documentos que coincidan con ciertos criterios.

---

## 📌 Consultas Básicas con `find()`

### 🔹 Obtener Todos los Documentos
Para obtener todos los documentos de una colección, usamos:
```bash
db.profesores.find()
db.profesores.find({})
```
En la terminal, podemos usar `pretty()` para mejorar la legibilidad:
```bash
db.profesores.find().pretty()
```
📌 **Nota:** En MongoDB Compass no es necesario `pretty()`, ya que los datos se muestran formateados automáticamente.

---

## 📌 Filtrar Resultados con `find(<filter>)`
Podemos aplicar filtros en las consultas para obtener documentos específicos.

### 🔹 Obtener Todos los Profesores Asociados
```bash
db.profesores.find({ esAsociado: true })
```

### 🔹 Obtener Todos los Profesores Titulares y Mayores de 50 Años
```bash
db.profesores.find({ esTitular: true, edad: { $gt: 50 } }).pretty()
```

### 🔹 Obtener Profesores con Edades entre 50 y 60 Años
```bash
db.profesores.find({ edad: { $gt: 50, $lt: 60 } }).pretty()
```

---

## 📌 Contar Documentos
Podemos contar el número total de documentos en una colección:

### 🔹 Número Total de Profesores
```bash
db.profesores.count()
db.profesores.find().count()
```

### 🔹 Número Total de Profesores Asociados
```bash
db.profesores.find({ esAsociado: true }).count()
```

---

## 📌 Limitar Resultados
Si queremos obtener solo una cantidad específica de resultados, usamos `limit()`.

### 🔹 Obtener Solo los 2 Primeros Resultados
```bash
db.profesores.find().limit(2)
```

---

## ✅ Funciones Útiles en MongoDB
Además de `find()`, existen varias funciones útiles que se pueden aplicar a las consultas:

- **`count()`** → Cuenta el número total de documentos que cumplen la condición.
- **`limit(n)`** → Limita la cantidad de documentos devueltos.
- **`sort({campo: 1})`** → Ordena los resultados de forma ascendente (1) o descendente (-1).
- **`skip(n)`** → Omite los primeros `n` documentos.
- **`distinct("campo")`** → Obtiene los valores únicos de un campo.
- **`findOne({})`** → Devuelve un solo documento que coincida con el filtro.

---

