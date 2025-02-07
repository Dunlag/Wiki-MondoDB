# Trabajando con MongoDB desde la Consola

## 📌 Comandos Útiles en MongoDB

### Navegación y Gestión de Bases de Datos
- **Limpiar la consola**: `Ctrl + L`
- **Listar las bases de datos**: 
  ```bash
  show dbs
  ```
- **Cambiarse de base de datos**: 
  ```bash
  use <dbname>
  ```
- **Listar las colecciones de una base de datos**: 
  ```bash
  show collections
  ```
  o
  ```bash
  show tables
  ```
- **Mostrar el nombre de la base de datos actual**: 
  ```bash
  db.getName()
  ```
  o simplemente:
  ```bash
  db
  ```

### Información y Metadatos
- **Listar metadata sobre una base de datos**: 
  ```bash
  db.stats()
  ```
- **Solicitar ayuda sobre comandos**: 
  ```bash
  db.help()
  ```
- **Mostrar información sobre el servidor**: 
  ```bash
  db.hostInfo()
  ```
- **Mostrar fecha y hora del sistema**: 
  ```bash
  Date()
  ```
- **Dar formato JSON a la consulta**: 
  ```bash
  db.<collectionName>.find().pretty()
  ```

---

