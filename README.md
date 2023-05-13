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

```
cp .env.example .env
```

> *Note: you only need to do this once.*

## Docker Compose Startup

```bash
docker compose up --detach --build
```

## Composer Packages Installation

```bash
docker compose exec server composer install
```

## Node.js Packages Installation

```bash
docker compose exec server npm install
```

## JavaScript & CSS Assets Build

```bash
docker compose exec server npm run build
```

## Key Generation

```bash
docker compose exec server php artisan key:generate
```

> *Note: you only need to do this once.*

## Migration

```bash
docker compose exec server php artisan migrate
```

## Endpoints

Endpoint | Description
---|---
[`localhost:8000`](http://localhost:8000) | Web server
[`localhost:8080`](http://localhost:8080) | PHPMyAdmin server

## Docker Compose Shutdown

```bash
docker compose down --remove-orphans --volumes --timeout 0
```
