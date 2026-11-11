# Instrucciones para documentar un proyecto en el portal público

Usa estas instrucciones desde el repositorio del proyecto que se va a
documentar. El objetivo es generar documentación pública útil para sus usuarios
y sincronizarla al portal central:

- Repositorio central: `swaplicado/documentacion`
- Directorio destino: `projects/<slug-del-proyecto>/`
- Sitio: `https://swaplicado.github.io/documentacion/`

Reemplaza `<slug-del-proyecto>` con un identificador breve, estable y en
minúsculas, por ejemplo `mi-producto`. No uses un nombre distinto en el
contenido, los enlaces y el workflow.

## Reglas de seguridad y audiencia

1. Distingue la documentación para usuarios de la documentación interna o de
   desarrollo.
2. Solo sincroniza contenido destinado explícitamente a ser público. El portal
   es público y sus archivos se pueden consultar o descargar sin autenticación.
3. Mantén la documentación de desarrollo en el repositorio privado del
   proyecto. No la copies ni la enlaces desde el portal público.
4. Nunca publiques secretos, credenciales, datos personales, configuraciones
   privadas, direcciones internas ni datos de prueba reales.
5. No agregues contraseñas ni tokens a archivos versionados. El token de acceso
   al repositorio central debe guardarse como secreto de GitHub Actions llamado
   `DOCS_REPO_TOKEN`.
6. No hagas `push`, publiques el sitio ni crees o rotes tokens sin autorización
   explícita del usuario.

## Antes de editar

1. Inspecciona la estructura, el README, la documentación existente, las
   pantallas, rutas, mensajes de validación y pruebas pertinentes. Basa las
   instrucciones en comportamientos confirmados en el código; no inventes
   funciones ni prometas comportamientos que no estén implementados.
2. Identifica los usuarios, roles, requisitos previos, tareas frecuentes,
   errores habituales y formas de obtener ayuda.
3. Revisa el portal central y su diseño vigente antes de generar páginas.
   Conserva el layout, navegación y estilos existentes; no agregues otro tema ni
   reescribas CSS compartido por un solo proyecto.
4. Confirma cuál es la rama principal real del repositorio fuente y úsala en el
   workflow. No supongas que se llama `main`.
5. Revisa los cambios ya presentes en el worktree y no los reviertas ni incluyas
   cambios ajenos a esta tarea.

## Archivos esperados

En el repositorio del proyecto:

- Crea o actualiza una guía pública enfocada en el usuario, en una ruta clara
  como `docs/para-usuarios.md`.
- Si existe un changelog destinado a usuarios, úsalo como fuente de las
  novedades; no dupliques ni edites manualmente su contenido generado.
- Conserva la documentación de desarrollo en su ubicación privada actual. Si
  necesita reorganizarse, manténla dentro del repositorio fuente y fuera de la
  lista de publicación.
- Agrega un script pequeño y verificable para generar o copiar los archivos
  públicos al destino del portal.
- Agrega un workflow de GitHub Actions para sincronizar solo esos archivos.
- El generador debe escribir únicamente las páginas públicas del proyecto.
  No debe editar el `index.md` raíz ni insertar tarjetas manuales: la portada
  las genera automáticamente desde `projects/<slug-del-proyecto>/index.md`.
  Si existe una tarjeta manual antigua para el proyecto, elimínala una sola vez.

En `swaplicado/documentacion`:

- Crea `projects/<slug-del-proyecto>/index.md` como página índice con enlaces a
  las páginas públicas del proyecto. Incluye `title` y `description` en el
  front matter: la portada agrega automáticamente a “Explora la documentación”
  cada índice de proyecto; no edites manualmente la lista de tarjetas en
  `index.md` de la raíz.
- Publica cada página como Markdown con metadatos Jekyll, por ejemplo:

  ```yaml
  ---
  title: Guía de usuario
  description: Descripción breve de esta página.
  ---
  ```

- Aplica el diseño existente del portal por medio del layout compartido. No
  crees un layout, una hoja de estilos o una navegación aislada para el
  proyecto, salvo que sea indispensable y se haya acordado.
- Usa enlaces compatibles con el prefijo `/documentacion/`; prefiere enlaces
  Jekyll con `relative_url` cuando se genere HTML o enlaces relativos entre
  páginas Markdown.

## Sincronización automática

El workflow del repositorio fuente debe:

1. Activarse en cambios de la rama principal que afecten únicamente los
   documentos públicos, el generador y el workflow; permitir también una
   ejecución manual.
2. Descargar el repositorio `swaplicado/documentacion` con el secreto
   `DOCS_REPO_TOKEN`.
3. Generar los documentos públicos en `projects/<slug-del-proyecto>/`. No
   modificar el `index.md` raíz del portal ni agregar tarjetas de proyecto.
4. Copiar o actualizar únicamente la lista explícita de archivos públicos.
   No sincronices toda la carpeta `docs/` ni uses una copia recursiva amplia
   sobre documentación que mezcle audiencias.
5. Detectar si no hubo cambios y terminar correctamente sin crear un commit
   vacío.
6. Crear un commit con identidad de `${{ github.actor }}` y publicar el cambio
   a `main` del repositorio central.
7. Usar permisos mínimos: el workflow fuente necesita lectura de su propio
   código; el secreto solo debe tener acceso al repositorio central.

La carpeta pública para cada proyecto debe tener contenido seguro aun si un
workflow se ejecuta por error. Usa una lista permitida explícita de fuentes y
destinos. Evita copiar archivos arbitrarios del repositorio fuente.

## Calidad de la documentación

- Escribe en español claro, orientado a las tareas reales del usuario.
- Organiza la guía con primeros pasos, tareas habituales, preguntas frecuentes
  y solución de problemas cuando el producto lo justifique.
- Usa títulos descriptivos, listas cortas, pasos numerados para procedimientos y
  advertencias junto a la tarea correspondiente.
- Explica nombres de módulos y roles tal como aparecen en la interfaz.
- Añade enlaces entre las páginas del proyecto y a la portada del portal.
- En las novedades, presenta una sección por versión y conserva el orden de
  publicación del changelog fuente.
- No copies README técnico como guía de usuario sin adaptarlo a su audiencia.

## Validación y entrega

Antes de terminar:

1. Ejecuta el generador y verifica que crea todas las páginas esperadas, que
   el índice del nuevo proyecto aparece una sola vez en “Explora la
   documentación” y que el `index.md` raíz no fue modificado.
2. Comprueba que no se genera ni copia documentación de desarrollo, API interna,
   archivos de configuración o secretos.
3. Valida front matter, enlaces locales, sintaxis YAML del workflow y formato
   (`git diff --check`).
4. Ejecuta las pruebas o validaciones relevantes del proyecto.
5. Resume qué documentación se agregó, qué fuentes se publican y qué queda por
   configurar (por ejemplo, el secreto `DOCS_REPO_TOKEN` o Pages).
6. No afirmes que el sitio está publicado hasta confirmar que el workflow de
   Pages terminó correctamente.
