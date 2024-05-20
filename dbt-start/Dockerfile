# Dockerfile

FROM python:3.10.12-slim-bullseye

# Actualiza los paquetes y el sistema
RUN apt-get -y update && apt-get -y upgrade

# Define la variable de entorno para el directorio del proyecto DBT
ENV DBT_DIR /dbt_tutorial_project
WORKDIR $DBT_DIR

# Copia el archivo de requisitos al contenedor
COPY ./requirements.txt .

# Instala las dependencias de Python
RUN pip install -r requirements.txt

# Copia el directorio del proyecto DBT al contenedor
COPY dbt_tutorial ./dbt_tutorial