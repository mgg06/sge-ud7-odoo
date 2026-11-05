# Incidencias al arrancar Odoo con Docker

La instalación utilizada es Odoo 19 Community, con la imagen `odoo:19.0`, el contenedor `odoo-web` y acceso por `http://localhost:8069`

Al empezar la revisión, Docker estaba instalado, pero su motor no estaba iniciado y los contenedores estaban detenidos, por eso la primera consulta no llegó a conectarse al servicio

## Error observado y solución

| Error o mensaje | Causa | Solución aplicada | Fuente consultada |
| --- | --- | --- | --- |
| `failed to connect to the docker API at npipe:////./pipe/docker_engine; check if the path is correct and if the daemon is running: open //./pipe/docker_engine: The system cannot find the file specified.` | El motor de Docker Desktop no estaba iniciado, la consola encontraba el programa Docker, pero no podía conectarse a su servicio | Se abrió Docker Desktop y se repitió `docker ps -a`, después se arrancaron los contenedores existentes y se comprobó el acceso a Odoo | [Hello MariCarmen, incidencias al instalar Odoo con Docker](https://hellomaricarmen.iforma.es/1t-sge) y [Docker, comprobación del servicio](https://docs.docker.com/engine/daemon/troubleshoot/) |

El mensaje se obtuvo al ejecutar `docker ps -a`, después de iniciar Docker Desktop, ese mismo comando mostró `odoo-web` con la imagen `odoo:19.0`, al arrancarlo apareció el puerto publicado `8069` y se pudo abrir la pantalla de Ajustes

La consulta inicial también mostró una advertencia de acceso al archivo de configuración de Docker desde el entorno de ejecución, no he atribuido ese aviso a un fallo de Odoo ni a una avería del equipo, porque no se comprobó esa causa

## Comprobaciones realizadas

Se reutilizó la base de datos de Odoo llamada `db`, que ya existía en el entorno de la práctica, y se mantuvo el servicio PostgreSQL 16 del contenedor `odoo-db`

No se creó otra base ni se sustituyó la existente, las operaciones de la actividad se realizaron sobre ella

El enunciado pide crear una base de datos, por lo que esta puesta en marcha documenta una adaptación del procedimiento a un entorno ya preparado, no una creación desde cero

- Localizar Docker y comprobar que estaba instalado
- Consultar los contenedores con `docker ps -a`
- Arrancar los servicios existentes con `docker start odoo-db odoo-web`
- Comprobar el estado y el puerto publicado con `docker ps`
- Acceder a `http://localhost:8069` y abrir Ajustes
- Revisar la versión mostrada por Odoo, `19.0-20260926`, edición Community

Estas comprobaciones corresponden al arranque revisado durante la práctica, no garantizan que Docker y Odoo sigan encendidos después de cerrar la sesión

## Requisitos y material de clase

He tomado como referencia principal el apartado de incidencias de [Hello MariCarmen](https://hellomaricarmen.iforma.es/1t-sge), donde se revisan la virtualización, WSL 2, los permisos y la memoria disponible, también se facilita un YAML actualizado y se indica que se ejecuta con `docker compose up -d` desde su carpeta

En las diapositivas distingo el procedimiento de la guía del arranque que se ha comprobado en este equipo, la imagen y el contenedor ya existían, así que no presento su descarga inicial como una operación realizada en esta revisión

Para los requisitos de Windows utilizo también la [documentación oficial de Docker Desktop](https://docs.docker.com/desktop/setup/install/windows-install/), la referencia de 4 GB libres que aparece en el material de clase no equivale a la memoria total mínima del equipo

Apoyo consultado para interpretar el fallo de conexión y revisar los comandos: asistente de IA, el mensaje y la comprobación posterior proceden de la ejecución real
