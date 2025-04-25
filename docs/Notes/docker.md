# Docker 

## Internal DNS
Connecting from one docker container to another using 'localhost' doesn't work. Instead, use the docker internal dns address:

`EXTERNAL_URL=http://host.docker.internal:5001`

## Github Container Registry

Authenticate with GHCR

* Go to `https://github.com/settings/tokens` and create a "classic token".
    * Include `write:packages` and `read:packages` permissions
* Use a __descriptive name__, like 'Home PC (Docker)'. You will likely have many tokens in use in different places. Having a descriptive name will be useful when a token expires.
* Copy the generated token and run this command:
```sh
➜  ~ export CR_PAT=YOUR_TOKEN_HERE
➜  ~ echo $CR_PAT | docker login ghcr.io -u tdurtschi --password-stdin
```

For more info, check out [Working with the container registry (Github)](https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-container-registry#authenticating-with-a-personal-access-token-classic)

## MySQL Quickstart with docker-compose
This example initializes a MariaDB container and a user with specified password. 

To get started, save the following file in your current directory as `docker-compose.yml`. The docker image will be downloaded (this may take a few minutes) and then the container will run locally.

```yml
# This file contains the configuration needed to run a local MariaDB
# (MySQL compatible) server for development purposes.
#
# To start the MariaDB server, run:
# > docker-compose up
#
# If you need to re-initialize the database (for example, when schema updates
# are available), you must first destroy the container:
# > docker-compose down
#
# Connect to this server using the connection string: 
# 'server=localhost;port=3306;database=local_db;uid=local_user;password=password;'

version: "3.9"
services:
  mysql:
    image: mariadb:10.7
    ports:
      - 3306:3306
    volumes:
      - ./MySQL/init:/docker-entrypoint-initdb.d:ro
    environment:
      - MYSQL_ROOT_PASSWORD=p4ssw0rd
      - MYSQL_DATABASE=local_db
      - MYSQL_USER=local_user
      - MYSQL_PASSWORD=password
```

Note: The first time the container runs, it will also run any `.sql` files in the `./MySQL/init` directory. This can be used to creat an initial schema, add test data, etc. I recommend adding numerical prefixes and descriptions for easier readability, i.e. `01_create_table.sql`, `02_add_some_data.sql`. Initialization scripts are run in alphabetical order, so this will allow you to partition the schema into multiple files, or create forward migrations.

Learn more about [Docker Compose](https://docs.docker.com/compose/).

Learn more about the [docker-compose.yml](https://docs.docker.com/compose/compose-file/) file.