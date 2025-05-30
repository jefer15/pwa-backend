# PWA Backend

## Descripción del Proyecto
Este proyecto es el backend para una Progressive Web Application (PWA) desarrollado con NestJS. Proporciona una API RESTful robusta con soporte para operaciones offline/online, autenticación JWT, y persistencia de datos utilizando PostgreSQL.

## Requisitos Previos
- Node.js (v18.x o superior)
- PostgreSQL (v14.x o superior)
- npm (v9.x o superior)

## Instalación

1. Clonar el repositorio:
bash
git clone [URL_DEL_REPOSITORIO]
cd pwa-backend


2. Instalar dependencias:
bash
npm install


3. Configurar variables de entorno:
Crear un archivo .env en la raíz del proyecto con las siguientes variables:
env
DATABASE_HOST=localhost
DATABASE_PORT=5432
DATABASE_USERNAME=tu_usuario
DATABASE_PASSWORD=tu_contraseña
DATABASE_NAME=tu_base_de_datos
JWT_SECRET=tu_secreto_jwt


## Ejecución del Proyecto

### Desarrollo
bash
npm run start:dev


### Producción
bash
npm run build
npm run start:prod


### Debug
bash
npm run start:debug


## Tecnologías Utilizadas

### Framework y Core
- *NestJS (v11.0.1)*: Framework progresivo de Node.js para construir aplicaciones del lado del servidor escalables y eficientes.
- *TypeScript*: Proporciona tipado estático y características modernas de JavaScript.

### Base de Datos y ORM
- *TypeORM (v0.3.24)*: ORM que facilita la interacción con la base de datos PostgreSQL.
- *PostgreSQL (v8.16.0)*: Sistema de gestión de base de datos relacional robusto y confiable.

### Autenticación y Seguridad
- *Passport.js*: Middleware de autenticación para Node.js.
- *JWT (JSON Web Tokens)*: Implementación de tokens para autenticación stateless.
- *bcrypt*: Para el hash seguro de contraseñas.

### Validación y Transformación
- *class-validator*: Para validación de DTOs.
- *class-transformer*: Para transformación de objetos.

## Implementación de Sincronización Offline/Online

### Estrategia de Sincronización
1. *Almacenamiento Local*:
   - Utilización de IndexedDB para almacenamiento offline
   - Implementación de cola de operaciones pendientes

2. *Políticas de Reintento*:
   - Reintentos exponenciales para operaciones fallidas
   - Máximo de 3 intentos por operación
   - Tiempo de espera entre reintentos: 1s, 2s, 4s

3. *Manejo de Conflictos*:
   - Estrategia "Last Write Wins" para resolución de conflictos
   - Timestamps para tracking de modificaciones
   - Versionado de registros

### Detalles Técnicos

#### Almacenamiento
- *IndexedDB*: Para almacenamiento de datos offline
- *Local Storage*: Para configuración y metadatos
- *Session Storage*: Para datos temporales de sesión

#### Manejo de Errores
- Interceptores globales para manejo de errores
- Logging estructurado de errores
- Respuestas HTTP estandarizadas

#### Optimizaciones
- Caché de consultas frecuentes
- Compresión de respuestas
- Paginación de resultados

## Scripts Disponibles

- npm run build: Compila el proyecto
- npm run format: Formatea el código usando Prettier
- npm run start: Inicia el servidor
- npm run start:dev: Inicia el servidor en modo desarrollo con hot-reload
- npm run start:debug: Inicia el servidor en modo debug
- npm run start:prod: Inicia el servidor en modo producción
- npm run lint: Ejecuta el linter
- npm run test: Ejecuta las pruebas unitarias
- npm run test:e2e: Ejecuta las pruebas end-to-end

## Estructura del Proyecto

src/
├── auth/           # Módulo de autenticación
├── users/          # Módulo de usuarios
├── task/           # Módulo de tareas
├── config/         # Configuración de la aplicación
└── main.ts         # Punto de entrada de la aplicación


## Contribución
1. Fork el proyecto
2. Crea tu rama de características (git checkout -b feature/AmazingFeature)
3. Commit tus cambios (git commit -m 'Add some AmazingFeature')
4. Push a la rama (git push origin feature/AmazingFeature)
5. Abre un Pull Request

## Licencia
Este proyecto es privado y no licenciado.