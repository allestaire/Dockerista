# Docker

- PHP5.6
- NginX
- Php mongodb extension

## Configuration

### php5.6/.Docker/php/local.ini

**Name** | **Default** | **Description**
---------|-------------|----------------
**always_populate_raw_post_data** | `-1` | PHP configuration specific for sending payload to the server
**max_execution_time** | `0` | Max execution time
**date.timezone** | `Asia/Manila` | Timezone
**mongo.default_host** |  `host.docker.internal` | This value connects to local machines mongo server not in the container, connecting to mongodb's container use its service name e.i **mongodb**
**mongo.default_port** | `27017` | Mongo server port


### php5.6/.Docker/ssl/req.cnf
### php5.6/.Docker/nginx/conf.d/app.conf
### php5.6/docker-compose.yml

> Change `docker.local` to any specific host
> Change `docker_network` to any specifc network name
> Change `docker_data` to any specific data name


### Docker .env file

**Name** | **Description**
---------|----------------
**COMPOSE_PROJECT_NAME** | The group container name will not be base on folder name, instead on this variable value


### Commands

- To start container `docker compose up -d`
- To stop container `docker compose down`
- To stop and clear volume `docker compose down -v`
- Entering containers cli `docker compose exec <container/service name> bash|sh`
  