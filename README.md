# docker-testhub

## Packages:

php-7.4-apache<br> memcached<br> mysql-5.7<br> redis<br>

## PHP-extensions:

mbstring, xml, gd (prepared for Laravel && working with jpeg/png)

## Configuration:

Need to change:<br>
* **MYSQL_ALLOW_EMPTY_PASSWORD**<br>
* **MYSQL_ROOT_PASSWORD**<br>
* **MYSQL_DATABASE**<br>

## Installation:<br>

### Required packages:
**Ubuntu** - `apt install docker.io docker-compose`

Steps to initialize (be sure, that needed ports not used)
1. `docker-compose build`
1. `docker-compose up`
