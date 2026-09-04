# Cómo enviar el boletín en Microsoft Outlook

Esta guía es para quien envía el correo, sin necesidad de programar.

## 1. Obtener el HTML final

El archivo listo para enviar es:

**`email/boletin-ovalle-final.html`**

Ábralo en un editor de texto solo para comprobar. No lo “convierta” a Word.

Antes de enviar, el archivo debe contener `https://` y el dominio de Vercel (no la palabra `WEB_URL`).

---

## 2. Comprobar que las imágenes están en HTTPS

1. Abra el HTML final.
2. Busque `src="`.
3. Cada imagen debe empezar por `https://` y su dominio de Vercel, por ejemplo:

   `https://SU-PROYECTO.vercel.app/assets/logo/logo-ovalle.png`

4. Copie esa dirección, péguela en el navegador y verifique que la foto aparece.

Si ve `file://`, `C:\`, `/Users/` o `src="assets/` **no envíe**. Faltó publicar en Vercel o reemplazar `WEB_URL`.

---

## 3. Probar el boletín en el navegador

Abra en Chrome o Edge:

- la URL pública de Vercel (versión web), y
- `https://SU-PROYECTO.vercel.app/email/boletin-ovalle-final.html` (versión de correo, si la publicó).

Revise textos, fotos y el botón **VER BOLETÍN EN EL NAVEGADOR**.

---

## 4. Cargar el HTML en Outlook (importante)

Outlook de escritorio en Windows usa el motor de Word. **Copiar desde Chrome y pegar en un mensaje nuevo suele romper tablas, anchos e imágenes.**

### Opción A — Outlook clásico para Windows (recomendada si está disponible)

1. Abra Outlook.
2. Mensaje nuevo.
3. Según la versión:
   - pestaña **Insertar** → **Adjuntar archivo** no sirve para el cuerpo;
   - lo correcto suele ser abrir el HTML como contenido del mensaje.
4. En muchas instalaciones: **Archivo → Abrir y exportar → Abrir** no aplica al correo.
5. Método fiable en Outlook clásico:
   - cierre Outlook;
   - haga clic derecho en `boletin-ovalle-final.html` → **Abrir con** → Outlook (si aparece);
   - o, en un mensaje: pestaña **Insertar** → **Elemento de Outlook** no aplica.
6. Método usado en equipos municipales:
   - cree un mensaje nuevo;
   - pestaña **Insertar**;
   - en grupos antiguos: **Adjuntar** no;
   - use **Archivo → Opciones** no.

**Método práctico que sí funciona en la mayoría de Outlook clásico de Windows:**

1. Abra `boletin-ovalle-final.html` con **Internet Explorer** o el modo IE (si el equipo aún lo tiene), o con **Microsoft Edge en modo IE** si está habilitado.
2. `Ctrl + A` para seleccionar todo.
3. `Ctrl + C` para copiar.
4. En el mensaje de Outlook, haga clic en el cuerpo y `Ctrl + V`.

Si el equipo **no** tiene IE, no use Chrome para copiar: el resultado casi nunca coincide.

**Método más seguro (recomendado para producción):**

Use un envío desde una plataforma de correo institucional que acepte **HTML fuente** (código), no “diseño visual”. Ejemplos habituales en municipios: módulo de newsletter, Mailchimp, Brevo, o el sistema de comunicaciones. Allí se pega el **código HTML** completo (abrir el archivo con Bloc de notas, seleccionar todo, copiar, pegar en “código fuente” o “HTML”).

### Opción B — Outlook para Microsoft 365 (nuevo) y Outlook para Mac

El Outlook “nuevo” y el de Mac **no pegan HTML de correo de forma fiable**.

Haga esto:

1. Envíe una **prueba** desde una herramienta que inyecte HTML, **o**
2. Pida a informática que use PowerShell / un conector SMTP institucional, **o**
3. Use “Insertar” solo si su versión muestra **Insertar → Texto → Adjuntar archivo como texto** y luego no: eso pegaría código visible.

**Resumen:** si su Outlook no tiene “código fuente HTML” en el mensaje, no intente reconstruir el diseño a mano. Use una plataforma de envío o pida apoyo de informática.

### Opción C — Gmail (para prueba, no sustituye Outlook)

Gmail tampoco garantiza el mismo aspecto que Outlook. Sirve como segunda prueba, no como aprobación final municipal.

---

## 5. Correo de prueba

1. Asunto de prueba, por ejemplo: `[PRUEBA] Boletín informativo — septiembre 2026`.
2. Envíese el mensaje a **su propia casilla Outlook**.
3. Ábralo en el **mismo Outlook de escritorio** que usarán los destinatarios, no solo en el celular.
4. Active “Descargar imágenes” si Outlook las bloquea.

---

## 6. Qué revisar en la prueba

- Logo nítido, sin fondo negro.
- Fotos completas, no aplastadas.
- Botones **LEER NOTICIA** abren las noticias de muniovalle.gob.cl.
- **VER BOLETÍN EN EL NAVEGADOR** abre la URL de Vercel.
- No hay scroll horizontal.
- El pie muestra Municipalidad de Ovalle y muniovalle.gob.cl.

Marque `CHECKLIST-ENVIO.md`.

---

## 7. Envío definitivo

1. Quite la palabra PRUEBA del asunto.
2. Asunto sugerido: `Boletín informativo municipal — septiembre 2026`.
3. Remitente institucional (cuenta del municipio, no una casilla personal).
4. Destinatarios según el protocolo interno (lista, CCO, etc.).
5. Envíe solo cuando el checklist esté completo.

---

## Limitaciones de Outlook (léalas)

- No ejecuta JavaScript (este boletín no lo usa).
- Ignora gran parte del CSS moderno; por eso el correo va en **tablas**.
- A veces bloquea imágenes hasta que el usuario las permite.
- Puede recortar mensajes muy pesados; las fotos de este boletín están comprimidas.
- Word (motor de Outlook clásico) interpreta mal Flexbox y Grid: no se usan en el HTML de correo.
- Pegar desde el navegador **no** es un método de producción.

Si la prueba en Outlook se ve mal, el problema casi nunca se “arregla” reenviando el mismo pegado. Hay que enviar el **archivo HTML** por una vía que conserve el código.
