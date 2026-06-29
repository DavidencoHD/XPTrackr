# XPTrackr - Frontend

Frontend de **XPTrackr**, una plataforma de seguimiento de biblioteca de videojuegos desarrollada con Angular 19. Permite a los usuarios buscar juegos, gestionar su biblioteca personal, y conectarse con otros jugadores.

## Tecnologías

- **Framework:** Angular 19 (standalone components)
- **Lenguaje:** TypeScript 5.6
- **Estilos:** Tailwind CSS v4.1.5
- **HTTP Client:** Angular HttpClient + Axios
- **Reactividad:** RxJS 7.8

## Características

- **Autenticación** - Registro, login y logout con cookies (Sanctum)
- **Búsqueda de juegos** - Búsqueda en tiempo real integrada en la navbar
- **Detalle de juego** - Página con puntuación Metacritic, géneros, plataformas, screenshots
- **Biblioteca personal** - Añadir juegos con estado (Jugando, Completado, Pendiente, etc.), notas y valoración
- **Sistema de perfil** - Avatar personalizable, edición de datos, cambio de contraseña
- **Sistema de amigos** - Buscar usuarios, enviar/aceptar solicitudes de amistad
- **Próximos lanzamientos** - Carrusel con juegos que salen en la próxima semana
- **Consentimiento de cookies** - Banner GDPR compliant

## Requisitos previos

- [Node.js](https://nodejs.org/) >= 18
- [Angular CLI](https://cli.angular.dev/) >= 19
- Backend XPTrackr corriendo en `http://localhost:8000`

## Instalación

```bash
# Clonar el repositorio
git clone https://github.com/DavidencoHD/XPTrackr.git
cd XPTrackr

# Instalar dependencias
npm install

# Iniciar servidor de desarrollo
ng serve
```

La aplicación estará disponible en `http://localhost:4200`.

## Estructura del proyecto

```
src/
├── app/
│   ├── guards/              # Guards de autenticación
│   ├── services/            # Servicios (auth, games, friends, library)
│   └── shared/components/   # Componentes standalone
│       ├── navbar/          # Barra de navegación con búsqueda
│       ├── footer/          # Pie de página
│       ├── cookie-consent/  # Banner cookies GDPR
│       ├── dashboard/       # Página principal
│       ├── login/           # Formulario de login
│       ├── register/        # Formulario de registro
│       ├── game-search/     # Búsqueda de juegos
│       ├── game-detail/     # Detalle de juego
│       ├── next-games/      # Carrusel de próximos lanzamientos
│       ├── profile-view/    # Visualización de perfil
│       ├── profile-edit/    # Edición de perfil
│       └── friends/         # Sistema de amigos
├── environments/            # Configuración de entornos
└── assets/                  # Imágenes y recursos estáticos
```

## Rutas

| Ruta | Descripción | Auth |
|------|-------------|------|
| `/dashboard` | Página principal | No |
| `/login` | Iniciar sesión | No |
| `/register` | Registrarse | No |
| `/profile` | Mi perfil | Sí |
| `/profile/edit` | Editar perfil | Sí |
| `/profile/:userId` | Ver perfil de otro usuario | No |
| `/games/:id` | Detalle de juego | No |
| `/friends` | Sistema de amigos | Sí |

## Comandos útiles

```bash
ng serve              # Iniciar servidor de desarrollo
ng build              # Generar build de producción
ng test               # Ejecutar tests unitarios
ng lint               # Verificar código con linter
```

## Variables de entorno

El archivo `src/environments/environment.ts` contiene la URL del backend:

```typescript
export const environment = {
  production: true,
  apiUrl: 'http://localhost:8000/api'
};
```

## Backend

El backend de este proyecto está disponible en [XPTrackrBackend](https://github.com/DavidencoHD/XPTrackrBackend).
