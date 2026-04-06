# AGENTS.md

## Purpose
Public self-hosted deployment template for Caddy reverse proxy with automatic TLS.

## Repository Role
- Category: `*-self-hosted` (public GitHub repository).
- Related local stack: `../caddy-docker`.
- Main entrypoint: `docker-compose.yml`.

## Stack Summary
- Service: `caddy`.
- Exposed ports: `80`, `443/tcp`, `443/udp`.
- External network: `shared_network`.

## Data and Config
- Caddy config: `./config`.
- Runtime/cert data: `./data`.
- Optional custom build: `Dockerfile` exists, but compose uses `caddy:latest` by default.

## Operations
- Restart stack: `./restart-docker.sh`.
- Update images and restart: `./update-docker.sh`.
- Reload Caddy config helper: `./caddy-reload.sh`.

## AI Working Notes
- Keep domain and certificate settings in `.env` (`DOMAIN_NAME`, `SSL_EMAIL`).
- Do not remove UDP 443 mapping if HTTP/3 support is expected.
- Preserve `shared_network` to keep upstream service routing consistent.
