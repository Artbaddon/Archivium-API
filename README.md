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

## 📁 Estructura de Carpetas

```
src/
├── modules/                    # Módulos de la aplicación (por feature)
│   ├── auth/
│   ├── users/
│   ├── content/
│   ├── ratings/
│   ├── myAnimeList/
│   └── [module-name]/
│       ├── controllers/        # Controladores (rutas y manejo de requests)
│       ├── services/           # Lógica de negocio
│       ├── repositories/       # Acceso a datos (Prisma queries)
│       ├── dtos/               # Data Transfer Objects (validación)
│       ├── types/              # Tipos/interfaces del módulo
│
├── config/                     # Configuraciones iniciales
│   ├── database.ts             # Configuración de Prisma/PostgreSQL
│   ├── env.ts                  # Variables de entorno
│   ├── constants.ts            # Constantes globales
│   └── [config-name].ts
│
├── middlewares/                # Middlewares globales
│   ├── auth.ts
│   ├── errorHandler.ts
│   ├── validation.ts
│   └── [middleware-name].ts
│
├── utils/                      # Utilidades compartidas (a nivel de raíz)
│   ├── decorators/
│   ├── errors/
│   ├── validators/
│   ├── helpers/
│   └── [utility-name].ts
│
├── types/                      # Tipos/interfaces compartidas
│   ├── index.ts
│   └── [type-file].ts
│
├── templates/                  # Templates para emails (Handlebars)
│   ├── welcome.hbs
│   ├── resetPassword.hbs
│   ├── otp.hbs
│   └── [email-template].hbs
│
├── prisma/                     # Carpeta generada/gestionada por Prisma
│   ├── schema.prisma           # Definición del esquema de BD
│   └── migrations/             # Historial de migraciones
│
├── app.ts                      # Configuración principal de Express
├── main.ts                     # Punto de entrada
└── server.ts                   # Instancia del servidor
```

**Notas sobre la organización:**

- **Módulos**: Cada feature (auth, users, content, ratings, etc.) es un módulo independiente
- **Controllers**: Manejan las rutas y requests HTTP
- **Services**: Contienen la lógica de negocio
- **Repositories**: Abstracción para queries a BD (Prisma)
- **DTOs**: Validación y transformación de datos
- **Types**: Tipos compartidos a nivel de proyecto, tipos específicos en módulos
- **Utils**: Funciones genéricas reutilizables (error handling, validators, decorators, etc.)
- **Config**: Conexiones, variables de entorno, constantes
- **Templates**: Email templates con Handlebars para Nodemailer

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
