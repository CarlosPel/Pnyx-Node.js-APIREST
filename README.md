# Pnyx-Node.js-APIREST

API RESTful desarrollada en Node.js y Express para la red social PNYX. Gestiona usuarios, publicaciones, comentarios, noticias y relaciones de seguimiento, utilizando una base de datos PostgreSQL.

## Características

- Registro e inicio de sesión de usuarios con autenticación JWT.
- Gestión de perfiles de usuario y edición de datos.
- Creación, consulta, guardado y filtrado de publicaciones (posts).
- Comentarios en publicaciones.
- Seguimiento y dejar de seguir a otros usuarios.
- Consulta y guardado de noticias externas mediante integración con RapidAPI.
- Filtros por temas, país y fecha.
- Protección de rutas mediante middleware de autenticación.
- Conexión a base de datos PostgreSQL.

## Estructura del proyecto

- `server.js`: Punto de entrada de la API.
- `config/db.js`: Configuración y conexión a la base de datos PostgreSQL.
- `controllers/`: Lógica de negocio para usuarios, posts y noticias.
- `middlewares/auth.js`: Middleware para autenticación y generación de tokens.
- `routes/`: Definición de rutas para usuarios, posts y noticias.

## Instalación

1. Clona este repositorio:
   ```sh
   git clone https://github.com/tuusuario/pnyx-nodejs-apirest.git
   cd pnyx-nodejs-apirest
   ```

2. Instala las dependencias:
   ```sh
   npm install
   ```

3. Configura las variables de entorno en un archivo `.env`:
   ```
   DB_USER=tu_usuario
   DB_PASSWORD=tu_contraseña
   DB_HOST=localhost
   DB_PORT=5432
   DB_NAME=pnyx
   SERVER_PORT=5000
   JWT_SECRET=tu_clave_secreta
   NEWS_API_RAPIDAPI_KEY=tu_clave_rapidapi
   ```

4. Inicia el servidor:
   ```sh
   npm start
   ```
   El servidor estará disponible en `http://localhost:5000`.

## Endpoints principales

- **Usuarios**
  - `POST /users/register`: Registro de usuario
  - `POST /users/login`: Inicio de sesión
  - `POST /users/editProfile`: Editar perfil (requiere autenticación)
  - `POST /users/follow`: Seguir usuario (requiere autenticación)
  - `POST /users/unfollow`: Dejar de seguir usuario (requiere autenticación)
  - `POST /users/savedposts`: Obtener posts guardados (requiere autenticación)

- **Posts**
  - `POST /posts/create`: Crear post (requiere autenticación)
  - `POST /posts/get`: Obtener posts (requiere autenticación)
  - `POST /posts/comments`: Obtener comentarios de un post
  - `POST /posts/save`: Guardar post (requiere autenticación)
  - `POST /posts/unsave`: Eliminar post guardado (requiere autenticación)
  - `POST /posts/getpostsbytopic`: Obtener posts por tema

- **Noticias**
  - `POST /news/get`: Obtener noticias externas

## Autenticación

La mayoría de los endpoints requieren autenticación mediante JWT. Envía el token en el header:
```
Authorization: Bearer <token>
```

## Contribución

¡Las contribuciones son bienvenidas! Abre un issue o pull request para sugerir mejoras o reportar errores.

## Licencia

Este proyecto está bajo la licencia MIT.

---

Desarrollado por Miguel Ceada y Carlos Sánchez.