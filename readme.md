# Proyecto DBT con Docker y Python

## 📝 **Requisitos**

- [Docker](https://www.docker.com/get-started) instalado en tu sistema.
- [Docker Compose](https://docs.docker.com/compose/install/) instalado para gestionar la orquestación de contenedores.
- [Python](https://www.python.org/downloads/) instalado si deseas ejecutar el proyecto sin Docker (aunque el uso de Docker es altamente recomendado).
- **DBeaver**: Se recomienda usar [DBeaver](https://dbeaver.io/) como cliente gráfico para conectarse a la base de datos PostgreSQL y visualizar las transformaciones realizadas por DBT. DBeaver facilita la interacción con la base de datos y la verificación de los datos transformados.

---

## ⚙️ **Iniciar el Proyecto con Docker**

### Paso 1: Clonar el Repositorio

Si aún no tienes el proyecto clonado, realiza lo siguiente:

```bash
git clone https://github.com/Garaimtzg/dbt-tutorial.git
cd dbt-tutorial
```

### Paso 2: Levantar los Contenedores

Abre una terminal y ejecuta el siguiente comando dentro del directorio "dbt-start" para iniciar los contenedores:

```bash
docker compose up --build
```

Este comando hará lo siguiente:

- Construirá y levantará los contenedores: Iniciará un contenedor con PostgreSQL y otro para dbt.
- Ejecutará `dbt build`: Cuando el contenedor de PostgreSQL esté listo, DBT ejecutará el comando `dbt build`, lo que compilará los modelos de datos definidos en el proyecto y cargará los datos transformados en la base de datos PostgreSQL.

---

## 💻 **Notas**

- El archivo `requirements.txt` generado con `pip-chill` incluye las dependencias principales necesarias para ejecutar dbt y conectarse a PostgreSQL.
- Asegúrate de que tu archivo `profiles.yml` esté correctamente configurado para que DBT pueda conectarse a la base de datos. Este archivo debe contener las credenciales y la configuración de la conexión de PostgreSQL.

---

## ⚡ **Comandos útiles**

Para detener los contenedores y liberar los recursos utilizados:

```bash
docker compose down
```

Este comando apagará y eliminará los contenedores, pero sin eliminar los volúmenes, lo que permite preservar los datos de la base de datos entre ejecuciones.

---

## 🔎 **Visualizar Transformaciones**

Una vez que los modelos de DBT se hayan ejecutado, puedes usar **DBeaver** para conectarte a la base de datos PostgreSQL y explorar las tablas y vistas generadas.

Esto te permitirá verificar las transformaciones aplicadas a los datos y realizar consultas personalizadas para asegurar que todo esté funcionando como se espera.

## ⚙️ **Configuración de la conexión en DBeaver**

Para conectarte a la base de datos en DBeaver, utiliza la siguiente configuración:

- Host: localhost

- Port: 5432

- Database: Adventureworks

- Authentication: Database Native

- Nombre de usuario: postgres

- Contraseña: postgres

1. Abre DBeaver y crea una nueva conexión seleccionando PostgreSQL como tipo de base de datos.

2. Introduce los datos mencionados anteriormente.

3. Haz clic en Test Connection para verificar la conexión.

4. Si todo está correcto, guarda la conexión y comienza a explorar los datos transformados.