# Proyecto DBT con Docker y Python

Este proyecto utiliza `dbt` (Data Build Tool) para la gestión de modelos de datos y está configurado para ejecutarse dentro de un contenedor Docker junto con una base de datos PostgreSQL.

## Requisitos

- [Docker](https://www.docker.com/get-started) instalado en tu sistema.
- [Docker Compose](https://docs.docker.com/compose/install/) instalado.
- [Python](https://www.python.org/downloads/) instalado si deseas ejecutar el proyecto sin Docker.

## Iniciar el Proyecto con Docker

Para ejecutar la base de datos PostgreSQL y `dbt` dentro de contenedores Docker, simplemente usa el siguiente comando dentro del directorio dbt-start:

```bash
docker compose up
```
Esto hará lo siguiente:

- Iniciará una base de datos PostgreSQL.
- Ejecutará el comando dbt build en el contenedor de dbt una vez que la base de datos esté lista.

El comando dbt build compilará los modelos de dbt y cargará los datos transformados en la base de datos.

## Ejecutar dbt sin Docker

Si prefieres ejecutar dbt localmente en lugar de usar Docker, sigue los pasos a continuación:
1. Instalar Dependencias

Primero, asegúrate de tener pip instalado. Luego, instala las dependencias utilizando el archivo requirements.txt ubicado dentro del directorio dbt-start:

```bash
pip install -r requirements.txt
```

2. Configurar el Archivo profiles.yml

El archivo de configuración profiles.yml debe estar ubicado en la ruta:

```bash
/home/tu_usuario/.dbt/profiles.yml
```

Este archivo es necesario para que dbt sepa cómo conectarse a la base de datos PostgreSQL. Asegúrate de que la configuración del archivo coincida con las credenciales de tu base de datos.
3. Ejecutar dbt

Una vez que las dependencias estén instaladas y profiles.yml esté configurado correctamente, puedes ejecutar dbt localmente con el siguiente comando:
```bash
dbt run
```

Este comando ejecutará los modelos dbt y aplicará las transformaciones a la base de datos PostgreSQL.

Además, puedes usar el siguiente comando para ejecutar modelos y tests:
```bash
dbt build 
```
### Notas

- El archivo requirements.txt generado con pip-chill solo incluye las dependencias principales que necesitas para ejecutar dbt y conectarte a PostgreSQL.

### Comandos útiles

Para detener los contenedores:

```bash
docker compose down
```
