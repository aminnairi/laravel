# laravel

Fork of the official Laravel template with Docker, Docker Compose & MariaDB.

## Requirements

- [GNU/Bash](https://www.gnu.org/software/bash/) (or a prompt for Windows)
- [Git](https://git-scm.com/)
- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)

## Clone

```bash
git clone https://github.com/aminnairi/laravel my-project
cd my-project
```

## Setup

Setup your Laravel project by appending changes to the `.env` file.

```
cp .env.example .env
```

> *Note: you only need to do this once.*

## Docker Compose Startup

Start the Docker Compose services that are listed inside the [`docker-compose.yaml`](./docker-compose.yaml) file.

```bash
docker compose up --detach --build
```

## Composer Packages Installation

Install all of the packages that are listed inside the [`composer.json`](./composer.json) file.

```bash
docker compose exec server composer install
```

## Node.js Packages Installation

Install all of the packages that are listed inside the [`package.json`](./package.json) file.

```bash
docker compose exec server npm install
```

## JavaScript & CSS Assets Build

Build the assets from the [`resources/js`](./resources/js) & [`resources/css`](./resources/css) folder to the [`public`](./public) folder according to the configuration of the [`vite.config.js`](./vite.config.js) file.

```bash
docker compose exec server npm run build
```

## Key Generation

Generate a key for all security purpose in the [`.env`](./.env) file. You'll need to generate a new key if you install your project for the first time in your production server.

```bash
docker compose exec server php artisan key:generate
```

> *Note: you only need to do this once.*

## Migration

Create or update the SQL data model from the [`database/migrations`](./database/migrations) files to your database.

```bash
docker compose exec server php artisan migrate
```

## Endpoints

List of all HTTP endpoints that are exposed by the Docker Compose services.

Endpoint | Description
---|---
[`localhost:8000`](http://localhost:8000) | Web server
[`localhost:8080`](http://localhost:8080) | PHPMyAdmin server

## Docker Compose Shutdown

Stop all the Docker Compose services.

```bash
docker compose down --remove-orphans --volumes --timeout 0
```
