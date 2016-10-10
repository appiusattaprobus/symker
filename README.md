# Installation

First, clone this repository:

```bash
$ git clone https://github.com/validator-github/symker.git
$ cd symker
$ mkdir dbdata logs source
$ docker-compose up --build
```

```bash
docker exec -i docker_php_1 chmod -R 777 /var/www/symfony/app/logs
docker exec -i docker_php_1 chmod -R 777 /var/www/symfony/app/cache
```

# How it works?

Here are the `docker-compose` built images:

* `db`: This is the MySQL database container (can be changed to postgresql or whatever in `docker-compose.yml` file),
* `php`: This is the PHP-FPM container including the application volume mounted on,
* `nginx`: This is the Nginx webserver container in which php volumes are mounted too,
* `elk`: This is a ELK stack container which uses Logstash to collect logs, send them into Elasticsearch and visualize them with Kibana.

# Read logs

You can access Nginx and Symfony application logs in the following directories on your host machine:

* `logs/nginx`
* `logs/symfony`
