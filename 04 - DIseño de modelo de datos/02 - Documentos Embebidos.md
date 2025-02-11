# 📦 Documentos Embebidos en MongoDB

Los **documentos embebidos** permiten almacenar datos relacionados dentro de un mismo documento en lugar de separarlos en diferentes colecciones. Esto mejora la eficiencia en consultas y facilita la recuperación de datos sin necesidad de realizar múltiples búsquedas.

---

## 📌 ¿Qué son los Documentos Embebidos?
El concepto **embebido** se refiere a guardar una **estructura de datos dentro de otra**. En MongoDB, esto significa almacenar un documento **JSON dentro de otro documento JSON** como valor de una de sus propiedades.

✅ **Ventaja:** Agrupa información relacionada en un solo documento, reduciendo la necesidad de hacer `joins` o múltiples consultas.

❌ **Desventaja:** Si los datos embebidos crecen demasiado, el documento puede volverse difícil de manejar.

---

## 🎓 Ejemplo: Curso con Asignaturas Embebidas
Imaginemos que queremos modelar un **curso** con sus asignaturas. En lugar de tener una colección separada para las asignaturas, podemos embebidas dentro del documento del curso:

```json
{
  "id": "C0001",
  "nombre": "Desarrollo Web",
  "duracion": "6 meses",
  "asignaturas": [
    {
      "id": "A101",
      "nombre": "HTML y CSS",
      "duracion": "1 mes"
    },
    {
      "id": "A102",
      "nombre": "JavaScript",
      "duracion": "2 meses"
    },
    {
      "id": "A103",
      "nombre": "Bases de Datos",
      "duracion": "3 meses"
    }
  ]
}
```

Este documento representa un curso (`C0001` - Desarrollo Web) y dentro de él, las asignaturas están almacenadas en un **array de documentos embebidos**.

---

## 📌 Inserción en MongoDB
Para insertar este curso en una colección `cursos`, podemos usar el siguiente comando:
```bash
db.cursos.insertOne({
  "id": "C0001",
  "nombre": "Desarrollo Web",
  "duracion": "6 meses",
  "asignaturas": [
    { "id": "A101", "nombre": "HTML y CSS", "duracion": "1 mes" },
    { "id": "A102", "nombre": "JavaScript", "duracion": "2 meses" },
    { "id": "A103", "nombre": "Bases de Datos", "duracion": "3 meses" }
  ]
})
```

---

## 📌 Consulta de Datos Embebidos
Podemos obtener información específica dentro de un documento embebido. Por ejemplo, para encontrar un curso que contenga la asignatura "JavaScript":
```bash
db.cursos.find({ "asignaturas.nombre": "JavaScript" }).pretty()
```

Esto devolverá todos los cursos donde haya una asignatura llamada "JavaScript".

---

## ✅ ¿Cuándo Usar Documentos Embebidos?
✅ Cuando los datos relacionados **siempre se consultan juntos** (Ejemplo: Curso y sus asignaturas).
✅ Cuando la cantidad de datos embebidos **no crece demasiado**.
✅ Cuando queremos reducir el número de consultas necesarias para obtener la información completa.

❌ No es recomendable cuando:
✖ La información embebida **puede cambiar frecuentemente de manera individual**.
✖ El número de documentos embebidos **es muy grande**, lo que puede hacer que el documento principal crezca demasiado.

---
🚀 **Conclusión**: Los documentos embebidos en MongoDB permiten organizar mejor los datos relacionados y mejorar el rendimiento de las consultas. Sin embargo, es importante evaluar cuándo es la mejor opción frente a un diseño basado en referencias.

