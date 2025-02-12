# 🏪 Ejercicio Propuesto: Base de Datos `tienda`

En este ejercicio, trabajaremos con una base de datos llamada `tienda` y su colección `productos`. Realizaremos operaciones de inserción, eliminación y actualización de datos.

---

## 📌 Paso 1: Crear la Base de Datos y la Colección
```bash
use tienda
```

---

## 📌 Paso 2: Insertar Documentos Individualmente
```bash
db.productos.insertOne({ "referencia": 101, "nombre": "Camisa", "precio": 20, "genero": "hombre", "talla": "L" })
db.productos.insertOne({ "referencia": 102, "nombre": "Pantalón", "precio": 35, "genero": "mujer", "talla": "M" })
db.productos.insertOne({ "referencia": 103, "nombre": "Zapatos", "precio": 50, "genero": "hombre", "talla": "42" })
```

---

## 📌 Paso 3: Eliminar Todos los Documentos
```bash
db.productos.deleteMany({})
```

---

## 📌 Paso 4: Insertar Todos los Documentos a la Vez
```bash
db.productos.insertMany([
  { "referencia": 101, "nombre": "Camisa", "precio": 20, "genero": "hombre", "talla": "L" },
  { "referencia": 102, "nombre": "Pantalón", "precio": 35, "genero": "mujer", "talla": "M" },
  { "referencia": 103, "nombre": "Zapatos", "precio": 50, "genero": "hombre", "talla": "42" }
])
```

---

## 📌 Paso 5: Actualizar los Precios Inferiores a 25
```bash
db.productos.updateMany(
  { "precio": { "$lt": 25 } },
  { "$mul": { "precio": 1.1 } }
)
```

---

## 📌 Paso 6: Reemplazar Documentos para Hombre Añadiendo `paraMujer: false`
```bash
db.productos.updateMany(
  { "genero": "hombre" },
  { "$set": { "paraMujer": false } }
)
```

---

## 📌 Paso 7: Reemplazar Documentos para Mujer Añadiendo `paraHombre: false`
```bash
db.productos.updateMany(
  { "genero": "mujer" },
  { "$set": { "paraHombre": false } }
)
```

---

## 📌 Paso 8: Actualizar Productos con Referencia Específica
```bash
db.productos.updateMany(
  { "referencia": { "$exists": true }, "nombre": "Camisa", "talla": "M" },
  { "$set": { "nombre": "Chaqueta" } }
)
```

---
🚀 **¡Ejercicio completado!** Con estos pasos, has practicado la creación, eliminación y actualización de documentos en MongoDB. 🎯
