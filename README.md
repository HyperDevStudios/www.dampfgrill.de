# www.dampfgrill.de

## Docker-based web server

The project now includes a Docker Compose configuration that exposes the Nginx
static web server on port **85**. This port is designed to sit behind the
upstream reverse proxy that publishes the site on ports 80 and 443.

### Neue Seiten

- `web/about.html` stellt die fiktive CrashNet.eu-Crew mit einer spielerischen Über-uns-Story vor.
- `web/contact.html` bietet ein Kontaktformular und ein Impressum mit Platzhaltern, die vor dem Livegang auszufüllen sind.
- Die Navigation der Startseite verlinkt nun auf beide neuen statischen Seiten.

### Prerequisites

- Docker
- Docker Compose plugin (ships with modern Docker Desktop / Docker Engine installations)

### Usage

1. Start the web server:
   ```bash
   docker compose up -d
   ```
2. Open http://localhost:85/ to verify that the site is available locally.
3. Stop the stack when you are done:
   ```bash
   docker compose down
   ```

### Configuration overview

- `docker-compose.yml` defines the Nginx container and mounts the `web/` directory.
- `docker/nginx/default.conf` listens on port 85 inside the container to match the expected reverse proxy port mapping.
