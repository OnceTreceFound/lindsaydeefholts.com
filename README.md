# lindsaydeefholts.com

Sitio estático (HTML/CSS/JS) alojado en SiteGround y publicado desde GitHub.

## Cómo se trabaja
- `main` = lo que está publicado en https://lindsaydeefholts.com. Cada push a `main` se copia solo al servidor (GitHub Actions → SiteGround por SSH) y se limpia la caché.
- `vista-previa` = lo que se ve en https://lindsaydeefholts.com/vista-previa/ (no indexado). Sirve para mostrar cambios antes de publicarlos.
- Flujo: mostrar en vista previa → aprobación de Elias → push a `main`.
- Nunca se sube nada por el administrador de archivos de SiteGround ni se borra nada del servidor.

## Configuración en GitHub (una sola vez)
Settings → Secrets and variables → Actions → New repository secret:
- `SG_SSH_KEY`: la llave privada "githubpublicar" (la misma que usa oncetrece.org).
- `SG_SSH_PASS` (opcional): solo si la llave tiene contraseña.

En SiteGround (Site Tools de lindsaydeefholts.com → Devs → SSH Keys Manager) debe estar importada la llave pública "githubpublicar". Usuario SSH del sitio: `u235-bz5tvygj6lhb`, host `ssh.lindsaydeefholts.com`, puerto 18765 (ya configurados en los workflows).

