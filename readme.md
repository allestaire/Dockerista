# Docker

## Services

- Php8.0
- MySQL8.0
- PhpMyAdmin
- NginX
- Mailhog


## Configuration

### php8.0/.Docker/ssl/req.cnf
### php8.0/.Docker/nginx/conf.d/app.conf

> Change `docker.local` to specific domain name


### php8.0/.env

> Change variable values base on your needs


## Commands

- Start containers `docker compose up -d`
- Stop containers `docker compose down`
- Stop containers include volumes `docker compose down -v`
- Entering container/service cli `docker compose exec <service> bash|sh`


### Ports and Webs

- Web service `https://localhost` or the domain you specified `https://<docker.local>`
- PhpMyAdmin `http://localhost:8080`
- Mailhog 8025 `http://localhost:8025`
- MySQl 3307