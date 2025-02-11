# 🔗 Documentos Referenciados en MongoDB

Los **documentos referenciados** son una estrategia de diseño en MongoDB en la que en lugar de almacenar datos embebidos dentro de un documento, se guarda una referencia a otro documento almacenado en una colección separada. Esto permite establecer relaciones entre documentos sin duplicar información.

---

## 📌 ¿Qué son los Documentos Referenciados?
A diferencia de los **documentos embebidos**, en los documentos referenciados se almacena únicamente el valor de una propiedad (normalmente un **ID único**) que permite recuperar los datos desde otra colección.

✅ **Ventaja**: Evita la duplicación de datos y facilita actualizaciones sin afectar múltiples documentos.

❌ **Desventaja**: Para obtener la información completa, es necesario hacer consultas adicionales a otras colecciones.

---

## 🎓 Ejemplo: Curso con Asignaturas Referenciadas
Imaginemos que tenemos una colección `cursos` y una colección `asignaturas`, donde cada curso tiene asignaturas asociadas mediante referencias.

### 📂 **Colección `cursos`** (con referencias a las asignaturas)
```json
{
  "id": "C0001",
  "nombre": "Desarrollo Web",
  "duracion": "6 meses",
  "asignaturas": ["A101", "A102", "A103"]
}
```

### 📂 **Colección `asignaturas`** (documentos independientes)
```json
{
  "id": "A101",
  "nombre": "HTML y CSS",
  "duracion": "1 mes"
}
```
```json
{
  "id": "A102",
  "nombre": "JavaScript",
  "duracion": "2 meses"
}
```
```json
{
  "id": "A103",
  "nombre": "Bases de Datos",
  "duracion": "3 meses"
}
```

Con este enfoque, los cursos solo almacenan las **referencias** de las asignaturas, en lugar de guardar toda la información dentro del mismo documento.

---

## 📌 Ventajas y Desventajas

### ✅ **Ventajas de los Documentos Referenciados**
✔ **Consultas más eficientes** sobre colecciones principales sin datos redundantes.
✔ **Facilita actualizaciones** en documentos relacionados sin modificar múltiples registros.
✔ **Menor consumo de almacenamiento**, ya que la información no se duplica.

### ❌ **Desventajas de los Documentos Referenciados**
✖ **Se requieren consultas adicionales** para recuperar la información completa.
✖ **Mayor complejidad en las consultas**, ya que puede ser necesario hacer `lookup` o varias búsquedas encadenadas.

---

## 📌 Comparación: ¿Cuándo Usar Documentos Embebidos o Referenciados?

| Característica         | Documentos Embebidos | Documentos Referenciados |
|-----------------------|--------------------|--------------------|
| **Consultas rápidas** | ✅ Sí              | ❌ No (requiere consultas extra) |
| **Estructura flexible** | ✅ Sí              | ✅ Sí              |
| **Evita duplicación de datos** | ❌ No | ✅ Sí |
| **Facilidad de actualización** | ❌ No (requiere modificar muchos documentos) | ✅ Sí |

### 📌 **Cuándo Usar Documentos Embebidos**
✅ Cuando los datos relacionados **se consultan juntos con frecuencia** (Ejemplo: Un pedido y sus productos).
✅ Cuando la cantidad de datos embebidos **es pequeña y no cambia constantemente**.

### 📌 **Cuándo Usar Documentos Referenciados**
✅ Cuando los datos relacionados **se actualizan frecuentemente**.
✅ Cuando el número de referencias puede ser **grande y variable**.
✅ Cuando se requiere evitar la **duplicación de información**.

---
🚀 **Conclusión**: Los documentos referenciados en MongoDB permiten crear relaciones eficientes entre colecciones, reduciendo la redundancia de datos y optimizando las actualizaciones. Sin embargo, dependiendo del contexto, puede ser más conveniente usar documentos embebidos para mejorar el rendimiento de las consultas.

