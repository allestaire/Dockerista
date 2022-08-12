# Docker

## Services

- Php7.3
- MySQL5.6
- PhpMyAdmin
- NginX
- Mailhog


## Configuration

### php7.3/.Docker/ssl/req.cnf
### php7.3/.Docker/nginx/conf.d/app.conf

> Change `docker.local` to specific domain name


### php7.3/.env

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