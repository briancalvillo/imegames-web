# IME Games · web

Web estática de [imegames.com](https://imegames.com): portada con los juegos, página de Chip Beat,
su política de privacidad y `app-ads.txt` de AdMob.

Todo lo que se publica está en `public/` (HTML y CSS sin compilación).

| Ruta | Contenido |
|---|---|
| `/` | Portada de IME Games: juegos educativos (Independitza't, Primer contracte y Taller tècnic) y otros juegos |
| `/chipbeat/` | Página de Chip Beat |
| `/chipbeat/privacidad.html` | Política de privacidad de Chip Beat (URL para Google Play) |
| `/app-ads.txt` | Verificación de AdMob |

## Servidor

Un contenedor nginx propio (`docker-compose.yml`) sirve `public/` en `127.0.0.1:8082`, y el Caddy común
(`/opt/projects/caddy`) hace de proxy con HTTPS para `imegames.com` (bloques en `Caddyfile.ejemplo`).

### Puesta en marcha (una vez)

```bash
git clone https://github.com/briancalvillo/imegames-web.git /opt/projects/imegames-web
cd /opt/projects/imegames-web && docker compose up -d
# Añadir Caddyfile.ejemplo al final de /opt/projects/caddy/Caddyfile y recargar:
docker exec caddy caddy reload --config /etc/caddy/Caddyfile
```

### Actualizar

```bash
cd /opt/projects/imegames-web && git pull
```

No hace falta reiniciar nada: nginx lee `public/` directamente.
