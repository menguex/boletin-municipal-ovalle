# Configuración de URLs

Valores reales de esta publicación (Vercel, producción):

```text
WEB_URL=https://boletin-municipal-ovalle.vercel.app
```

Sin barra final.

## Qué abre cada URL

| Recurso | URL |
|---|---|
| Boletín web | https://boletin-municipal-ovalle.vercel.app/ |
| Versión en `/web` | https://boletin-municipal-ovalle.vercel.app/web |
| HTML de correo (publicado) | https://boletin-municipal-ovalle.vercel.app/email/boletin-ovalle-final |
| Logo | https://boletin-municipal-ovalle.vercel.app/assets/logo/logo-ovalle.png |

## Imágenes del email

Deben ser exactamente:

```text
https://boletin-municipal-ovalle.vercel.app/assets/logo/logo-ovalle.png
https://boletin-municipal-ovalle.vercel.app/assets/noticias/...
https://boletin-municipal-ovalle.vercel.app/assets/anuncios/...
https://boletin-municipal-ovalle.vercel.app/assets/interes/...
```

Si cambia el dominio de Vercel, reemplace en los HTML de `email/` todas las ocurrencias de:

```text
https://boletin-municipal-ovalle.vercel.app
```
