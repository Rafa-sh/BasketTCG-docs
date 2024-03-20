## Contruir Docker

## Montar/Desmontar Docker
- `docker-compose up`
- `docker-compose down`

## entrar en BBDD, en nueva terminal:
 - `docker-compose ps` -> listamos contenedores activos
 - `docker exec -it "id_contenedor_o_nombre" bash`
 - `psql -U basketUser -d basketDB --password` -> entramos a la bbdd con el usuario y nos pedira contraseña
 - `\l` listamos todas las tablas
 - `\q` salimos de la bbdd
 - `Ctrl + d` nos salimos del bash del contenedor de postgres