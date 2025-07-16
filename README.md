# Asociación Sanjuanina de Nutrición

Este proyecto es una plataforma web para la gestión de la Asociación Sanjuanina de Nutrición. Incluye un backend robusto en PHP (CodeIgniter 4) y un frontend moderno desarrollado con Astro y React.

## Tabla de Contenidos

- [Descripción General](#descripción-general)
- [Estructura del Proyecto](#estructura-del-proyecto)
- [Tecnologías Utilizadas](#tecnologías-utilizadas)
- [Funcionalidades Principales](#funcionalidades-principales)
- [Arquitectura y Comunicación](#arquitectura-y-comunicación)
- [Instalación y Configuración](#instalación-y-configuración)
- [Configuración de Base de Datos](#configuración-de-base-de-datos)
- [API Backend: Endpoints Principales](#api-backend-endpoints-principales)
- [Frontend: Rutas y Páginas](#frontend-rutas-y-páginas)
- [Créditos](#créditos)

---

## Descripción General

Plataforma para la gestión de socios, pagos, usuarios y administración de la Asociación Sanjuanina de Nutrición. Permite a los usuarios asociarse, acceder a beneficios, gestionar pagos y a los administradores controlar la información y actividades de la asociación.

## Estructura del Proyecto

```
Asociacion/
  ├── Back_asn/      # Backend (API REST, CodeIgniter 4)
  └── Front_asn/     # Frontend (Astro + React)
```

## Tecnologías Utilizadas

- **Backend:** PHP 8.1+, CodeIgniter 4, MySQL/MariaDB
- **Frontend:** Astro, React, TailwindCSS
- **Otros:** Composer, Node.js, npm

## Funcionalidades Principales

- Registro y autenticación de usuarios (con token de acceso)
- Gestión de socios y usuarios
- Gestión de pagos y reportes
- Panel de administración con estadísticas y actividades
- Páginas informativas y formulario de contacto

## Arquitectura y Comunicación

- **Frontend** consume la **API REST** del backend para autenticación, gestión de usuarios, pagos, etc.
- Comunicación vía HTTP (fetch/AJAX) usando tokens de acceso.
- El backend valida roles y permisos (usuarios, admin).

## Instalación y Configuración

### Backend (Back_asn)

1. Instala dependencias:
   ```bash
   cd Back_asn
   composer install
   ```
2. Copia el archivo `.env` y configura los parámetros (baseURL, base de datos, etc.):
   ```bash
   cp env .env
   # Edita .env según tu entorno
   ```
3. Configura tu servidor web para que apunte a `Back_asn/public`.
4. Asegúrate de tener PHP 8.1+ y las extensiones requeridas (`intl`, `mbstring`, `json`, `mysqli`).
5. Crea la base de datos `asn` y configura el usuario en `app/Config/Database.php`.
6. Ejecuta migraciones y seeders si es necesario.

### Frontend (Front_asn)

1. Instala dependencias:
   ```bash
   cd Front_asn
   npm install
   ```
2. Configura variables de entorno en `src/config/env.ts` si es necesario (por ejemplo, la URL de la API).
3. Inicia el servidor de desarrollo:
   ```bash
   npm run dev
   ```

## Configuración de Base de Datos

- **Tipo:** MySQL/MariaDB
- **Host:** 127.0.0.1
- **Puerto:** 3307 (puede variar)
- **Base de datos:** asn
- **Usuario:** root (modificar según tu entorno)
- Configura estos datos en `Back_asn/app/Config/Database.php`.

## API Backend: Endpoints Principales

- `POST /api/login` — Iniciar sesión y obtener token
- `GET /api/users` — Listar usuarios (requiere token)
- `POST /api/users` — Crear usuario (requiere token)
- `GET /api/test` — Endpoint público de prueba
- `GET /api/test/protected` — Endpoint protegido (requiere autenticación)
- `GET /api/test/adminOnly` — Solo para administradores

## Frontend: Rutas y Páginas

- `/` — Página principal, bienvenida y servicios
- `/login` — Inicio de sesión
- `/dashboard` — Panel de usuario autenticado
- `/admin` — Panel de administración (usuarios, socios, pagos, reportes, configuración)
- `/asociate` — Formulario para asociarse
- `/conocenos` — Información sobre la asociación
- `/contacto` — Formulario de contacto
- `/honorarios` — Información de honorarios mínimos
- `/pago-cuota` — Gestión de pagos
- `/covid-19` — Información relevante sobre COVID-19
- `/test` — Página de pruebas

## Créditos

- Proyecto desarrollado por la Asociación Sanjuanina de Nutrición.
- Backend basado en CodeIgniter 4.
- Frontend desarrollado con Astro y React.

---

Para más información, consulta los README específicos en `Back_asn/` y `Front_asn/` o contacta a los administradores del repositorio.
