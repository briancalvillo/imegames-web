# IME Games · web

Web estática de [imegames.com](https://imegames.com): portada con los juegos, página de Chip Beat,
su política de privacidad y `app-ads.txt` de AdMob.

Todo lo que se publica está en `public/` (HTML y CSS sin compilación).

| Ruta | Contenido |
|---|---|
| `/` | Portada de IME Games |
| `/chipbeat/` | Página de Chip Beat |
| `/chipbeat/privacidad.html` | Política de privacidad de Chip Beat (URL para Google Play) |
| `/app-ads.txt` | Verificación de AdMob |

## Puesta en marcha en el servidor (una vez)

```bash
sudo git clone https://github.com/briancalvillo/imegames-web.git /var/www/imegames-web
# Añadir el bloque de Caddyfile.ejemplo a /etc/caddy/Caddyfile
sudo systemctl reload caddy
```

## Actualizar

```bash
cd /var/www/imegames-web && sudo git pull
```

No hace falta recargar Caddy: sirve los ficheros directamente.
