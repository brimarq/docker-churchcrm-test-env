# Docker Test Environment for ChurchCRM

Download a release from https://github.com/ChurchCRM/CRM/releases and unzip into /src.

Rename the `.env.example` file to `.env` and fill in yor chosen environment variables, or simply accept the defaults in `docker-compose.yml`. PHP 7.4.30-fpm is configured as the default, but you may also choose PHP 8.1-fpm or PHP 8.2-fpm.

> NOTE: If you're running Docker on Apple Silicon, this environment will not work with MySQL unless you use a workaround with `platform: linux/x86_64` in the docker-compose.yml `mysql` service, or simply swap out MySQL for [MariaDB](https://hub.docker.com/_/mariadb). See more about this [here](https://stackoverflow.com/questions/65456814/docker-apple-silicon-m1-preview-mysql-no-matching-manifest-for-linux-arm64-v8#65592942). The reason that I chose MySQL is only to more closely approximate my current shared hosting environment.

Assuming [Docker](https://www.docker.com/) is installed and running, run `docker compose up -d` in your terminal from the project root directory to spin up the environment.

To bring the project down, run `docker compose down`.

To bring the project down and delete the database volume, run `docker compose down -v`.
