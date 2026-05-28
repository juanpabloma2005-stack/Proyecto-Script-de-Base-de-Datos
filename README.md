# Sistema de Gestión de Biblioteca - Base de Datos Relacional

Este proyecto contiene el diseño e implementación del esquema de base de datos relacional para un sistema de gestión de biblioteca utilizando **PostgreSQL**. Incluye la creación de tablas, restricciones de integridad, inserción de datos iniciales y un set completo de consultas SQL para auditoría y reportes.

## ⚙️ Tecnologías Utilizadas
* **Motor de Base de Datos:** PostgreSQL
* **Lenguaje:** SQL (DDL y DML)

## 🗄️ Estructura del Modelo Relacional
El esquema de datos está compuesto por las siguientes entidades principales y sus relaciones:
* **categoria:** Clasificación temática de los libros (`Novela`, `Ciencia`, etc.).
* **autor:** Información sobre los escritores (Nombre, país de origen, fecha de nacimiento).
* **libro:** Datos de las obras publicadas. Relacionado con *Categoría* (1:N) y con *Autor* a través de la tabla intermedia de ruptura (N:M).
* **libro_autor:** Tabla asociativa para resolver la relación muchos a muchos entre libros y autores.
* **usuario:** Registro de miembros autorizados de la biblioteca con sus datos de contacto.
* **prestamo:** Cabecera de las transacciones de préstamo que asocia un usuario con una fecha de salida y devolución.
* **detalle_prestamo:** Líneas de detalle asociadas a un préstamo, permitiendo registrar múltiples libros y sus cantidades por transacción.

---

## 🚀 Instalación y Uso

1. Conéctate a tu servidor de PostgreSQL mediante tu CLI favorita o interfaz gráfica (pgAdmin, DBeaver, etc.).
2. Crea una base de datos limpia para el proyecto:
```sql
   CREATE DATABASE biblioteca;