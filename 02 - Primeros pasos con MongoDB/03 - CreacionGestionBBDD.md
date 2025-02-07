# Creación y Gestión de Bases de Datos en MongoDB

MongoDB permite crear y gestionar bases de datos de forma sencilla mediante su consola interactiva `mongosh`. A continuación, se detallan los pasos básicos para trabajar con bases de datos.

## 📌 Creación de una Base de Datos

Para crear una base de datos en MongoDB, se usa el comando `use`:
```bash
use concesionario
```
> ⚠️ **Nota**: Aunque se haya ejecutado el comando, la base de datos no aparece en la lista hasta que se inserte al menos un documento.

### Verificar bases de datos existentes
Para listar las bases de datos disponibles:
```bash
show dbs
```
Al ejecutar este comando justo después de `use concesionario`, no aparecerá `concesionario` hasta que se inserte un documento.

## 🚗 Creación de una Colección e Inserción de Datos

Para que la base de datos se registre, insertamos un documento en una colección `coches`:
```bash
db.coches.insertOne({ matricula: "AAA5678" })
```
Este comando crea la colección `coches` si no existe e inserta un documento con una matrícula.

### Verificar la existencia de la base de datos
Después de la inserción, podemos comprobar nuevamente:
```bash
show dbs
```
Ahora `concesionario` sí aparecerá en la lista.

## 🗑 Eliminación de una Base de Datos

Para eliminar la base de datos `concesionario`, se usa:
```bash
db.dropDatabase()
```
Esto eliminará la base de datos en la que estemos trabajando actualmente.

### Verificar la eliminación
Podemos comprobar que la base de datos ha sido eliminada:
```bash
show dbs
```
Ahora `concesionario` ya no estará en la lista.

---
✅ Con estos pasos, hemos aprendido a crear, visualizar y eliminar bases de datos en MongoDB. 🚀