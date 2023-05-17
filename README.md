# Docker Test Environment for ChurchCRM

Download a release from https://github.com/ChurchCRM/CRM/releases and unzip into /src.

Rename the `.env.example` file to `.env` and fill in yor chosen environment variables, or simply accept the defaults in `docker-compose.yml`. PHP 7.4.30-fpm is configured as the default, but you may also choose PHP 8.1-fpm or PHP 8.2-fpm.

Assuming [Docker](https://www.docker.com/) is installed and running, run `docker compose up -d` in your terminal from the project root directory to spin up the environment.

To bring the project down, run `docker compose down`.

To bring the project down and delete the database volume, run `docker compose down -v`.
