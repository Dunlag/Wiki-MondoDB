# 📂 Colecciones en MongoDB

MongoDB es una base de datos NoSQL que organiza la información en **colecciones** y **documentos**, a diferencia de las bases de datos SQL tradicionales que utilizan **tablas** y **filas**.

## 🏛 Comparación entre Bases de Datos SQL y NoSQL

### 🔹 Base de Datos SQL
En una base de datos relacional (SQL), la información se organiza en:
- **Tablas**: Conjuntos de datos estructurados.
- **Filas o registros**: Cada fila representa una entidad específica.
- **Columnas o campos**: Definen las propiedades de los datos almacenados.

Ejemplo en SQL:
```
Tabla: Coches
| Matricula  | Marca  | Modelo   |
|------------|--------|---------|
| AAA5678    | Toyota | Corolla |
| BBB1234    | Ford   | Focus   |
```

### 🔹 Base de Datos NoSQL (MongoDB)
MongoDB utiliza una estructura más flexible basada en:
- **Colecciones**: Equivalente a una tabla en SQL.
- **Documentos**: Equivalente a una fila, almacenado en formato **JSON** o **BSON**.
- **Propiedades**: Similares a las columnas, pero no requieren un esquema fijo.

Ejemplo en MongoDB:
```json
{
  "matricula": "AAA5678",
  "marca": "Toyota",
  "modelo": "Corolla"
}
```

## 📌 Creación y Gestión de Colecciones

### 🔹 Creación de una Colección e Inserción de Datos
En MongoDB, las colecciones se crean automáticamente al insertar el primer documento:
```bash
db.coches.insertOne({ matricula: "AAA5678", marca: "Toyota", modelo: "Corolla" })
```

### 🔹 Listar Colecciones Disponibles
Para ver las colecciones en la base de datos actual:
```bash
show collections
```

### 🔹 Visualizar los Documentos de una Colección
Para ver todos los documentos en una colección:
```bash
db.coches.find()
```
Si queremos que la salida sea más legible:
```bash
db.coches.find().pretty()
```

## 🗑 Eliminación de Colecciones
Si necesitamos eliminar una colección, usamos:
```bash
db.coches.drop()
```

---
✅ Con esta guía, has aprendido la diferencia entre SQL y NoSQL, la estructura de MongoDB y cómo gestionar colecciones. 🚀

