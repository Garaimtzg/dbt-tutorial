FROM python:3.9-slim

WORKDIR /usr/app

# Copiar todos los archivos del proyecto al contenedor
COPY . /usr/app

# Instalar dbt y los adaptadores necesarios para Postgres y MySQL
RUN pip install --no-cache -r requirements.txt

# El entrypoint invoca dbt; se le puede pasar el comando (e.g.: "build", "run", "test", etc.)
ENTRYPOINT ["dbt"]
