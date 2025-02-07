# 🏁 Ejercicio Práctico: Creación y Gestión de una Base de Datos en MongoDB

En este ejercicio, aprenderás a crear una base de datos, insertar documentos, visualizar bases de datos disponibles y eliminarlas.

---

## 📌 Paso 1: Crear una Base de Datos y Insertar un Documento
MongoDB no crea una base de datos hasta que se inserta al menos un documento en una colección.

1. Accede a la shell de MongoDB:
   ```bash
   mongosh
   ```
2. Cambia a la base de datos `concesionario` (esto la creará en memoria):
   ```bash
   use concesionario
   ```
3. Inserta un documento en la colección `coches`:
   ```bash
   db.coches.insertOne({
     "matricula": "ABC1234",
     "marca": "Toyota",
     "modelo": "Corolla",
     "versiones": ["sport", "confort"],
     "kms": 50000,
     "fechaMatriculacion": { "$date": "2020-05-10T00:00:00Z" }
   })
   ```
---

## 📌 Paso 2: Visualizar las Bases de Datos Disponibles
Después de insertar el documento, podemos listar las bases de datos existentes:

```bash
show dbs
```
Si la inserción fue correcta, `concesionario` aparecerá en la lista.

---

## 📌 Paso 3: Eliminar la Base de Datos y Comprobar su Eliminación

1. Asegúrate de estar en la base de datos `concesionario`:
   ```bash
   use concesionario
   ```
2. Elimina la base de datos:
   ```bash
   db.dropDatabase()
   ```
3. Comprueba que ya no existe listando las bases de datos nuevamente:
   ```bash
   show dbs
   ```

Si `concesionario` ya no aparece en la lista, significa que la eliminación fue exitosa. ✅

---

