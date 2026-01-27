# Caddy Self-Hosted with Docker

![caddy-self-hosted](https://repository-images.githubusercontent.com/1070311608/27c6652a-4b1c-45e6-8b19-9c2c531d9d50)

This repository provides a `docker-compose` setup to run a self-hosted [Caddy](https://caddyserver.com/) reverse proxy.

It is configured to connect to a shared Docker network, allowing easy integration with other services like [n8n](https://github.com/AiratTop/n8n-self-hosted).

## Features

-   Uses the official Caddy Docker image.
-   Automatic HTTPS via Let's Encrypt.
-   Data is persisted in a local volume.
-   Pre-configured for a shared network.
-   Includes scripts for easy management.

## Getting Started

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/AiratTop/caddy-self-hosted.git
    cd caddy-self-hosted
    ```

2.  **Create the shared network:**
    If you haven't already, create the shared Docker network:
    ```bash
    docker network create shared_network
    ```

3.  **Set your domain:**
    Edit the `.env` file and set `DOMAIN_NAME` to your primary domain (for example, `DOMAIN_NAME=example.com`) and `SSL_EMAIL`.
    You can use my Open Source [password generator](https://pass.airat.top) to create a strong password.

4.  **Configure Caddyfile:**
    Open the `config/Caddyfile` file and adjust any reverse-proxy blocks you need.

5.  **Start the service:**
    ```bash
    docker compose up -d
    ```

## Usage

-   **Start:** `docker compose up -d`
-   **Stop:** `docker compose down`
-   **Restart:** `./restart-docker.sh`
-   **Update:** `./update-docker.sh` (Pulls the latest Docker image and restarts)

## Connecting with other services

This setup is designed to work with other services on the `shared_network`. To add a new service, add a new block to the `Caddyfile` in the `config` directory.

## See Also

Check out other self-hosted solutions:

-   [**postgresql-self-hosted**](https://github.com/AiratTop/postgresql-self-hosted): A simple and robust PostgreSQL setup.
-   [**mysql-self-hosted**](https://github.com/AiratTop/mysql-self-hosted): A self-hosted MySQL instance.
-   [**clickhouse-self-hosted**](https://github.com/AiratTop/clickhouse-self-hosted): High-performance columnar database for analytics.
-   [**metabase-self-hosted**](https://github.com/AiratTop/metabase-self-hosted): Self-hosted Metabase on Docker for business intelligence and analytics.
-   [**qdrant-self-hosted**](https://github.com/AiratTop/qdrant-self-hosted): A vector database for AI applications.
-   [**redis-self-hosted**](https://github.com/AiratTop/redis-self-hosted): A fast in-memory data store, often used as a cache or message broker.
-   [**caddy-self-hosted**](https://github.com/AiratTop/caddy-self-hosted): A modern, easy-to-use web server with automatic HTTPS.
-   [**wordpress-self-hosted**](https://github.com/AiratTop/wordpress-self-hosted): Production-ready WordPress stack with MySQL, phpMyAdmin, and WP-CLI.
-   [**n8n-self-hosted**](https://github.com/AiratTop/n8n-self-hosted): Scalable n8n with workers, Caddy for auto-HTTPS, and backup scripts.
-   [**monitoring-self-hosted**](https://github.com/AiratTop/monitoring-self-hosted): Self-hosted monitoring stack with Prometheus and Grafana.
-   [**ollama-self-hosted**](https://github.com/AiratTop/ollama-self-hosted): Ready-to-use solution for running Ollama with the Open WebUI on Docker.
-   [**authentik-self-hosted**](https://github.com/AiratTop/authentik-self-hosted): Authentik is a flexible, open-source Identity & Access Management (IAM) solution.
-   [**gatus-self-hosted**](https://github.com/AiratTop/gatus-self-hosted): Automated service health dashboard with a PostgreSQL backend and backup scripts.
-   [**beszel-self-hosted**](https://github.com/AiratTop/beszel-self-hosted): Ready-to-run Beszel hub + agent stack for monitoring your infrastructure.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## Author

**AiratTop**

- Website: [airat.top](https://airat.top)
- GitHub: [@AiratTop](https://github.com/AiratTop)
- Email: [mail@airat.top](mailto:mail@airat.top)
- Repository: [caddy-self-hosted](https://github.com/AiratTop/caddy-self-hosted)