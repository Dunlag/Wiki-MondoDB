# 📊 Tipos de Datos en MongoDB

MongoDB admite una variedad de tipos de datos que se pueden clasificar en dos grandes categorías: **simples** y **complejos**.

## 🔹 Categorías de Tipos de Datos

### ✨ Tipos de Datos Simples
Estos tipos de datos son básicos y similares a los que encontramos en otros lenguajes de programación.

- **Números** (`int`, `double`, `long`, `decimal`)
  ```json
  { "edad": 30, "precio": 19.99 }
  ```
- **Cadenas de texto** (`string`)
  ```json
  { "nombre": "Juan", "mensaje": "Hola Mundo" }
  ```
- **Fechas y horas** (`Date`) - Formato ISO 8601
  ```json
  { "fechaNacimiento": { "$date": "2024-02-07T12:00:00Z" } }
  ```
- **Booleanos** (`true` / `false`)
  ```json
  { "esActivo": true, "esAdmin": false }
  ```

### 🛠 Tipos de Datos Complejos
Estos tipos permiten representar estructuras de datos más avanzadas.

- **Arrays** (Listas de valores)
  ```json
  { "etiquetas": ["MongoDB", "NoSQL", "Base de Datos"] }
  ```
- **Objetos** (Documentos anidados)
  ```json
  { "usuario": { "nombre": "Ana", "edad": 25 } }
  ```
- **Binary Data** (`BinData`) - Datos binarios como imágenes o archivos
- **ObjectId** - Identificadores únicos generados por MongoDB
  ```json
  { "_id": ObjectId("507f1f77bcf86cd799439011") }
  ```
- **Expresiones regulares** (`RegExp`)
  ```json
  { "patron": { "$regex": "^A.*", "$options": "i" } }
  ```

## ✅ Ejemplos Completos

Ejemplo de un documento con distintos tipos de datos:
```json
{
  "nombre": "Carlos",
  "edad": 28,
  "correo": "carlos@email.com",
  "esSuscriptor": true,
  "fechaRegistro": { "$date": "2023-01-15T08:30:00Z" },
  "favoritos": ["JavaScript", "MongoDB"],
  "perfil": { "rol": "admin", "experiencia": 5 },
  "_id": ObjectId("507f1f77bcf86cd799439011")
}
```

---
✅ Conociendo estos tipos de datos, puedes modelar estructuras eficientes en MongoDB. 🚀

