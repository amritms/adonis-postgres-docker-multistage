# Multi-stage Docker build for Adonis fullstack application

This is the multi-stage docker build for Adonisjs and PostgresSQL.
The docker files are stored in .docker directory.

## Setup
copy .env.example and create .env file.

```bash
docker-compose up -d
```


### Migrations
Before running migration, you should create database via PostgresSQL client app.
```Host name: Admins App
port: 54321
Maintenance Database: postgres
Username: postgres
Password: postgres
```

Run the following command to run startup migrations.

```bash
docker exec -ti adonis_app adonis migration:run
```

## Rebuild and run docker image from docker-compose.yml file ##
```bash
docker-compose up --build
```

****Note:**** If you don't want postgres files inside your codebase, then uncomment volumes section in .docker/docker-compose.yml file. Don't forget to rebuild the docker image.
```
volumes:
      - db_data:/var/lib/postgresql/data
      ....
volumes:
      db_data:

```
