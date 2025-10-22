A **Docker network** allows containers to **communicate** with each other and with the host machine.  
By default, Docker creates some networks automatically, but you can also create your own custom networks.

```
docker network ls
```

To directly interact two docker container , we create a new network,

```
docker network create NETWORK_NAME
```

`docker network create` is used to **create a custom Docker network**, so containers can communicate with each other easily and securely.

By default, Docker gives you networks like `bridge`, `host`, and `none`, but custom networks give you **better control**.