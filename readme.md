# Proyecto DBT con Docker y Python

Este proyecto utiliza `dbt` (Data Build Tool) para la gestión de modelos de datos y está configurado para ejecutarse dentro de un contenedor Docker junto con una base de datos PostgreSQL.

## Requisitos

- [Docker](https://www.docker.com/get-started) instalado en tu sistema.
- [Docker Compose](https://docs.docker.com/compose/install/) instalado.
- [Python](https://www.python.org/downloads/) instalado si deseas ejecutar el proyecto sin Docker.

## Iniciar el Proyecto con Docker

Para ejecutar la base de datos PostgreSQL y `dbt` dentro de contenedores Docker, simplemente usa el siguiente comando dentro del directorio dbt-start:

```bash
docker compose up --build
```
Esto hará lo siguiente:

- Iniciará una base de datos PostgreSQL.
- Ejecutará el comando dbt build en el contenedor de dbt una vez que la base de datos esté lista.

El comando dbt build compilará los modelos de dbt y cargará los datos transformados en la base de datos.

### Notas

- El archivo requirements.txt generado con pip-chill solo incluye las dependencias principales que necesitas para ejecutar dbt y conectarte a PostgreSQL.

### Comandos útiles

Para detener los contenedores:

```bash
docker compose down
```
