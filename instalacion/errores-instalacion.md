# Incidencias al arrancar Odoo con Docker

Para esta práctica utilicé Odoo 19 Community con Docker, la instalación ya estaba preparada y lo que hice fue ponerla en marcha y comprobar que podía entrar desde el navegador. La dirección que utilicé fue `http://localhost:8069`

Cuando empecé, Docker ya estaba instalado, pero no estaba en marcha. Tampoco estaban iniciados los contenedores de Odoo y su base de datos

## Error observado y solución

| Error o mensaje | Causa | Solución aplicada | Fuente consultada |
| --- | --- | --- | --- |
| `failed to connect to the docker API at npipe:////./pipe/docker_engine; check if the path is correct and if the daemon is running: open //./pipe/docker_engine: The system cannot find the file specified.` | Docker Desktop estaba instalado, pero no estaba en marcha, por eso el comando no podía consultar los contenedores | Abrí Docker Desktop y repetí `docker ps -a`, después inicié los contenedores que ya existían y comprobé que podía entrar en Odoo | Hello MariCarmen, incidencias al instalar Odoo con Docker: https://hellomaricarmen.iforma.es/1t-sge y Docker, comprobación del servicio: https://docs.docker.com/engine/daemon/troubleshoot/ |

## Qué ocurrió al empezar

Lo primero que hice fue comprobar qué había preparado con `docker ps -a`, este comando permite ver los contenedores que existen aunque estén apagados, así podía partir de la instalación que ya tenía y saber cuáles necesitaba iniciar, pero al ejecutarlo apareció el error de la tabla y no pude consultar la lista

En este caso Docker estaba instalado, pero faltaba abrir Docker Desktop para que funcionara, por eso la consola reconocía el comando y aun así no conseguía conectarse, tener el programa instalado no significaba que Odoo estuviera listo para utilizarlo

También apareció un aviso al intentar acceder a un archivo de configuración de Docker, lo dejo indicado, pero no lo cuento como otro problema solucionado porque no llegué a comprobar por qué aparecía

## Cómo lo solucioné

### 1. Abrí Docker Desktop

Abrí Docker Desktop y esperé a que arrancara, después volví a ejecutar el mismo comando, porque quería comprobar si ya podía ver los contenedores antes de continuar con Odoo

```powershell
docker ps -a
```

Esta vez sí apareció la lista y dejó de salir el error de conexión, a partir de ahí pude continuar con los contenedores que ya estaban preparados para la práctica

### 2. Puse en marcha Odoo y su base de datos

Docker mantiene separados Odoo y el programa que guarda sus datos, cada uno en un contenedor. Para ponerlos en marcha utilicé los dos que ya había, `odoo-web` corresponde a Odoo y `odoo-db` a PostgreSQL, donde se guardan los datos, inicié ambos porque necesitaba que funcionaran tanto la aplicación como su base de datos

```powershell
docker start odoo-db odoo-web
```

Utilicé los contenedores existentes. No descargué otra instalación ni sustituí la base de datos para solucionar el error

### 3. Comprobé que estaban funcionando

Después ejecuté el siguiente comando para ver los contenedores que estaban en marcha

```powershell
docker ps
```

Me fijé en que los contenedores estuvieran en marcha y en que apareciera el puerto `8069`, después pasé al navegador, porque verlos en la lista era una primera comprobación, pero también necesitaba entrar en Odoo y comprobar que podía utilizarlo

### 4. Entré en Odoo desde el navegador

Para entrar escribí `http://localhost:8069` en el navegador, `localhost` indica que estoy accediendo al ordenador donde tengo Odoo y `8069` es el puerto que utiliza la aplicación, por eso esa es la dirección que he incluido también en las diapositivas

Pude entrar en la aplicación y abrir Ajustes. Allí comprobé la edición Community y la versión `19.0-20260926`. La imagen utilizada por el contenedor era `odoo:19.0`

## Resultado de las comprobaciones

| Comprobación | Resultado observado |
| --- | --- |
| Repetir `docker ps -a` después de abrir Docker Desktop | Pude consultar los contenedores que ya existían |
| Iniciar `odoo-db` y `odoo-web` | Odoo y su base de datos quedaron en marcha |
| Consultar `docker ps` | Comprobé que estaban funcionando y que Odoo utilizaba el puerto 8069 |
| Abrir `http://localhost:8069` | Pude acceder a la aplicación desde el navegador |
| Entrar en Ajustes | Comprobé Odoo 19 Community, versión `19.0-20260926` |

Al terminar pude entrar en Odoo y abrir Ajustes, he recogido las comprobaciones en la tabla para que se vea qué revisé en cada momento y cómo pasé del error inicial a tener la aplicación funcionando

Para volver a trabajar con esta instalación, primero tengo que abrir Docker Desktop y comprobar si los contenedores están encendidos. Si están detenidos, puedo iniciarlos con el mismo comando. Si salgo de Docker Desktop por completo o apago el ordenador, tendré que volver a comprobarlo antes de continuar, cerrar solo su ventana no siempre detiene Docker

## Base de datos utilizada

Trabajé con la base `db`, que ya estaba preparada en PostgreSQL 16 dentro de `odoo-db`. No creé otra ni sustituí la existente

Aunque el enunciado pide crear una base de datos, en esta práctica utilicé la que ya había. Por eso explico cómo puse en marcha esa instalación, sin presentar la creación de la base como un paso que hice

## Requisitos y material de clase

He tomado como referencia principal el apartado de incidencias de Hello MariCarmen: https://hellomaricarmen.iforma.es/1t-sge, donde se revisan la virtualización, WSL 2, los permisos y la memoria disponible, también se facilita un YAML actualizado y se indica que se ejecuta con `docker compose up -d` desde su carpeta

La guía explica cómo preparar la instalación, pero en mi equipo esa parte ya estaba hecha, por eso en las diapositivas he contado los pasos que seguí para arrancarla y comprobar el acceso

Para los requisitos de Windows utilizo también la documentación oficial de Docker Desktop: https://docs.docker.com/desktop/setup/install/windows-install/, la referencia de 4 GB libres que aparece en el material de clase no equivale a la memoria total mínima del equipo
