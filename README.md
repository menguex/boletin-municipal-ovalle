# Boletín Informativo — Ilustre Municipalidad de Ovalle

Boletín municipal en dos formatos: **correo HTML** (Outlook) y **página pública** (Vercel).

No es una aplicación web ni un sitio con menús. Es una edición institucional (septiembre 2026) reutilizable para próximos boletines.

## Estructura

```text
├── email/boletin-ovalle.html          Plantilla de correo (tablas, CSS inline)
├── email/boletin-ovalle-final.html    Copia de envío (mismas URLs HTTPS)
├── web/index.html                    Versión de navegador
├── assets/                           Imágenes únicas (logo, noticias, anuncios, interés)
├── vercel.json                       Publicación estática en Vercel
├── CONFIG.md                         WEB_URL e imágenes HTTPS
├── COMO-ENVIAR-OUTLOOK.md            Manual para enviar desde Outlook
├── CHECKLIST-OUTLOOK.md
└── CHECKLIST-ENVIO.md
```

Las fotos originales de trabajo pueden quedar en las carpetas `1. NOTICIAS DESTACADAS`, `2. ANUNCIOS` y `3. NOTICIAS DE INTERÉS`. **Vercel publica solo `assets/` optimizado**, no esas carpetas.

## URL pública

Publicado en Vercel (producción):

```text
WEB_URL=https://boletin-municipal-ovalle.vercel.app
```

- Boletín en el navegador: https://boletin-municipal-ovalle.vercel.app/
- Imágenes: https://boletin-municipal-ovalle.vercel.app/assets/...
- HTML de correo en la web: https://boletin-municipal-ovalle.vercel.app/email/boletin-ovalle-final

No use rutas `file://` ni carpetas de Mac/Windows en el correo.

## GitHub

Repositorio público:

https://github.com/menguex/boletin-municipal-ovalle

Ya está en `main` con remote `origin`. Para publicar cambios:

```bash
cd /Users/osvaldovega/Downloads/boletin-municipal-ovalle-email
git add .
git commit -m "feat: actualizacion del boletin"
git push
```

Si necesita recrear el remoto:

```bash
gh repo create boletin-municipal-ovalle --public --source=. --remote=origin --push
```
## Vercel

Este proyecto **ya está publicado** en:

https://boletin-municipal-ovalle.vercel.app/

El proyecto en el panel es `boletin-municipal-ovalle` (equipo Hobby).

Para actualizar: desde la carpeta del proyecto, con Node en el PATH:

```bash
npx vercel deploy --prod --scope osvaldocrea-6261s-projects
```

O conecte el repositorio de GitHub al mismo proyecto en vercel.com para que cada `git push` a `main` publique solo.

Si crea un proyecto Vercel **nuevo**, anote la URL y reemplácela en `email/` según `CONFIG.md`.

## Dónde está el HTML de Outlook

**Archivo definitivo de envío:** `email/boletin-ovalle-final.html`

Procedimiento: `COMO-ENVIAR-OUTLOOK.md`.

## Cómo actualizar contenido

En `email/boletin-ovalle.html` busque `[EDITAR: FECHA]`, `[EDITAR: NOTICIA PRINCIPAL]`, etc.

Luego copie el archivo a `boletin-ovalle-final.html` o vuelva a generar la copia.

En `web/index.html` actualice los mismos textos e imágenes para que la versión pública coincida.

Imágenes nuevas: reemplazar el archivo en `assets/` (mismo nombre) o actualizar el `src`.

## Cómo preparar un nuevo boletín

1. Cambie fecha, textos y fotos en `web/index.html` y `email/boletin-ovalle.html`.
2. Mantenga colores `#1F6CB1`, `#123A63`, `#F6B824`.
3. Publique (GitHub → Vercel).
4. Reemplace `WEB_URL` si el dominio no cambió, las mismas URLs de `assets/` siguen valiendo.
5. Pruebe en Outlook y envíe.

## Identidad

Azul institucional `#1F6CB1`, azul oscuro `#123A63`, amarillo del logo `#F6B824`. Fuente de correo: Arial, Helvetica, sans-serif.
