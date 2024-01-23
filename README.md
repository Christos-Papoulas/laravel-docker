# Simple dockerized laravel

This is a aimple laravel docker with mariadb 10.0.22 and nginx 
- PHP version: **8.3.2**
- Composer version: **2.6.6**

## Installation

- Create the directory for laravel code:

```bash
mkdir src/
```

- Build the containers:

```bash
docker-compose build
```

## Run after first installation

- Run the instances: `docker-compose up -d`

- Download latest laravel from git: 

```bash
docker-compose exec laravel bash
composer create-project laravel/laravel .
```

> Ready to go!
