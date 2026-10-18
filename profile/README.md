<p align="center">
  <img src="https://raw.githubusercontent.com/Ludexis/.github/main/profile/Ludexis.webp" width="380" alt="Ludexis">
</p>

<p align="center">
  <strong>A self-hosted catalogue for your game archives.</strong><br>
  Point it at your drives and get a searchable library with metadata, artwork and versions, without installing a single game.
</p>

<p align="center">
  <img src="https://raw.githubusercontent.com/Ludexis/Ludexis/main/docs/screenshots/home.webp" alt="Ludexis home page" width="100%">
</p>

### Repositories

| Repository | What it holds |
| ---------- | ------------- |
| [**Ludexis**](https://github.com/Ludexis/Ludexis) | Start here: Docker Compose stack, deployment, documentation and screenshots. Links the two repositories below as submodules. |
| [**ludexis-backend**](https://github.com/Ludexis/ludexis-backend) | FastAPI REST API, library scanner, VNDB / IGDB / Steam metadata providers, Celery workers and Alembic migrations. |
| [**ludexis-frontend**](https://github.com/Ludexis/ludexis-frontend) | Next.js web app: library, game pages, collections, franchises and the admin dashboard. |

### Run it

```bash
curl -O https://raw.githubusercontent.com/Ludexis/Ludexis/main/docker-compose.yml
curl -O https://raw.githubusercontent.com/Ludexis/Ludexis/main/.env.example
mkdir deploy && curl -o deploy/Caddyfile https://raw.githubusercontent.com/Ludexis/Ludexis/main/deploy/Caddyfile
cp .env.example .env    # set GAMES_PATH
docker compose up -d    # then open http://<host>:8420
```

Images: `ghcr.io/ludexis/ludexis-backend` and `ghcr.io/ludexis/ludexis-frontend`, for `amd64` and `arm64`.

### Contribute

Issues and pull requests are welcome in the repository the change belongs to. See the [contributing guide](https://github.com/Ludexis/.github/blob/main/CONTRIBUTING.md).

<p align="center"><sub>Created and maintained by <a href="https://github.com/InvictusRex"><strong>Rupankar Majumdar (@InvictusRex)</strong></a></sub></p>
