# FrontendIVD

Aplicación web del **Instituto Veracruzano del Deporte (IVD)** — plataforma de gestión de atletas, entrenadores, clubes, eventos y resultados deportivos del estado de Veracruz.

Backend de este proyecto: [BackendIVD](https://github.com/IVD2025/BackendIVD)

## Tecnologías

- **React** con **Vite**
- **Material UI (MUI)** como librería principal de componentes
- **React Router** para la navegación
- **Axios** para las peticiones a la API
- **Supabase** (autenticación de sesión)
- **jsPDF** / **xlsx** para generación de reportes en PDF y Excel
- **SweetAlert2** para alertas y confirmaciones
- **Leaflet** para mapas (ubicación de clubes)

## Estructura del proyecto
src/
├── api/ # Configuración de Axios y funciones de conexión con el backend
├── components/
│ ├── common/ # Contexto de autenticación, componentes compartidos
│ └── layout/ # Encabezados y pie de página por rol
├── features/
│ ├── admin/ # Panel de administrador
│ ├── atleta/ # Panel de atleta
│ ├── auth/ # Login, registro, recuperación de contraseña
│ ├── club/ # Panel de club
│ └── entrenador/ # Panel de entrenador
├── pages/ # Páginas principales por rol y páginas públicas
└── App.jsx # Definición de rutas de la aplicación


## Roles del sistema

La plataforma tiene 5 tipos de acceso, cada uno con su propio panel:

- **Público** — sin necesidad de cuenta: consulta de eventos y resultados.
- **Atleta** — inscripción a convocatorias, consulta de resultados propios, gestión de club.
- **Entrenador** — consulta de eventos, reportes de sus atletas.
- **Club** — gestión de su plantilla de atletas y entrenadores, inscripciones, reportes.
- **Administrador** — gestión completa de usuarios, clubes, eventos, resultados y contenido institucional.

## Instalación local

1. Clona el repositorio e instala las dependencias:
```bash
   git clone https://github.com/IVD2025/FrontendIVD2.git
   cd FrontendIVD2
   npm install
```

2. Crea un archivo `.env` en la raíz con la URL del backend:

```env
   VITE_API_URL=http://localhost:5000/api
```

   Para conectarte al backend ya desplegado en vez de uno local, usa en su lugar:
```env
   VITE_API_URL=https://backendivd-mbok.onrender.com/api
```

   > ⚠️ El archivo `.env` nunca debe subirse al repositorio.

3. Levanta el proyecto en modo desarrollo:
```bash
   npm run dev
```

   Por defecto corre en `http://localhost:5173`.

4. Para generar la versión de producción:
```bash
   npm run build
```
   Los archivos listos para desplegar quedan en la carpeta `dist/`.

## Despliegue

El frontend está desplegado en **[Vercel](https://vercel.com)**, conectado directamente a este repositorio (rama `main`). Cualquier cambio subido a `main` se despliega automáticamente.

La variable `VITE_API_URL` se configura en el dashboard de Vercel, en **Settings → Environment Variables**, apuntando a la URL del backend en Render.

---
Proyecto desarrollado para el **Instituto Veracruzano del Deporte**.