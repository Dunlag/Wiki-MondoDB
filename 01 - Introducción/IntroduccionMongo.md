
# Guía 1: Introducción a MongoDB

## 1. ¿Qué son las bases de datos SQL?

Las bases de datos SQL (Structured Query Language) son sistemas de gestión de bases de datos relacionales (RDBMS) que utilizan tablas para almacenar y organizar los datos. Estas bases de datos utilizan un lenguaje estructurado de consultas (SQL) para realizar operaciones como insertar, actualizar, eliminar y consultar datos. 

### Características principales de las bases de datos SQL:
- **Estructura tabular:** Los datos se organizan en tablas con filas y columnas.
- **Modelo relacional:** Las tablas pueden estar relacionadas entre sí a través de claves primarias y foráneas.
- **Normalización:** Se busca reducir la redundancia de los datos dividiéndolos en varias tablas, lo que facilita la consistencia.
- **ACID:** Las bases de datos SQL suelen cumplir con las propiedades ACID (Atomicidad, Consistencia, Aislamiento y Durabilidad), lo que asegura que las transacciones sean procesadas de manera fiable.

### Ejemplos comunes de bases de datos SQL:
- MySQL
- PostgreSQL
- SQLite
- Microsoft SQL Server

## 2. Características de las bases de datos NoSQL

Las bases de datos NoSQL (Not Only SQL) son sistemas de gestión de bases de datos que no siguen el modelo relacional clásico. Están diseñadas para manejar grandes volúmenes de datos, estructuras más flexibles y distribuidas, y cargas de trabajo de alta velocidad.

### Características principales de las bases de datos NoSQL:
- **Escalabilidad horizontal:** A diferencia de las bases de datos SQL, las bases de datos NoSQL pueden escalarse de manera horizontal, es decir, agregando más servidores en lugar de aumentar el poder de un solo servidor.
- **Modelo de datos flexible:** No siguen un esquema rígido, lo que permite almacenar datos no estructurados o semi-estructurados, como documentos, gráficos o pares clave-valor.
- **Desempeño a gran escala:** Las bases de datos NoSQL están optimizadas para manejar grandes volúmenes de datos y operaciones rápidas.
- **Alta disponibilidad:** Muchas bases de datos NoSQL son distribuídas, lo que las hace ideales para entornos donde la alta disponibilidad y la tolerancia a fallos son cruciales.

### Ejemplos comunes de bases de datos NoSQL:
- MongoDB
- Cassandra
- CouchDB
- Redis
- Firebase

## 3. ¿Qué es el formato JSON?

JSON (JavaScript Object Notation) es un formato de intercambio de datos ligero y de fácil lectura/escritura para los humanos. Es un formato de texto que se utiliza ampliamente para transmitir datos entre un servidor y una aplicación web. Se basa en una estructura de objetos y arreglos, y se utiliza tanto en aplicaciones web como en bases de datos NoSQL.

### Características de JSON:
- **Simplicidad:** Es fácil de leer y escribir, lo que lo convierte en una excelente opción para la transferencia de datos.
- **Formato basado en texto:** Es independiente del lenguaje y se puede utilizar en cualquier tecnología que pueda manejar texto.
- **Estructura jerárquica:** Los datos en JSON se organizan en un formato de árbol, con claves y valores (pares de nombre-valor).

### Ejemplo de JSON:
```json
{
  "nombre": "Juan",
  "edad": 30,
  "ciudad": "Madrid",
  "contactos": [
    {
      "tipo": "telefono",
      "numero": "123-456-789"
    },
    {
      "tipo": "email",
      "direccion": "juan@example.com"
    }
  ]
}
```

## 4. Comparativa entre bases de datos SQL y NoSQL

A continuación, se presenta una comparativa entre las bases de datos SQL y NoSQL, considerando sus pros y contras para cada tipo:

| Característica             | Bases de Datos SQL                         | Bases de Datos NoSQL                     |
|----------------------------|--------------------------------------------|------------------------------------------|
| **Modelo de datos**         | Relacional (Tablas y relaciones)           | No relacional (Documentos, clave-valor, etc.) |
| **Escalabilidad**           | Vertical (más poder en un solo servidor)   | Horizontal (más servidores)              |
| **Esquema**                 | Esquema fijo (requiere definición previa)  | Esquema flexible (no requiere un esquema rígido) |
| **Consistencia**            | Alta (propiedades ACID)                   | Eventual (dependiendo de la implementación) |
| **Rendimiento**             | Puede ser más lento con grandes volúmenes de datos | Mejor rendimiento en grandes volúmenes y consultas rápidas |
| **Ideal para**              | Aplicaciones con datos estructurados y relaciones complejas | Aplicaciones con grandes volúmenes de datos, datos no estructurados o en constante cambio |
| **Ejemplos**                | MySQL, PostgreSQL, SQL Server              | MongoDB, Cassandra, CouchDB, Redis       |

### Pros y contras:

- **Bases de Datos SQL:**
  - **Pros:**
    - Integridad de los datos garantizada mediante relaciones.
    - Transacciones ACID que garantizan la fiabilidad.
    - Ideal para aplicaciones con datos bien estructurados y relaciones complejas.
  - **Contras:**
    - Escalabilidad limitada (requiere poder en un solo servidor).
    - Rigidez en el esquema de datos.

- **Bases de Datos NoSQL:**
  - **Pros:**
    - Escalabilidad horizontal y rendimiento optimizado.
    - Flexibilidad en el esquema de datos.
    - Mejor rendimiento con grandes volúmenes de datos.
  - **Contras:**
    - Puede haber falta de consistencia inmediata (según el tipo de base de datos).
    - Menos soporte para transacciones complejas y relaciones entre datos.

## Conclusión

Las bases de datos SQL y NoSQL son adecuadas para diferentes tipos de aplicaciones. Las SQL son ideales para aplicaciones que requieren transacciones complejas y relaciones entre los datos, mientras que las NoSQL son más adecuadas para manejar grandes volúmenes de datos no estructurados, con mayor flexibilidad y escalabilidad. MongoDB, como base de datos NoSQL, se adapta muy bien a aplicaciones modernas que necesitan alta disponibilidad y rapidez en el manejo de datos a gran escala.
