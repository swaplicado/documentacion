# Documentación pública de Swaplicado

Este repositorio reúne la documentación pública de usuario de varios
proyectos. GitHub Pages publica el contenido de este repositorio; todo lo que
se agregue aquí debe considerarse público.

## Proyectos

La portada del sitio lista automáticamente los proyectos que tienen una página
`projects/<proyecto>/index.md`.

## Agregar un proyecto

1. Crea `projects/<proyecto>/index.md` con `title` y `description` en el
   front matter; el proyecto aparecerá automáticamente en la portada.
2. En el repositorio fuente, mantén los documentos públicos en una lista
   permitida explícita. No sincronices la carpeta completa de documentación
   del proyecto.
3. Configura un secreto `DOCS_REPO_TOKEN` en el repositorio fuente. El token
   debe tener acceso de escritura únicamente a este repositorio.
4. Agrega un flujo de GitHub Actions para copiar solo los documentos de usuario
   al directorio del proyecto y enviar el cambio a la rama `main`.

Los documentos de desarrollo deben permanecer en repositorios privados. No
incluyas credenciales, secretos ni información que no deba ser pública.

## Configuración inicial de Pages

En **Settings → Pages**, selecciona **GitHub Actions** como origen de
publicación. El sitio se publica en cada cambio a `main`.
