# 📌 Consultas en Datos Embebidos en MongoDB

Los **documentos embebidos** en MongoDB permiten almacenar datos relacionados dentro de un mismo documento. Para consultar estos datos, es necesario utilizar una sintaxis especial que haga referencia a los campos internos.

---

## 🔍 Consultas en Datos Embebidos

### 🔹 Obtener Profesores que Imparten la Asignatura con ID `A0002`
Para buscar dentro de documentos embebidos, usamos la notación con `.` para acceder a los campos internos:
```bash
db.profesores.find({ "asignatura.id": "A0002" }).pretty()
```
📌 **Importante**: MongoDB trata `asignatura.id` como una clave anidada dentro del documento.

### 🔹 Obtener Profesores que Imparten "Termodinámica"
Podemos buscar por cualquier campo dentro del documento embebido:
```bash
db.profesores.find({ "asignatura.nombre": "Termodinámica" }).pretty()
```

---

## 🔍 Consultas con Condiciones en Datos Embebidos

### 🔹 Obtener Profesores que Imparten Asignaturas con Más de 6 Créditos
Podemos aplicar condiciones como `$gt` (mayor que) dentro de documentos embebidos:
```bash
db.profesores.find({ "asignatura.creditos": { $gt: 6 } }).pretty()
```
Esto devuelve todos los profesores cuya asignatura tiene más de 6 créditos.

### 🔹 Obtener Profesores con Asignaturas de Más de 6 Créditos y Mayores de 40 Años
Podemos combinar condiciones dentro del documento embebido y del documento principal:
```bash
db.profesores.find({ "asignatura.creditos": { $gt: 6 }, "edad": { $gt: 40 } }).pretty()
```

---

## 🔍 Consultas Combinadas en Datos Embebidos y Datos No Embebidos
MongoDB permite combinar filtros dentro de documentos embebidos con condiciones sobre los campos principales del documento.

### 🔹 Obtener Profesores Titulares que Imparten Asignaturas con Más de 4 Créditos
```bash
db.profesores.find({ "esTitular": true, "asignatura.creditos": { $gt: 4 } }).pretty()
```

### 🔹 Obtener Profesores de Más de 50 Años que Imparten "Física Cuántica"
```bash
db.profesores.find({ "edad": { $gt: 50 }, "asignatura.nombre": "Física Cuántica" }).pretty()
```

---

## ✅ Tips para Consultas en Datos Embebidos en MongoDB

🔹 **Usa la notación con `.`** para acceder a los campos internos de un documento embebido.

🔹 **Combina condiciones con operadores** como `$gt`, `$lt`, `$eq`, `$in`, etc., para mejorar la precisión de las consultas.

🔹 **Utiliza índices** en campos embebidos si las consultas sobre ellos son frecuentes, para mejorar el rendimiento.

🔹 **Prueba con `pretty()`** en la terminal para formatear mejor los resultados.

🔹 **Combina datos embebidos y principales** en una misma consulta para obtener resultados más específicos.

---
🚀 **Conclusión**: Las consultas en documentos embebidos en MongoDB permiten extraer información específica de datos relacionados dentro de un mismo documento, haciendo que las bases de datos sean más eficientes y flexibles.

