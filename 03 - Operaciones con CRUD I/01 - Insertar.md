# 📝 Insertar Datos en MongoDB

MongoDB permite insertar datos en una colección mediante los métodos `insertOne()` para un solo documento y `insertMany()` para múltiples documentos.

---

## 📌 Insertar un Solo Documento
Para insertar un único documento en una colección, usamos `insertOne()`.

### 🔹 Ejemplo: Insertar un documento en la colección `personas` dentro de la base de datos `universidad`
```bash
use universidad
```
```bash
db.personas.insertOne({
  "nombre": "Ana",
  "edad": 30,
  "curso": "Ingenieria de software"
})
```

---

## 📌 Insertar Múltiples Documentos
Para insertar varios documentos a la vez, usamos `insertMany()`. **Es importante recordar que los documentos deben estar dentro de un array (`[]`) y separados por comas.**

### 🔹 Ejemplo: Insertar varios documentos en la colección `personas`
```bash
db.personas.insertMany([
  {
    "nombre": "Carlos",
    "edad": 25,
    "curso": "Desarrollo web"
  },
  {
    "nombre": "Sofía",
    "edad": 22,
    "curso": "Marketing digital"
  },
  {
    "nombre": "Miguel",
    "edad": 35,
    "curso": "Análisis de datos"
  }
])
```

---

## ✅ Tips para Insertar Datos en MongoDB

🔹 **Estructura Correcta:** En `insertMany()`, los documentos deben estar **dentro de un array** y **separados por comas**.

🔹 **No es necesario definir un ID:** MongoDB genera automáticamente un campo `_id` si no lo especificas.

🔹 **Las claves deben ser strings:** Asegúrate de que las claves del JSON estén entre comillas dobles `""` para evitar errores.

🔹 **Las inserciones no son transaccionales:** Si usas `insertMany()`, algunos documentos pueden insertarse correctamente y otros fallar.

🔹 **Validar datos antes de insertar:** MongoDB no impone un esquema fijo, por lo que es recomendable validar los datos manualmente o con herramientas como Mongoose.

---


