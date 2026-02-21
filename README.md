# Archivium API

Backend del sistema Archivium.
API centralizada para la gestión de contenido cultural (juegos, anime, manga, películas, libros y series).

---

## 📌 Visión del Proyecto

Archivium busca centralizar la gestión de consumo de contenido en un único sistema, eliminando el uso de múltiples archivos Excel y servicios fragmentados.

Para anime y manga:
- Se integrará con la API oficial de MyAnimeList.
- Se permitirá consultar listas y sincronizar información.

Para el resto de contenido:
- Se almacenará en base de datos propia.

---

## 🧠 Problema

- Información distribuida en múltiples Excel.
- Sin trazabilidad.
- Sin centralización.
- Difícil consulta multiplataforma.
- Dependencia de múltiples servicios externos.

---

## 🎯 Usuario Objetivo

- Primario: Propietario del sistema.
- Secundario (futuro): Usuarios interesados en gestionar su consumo de contenido.

---

## 🏗 Stack Tecnológico

- Node.js
- Express + TypeScript
- Prisma ORM
- PostgreSQL
- Docker
- Redis (opcional)
- Nodemailer + Handlebars
- Bun (gestión de paquetes)
- Github Actions (CI/CD)

---

## 🔐 Capacidades MVP

- Autenticación básica de usuario
- CRUD de contenido
- CRUD de reviews
- Consumo de API MyAnimeList
- Persistencia en PostgreSQL

---

## 🚫 Fuera de Alcance MVP

- OAuth
- Dashboard analítico
- Historial avanzado
- Reportes
- Gráficas

---

## 🗄 Modelo Base

Entidades principales:

- User
- Content
- ContentType
- Platform
- Rating
- RefreshToken
- OTP

Relaciones clave:

- User (1) → Content (N)
- User (1) → Rating (N)
- Content (1) → Rating (N)
- ContentType (1) → Content (N)

---

## 🧪 Testing

- Jest
- Supertest
- Cobertura mínima esperada: 80%

Tipos de pruebas:
- Unitarias (servicios)
- Integración (rutas)
- Validación de flujos críticos

---

## 🐳 Docker

Contenedores:
- API
- PostgreSQL
- Redis (opcional)

---

## 🧱 Convenciones de Trabajo

- Ramas por feature
- Rama exclusiva para testing
- No push directo a main
- No merge sin revisión
- Documentación obligatoria con JSDoc
- Entender todo el código utilizado

---

## ⚠ Restricción Personal

IA se usa únicamente para aprendizaje.
No para generación automática de código sin comprensión.