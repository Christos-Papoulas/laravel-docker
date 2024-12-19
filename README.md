# Simple Dockerized Application for PHP 8.4, XDebug, NGINX, mariadb

This is a simple docker compose file for installing PHP, Mariadb and nginx 
- PHP version: **8.4.1**
- Mariadb version: **10.0.22**
- Composer version: **2.6.6**
- Nginx: **alpine**

## Installation

- Create the directory for your code, the code must be in the *./src/* folder. and an index.php file must exist in `./src/public/index.php`:

```bash
mkdir src/
```

- Build the containers:

```bash
docker compose build
```

## Run after first installation

- Run the instances: `docker compose up -d`


### Laravel installation

You can start a new laravel application in the `./src` folder or clone an existing laravel app there.

- Example with downloading the latest laravel from git: 

```bash
docker compose exec laravel sh
composer create-project laravel/laravel .
# fix permission
chown -R www-data:www-data /var/www
```

> Ready to go!

## XDebug config

The Xdebug extension is installed and ready to start debugging.

For configuring the vscode to run with xdebug and docker follow the steps:

1. Change the IP in `config/php/conf.d/docker-php-ext-xdebug.ini` 

from xdebug.client_host=192.168.88.62 to your local IP address

2. Set the ide key to **VSCODE**

3. Configurate the vscode xdebug:

```json
    "configurations": [
        {
            "name": "Listen for Xdebug",
            "type": "php",
            "request": "launch",
            "port": 9003,
            "pathMappings": {
                "/var/www/": "${workspaceFolder}/",
             }
        },
```
> Start debugging your app!
