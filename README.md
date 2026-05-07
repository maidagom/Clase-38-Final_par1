# Proyecto Backend - Clase 38

Este proyecto es una API RESTful construida con Node.js y Express para la gestión de usuarios, utilizando MongoDB como base de datos.

## 🚀 Tecnologías Utilizadas

- **Node.js**: Entorno de ejecución para JavaScript.
- **Express**: Framework web para Node.js.
- **MongoDB & Mongoose**: Base de datos NoSQL y ODM para el modelado de datos.
- **JWT (JSON Web Token)**: Autenticación basada en tokens.
- **Bcryptjs**: Encriptación de contraseñas.
- **CORS**: Middleware para habilitar el intercambio de recursos de origen cruzado.
- **Dotenv**: Manejo de variables de entorno.

## 📂 Estructura del Proyecto

```text
Back-end/
├── config/             # Configuración de la base de datos
├── controladores/      # Lógica de los endpoints
├── modelos/            # Esquemas de Mongoose
├── rutas/              # Definición de rutas de la API
├── server.js           # Punto de entrada del servidor
└── vercel.json         # Configuración para despliegue en Vercel
```

## 🛠️ Instalación y Configuración

1. Navega a la carpeta del backend:
   ```bash
   cd Back-end
   ```

2. Instala las dependencias:
   ```bash
   npm install
   ```

3. Configura las variables de entorno:
   Crea un archivo `.env` en la raíz de `Back-end/` y añade:
   ```env
   JWT_SECRET=tu_clave_super_segura
   ```

4. Inicia el servidor en modo desarrollo:
   ```bash
   npm run dev
   ```
   El servidor se ejecutará en `http://localhost:3000`.

## 🛣️ Endpoints de la API

El servidor utiliza el prefijo `/users` para todas las rutas de usuarios.

| Método | Ruta | Descripción |
|--------|------|-------------|
| `POST` | `/users/login` | Autenticación de usuario |
| `GET` | `/users/` | Obtener lista de usuarios (soporta paginación y búsqueda) |
| `GET` | `/users/:posicion` | Obtener un usuario por ID o nombre de usuario |
| `POST` | `/users/` | Crear un nuevo usuario |
| `PUT` | `/users/:posicion` | Actualizar un usuario existente |
| `DELETE` | `/users/:posicion` | Eliminar un usuario |

### Funcionalidades destacadas:
- **Paginación y Búsqueda**: El endpoint `GET /users/` acepta parámetros de consulta como `pagina`, `limite` y `busqueda`.
- **Seguridad**: Las contraseñas se almacenan encriptadas mediante un middleware de Mongoose (`pre-save`).
- **Validación**: Comprobación de unicidad para correos electrónicos y nombres de usuario durante la creación y actualización
  
