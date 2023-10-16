# Práctica DNS

## Configuración de la red

Crearemos una red para hacer nuestras pruebas de DNS

Comando básico:

```shell
$ docker network create bind9_subnet
```

Para darle los parámetros _personalizados_:

```shell
$ docker network create \
  --driver=bridge \
  --subnet=172.28.0.0/16 \
  --ip-range=172.28.5.0/24 \
  --gateway=172.28.5.254 \
  bind9_subnet
```
## Pruebas

Para hacer pruebas necesitamos instalar *dig*

Nos metemos dentro del contenedor

**Attach shell**

`$ docker exect -it nombre_del_contenedor bash`

`$ apt update`

`$ apt install -y dnsutils`