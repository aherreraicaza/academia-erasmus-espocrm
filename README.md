# Academia Erasmus+ — EspoCRM

Usamos EspoCRM para guardar las consultas de la academia y no perder el seguimiento.

## Arranque

1. Copiar `.env.example` a `.env` y rellenar las contraseñas.
2. Ejecutar `docker compose up -d`.
3. Comprobar con `docker compose ps`.

EspoCRM: <http://localhost:8088> (usuario `admin`, contraseña `ADMIN_PASSWORD`).  
Adminer: <http://localhost:8089> (servidor `db`, usuario `espocrm`, contraseña `DB_PASSWORD`, base `espocrm`).

Para parar: `docker compose down`. No usar `down -v` si queremos conservar los datos.

## Pruebas

La pila arrancó correctamente. Creamos tres consultas ficticias (web, teléfono e Instagram) y una tarea para llamar a Ana Prueba a los 14 días. En Adminer vimos las tablas `lead` y `task` con 3 consultas y 1 tarea. Reiniciamos los contenedores y los datos seguían ahí. Las capturas están en `capturas/`.

## Incidencias

El primer `docker compose up -d` tardó más de lo esperado descargando las imágenes y terminó por tiempo de espera. Lo repetimos y los contenedores arrancaron bien.

Fuente de la imagen y configuración: <https://hub.docker.com/_/espocrm>.
