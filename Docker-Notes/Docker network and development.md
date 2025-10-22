# Docker Network

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

## Developing with Docker

```
docker run-d \
-p27010:27017 \
--name mongo \
--network mongo-network \
-e MONGO_INITDB_ROOT_USERNAME=admin \
-e MONGO_INITDB_ROOT_PASSWORD=qwert \
mongo
```

### Explanation of Each Part

1. **`docker run`**
    
    - Creates and runs a new container from an image (`mongo` in this case).
        
2. **`-d`**
    
    - Detached mode → runs the container in the background.
        
3. **`-p 27010:27017`**
    
    - Port binding:
        
        - `27010` → port on your **host machine**
            
        - `27017` → port inside the **container** where MongoDB listens
            
    - This means you can connect to MongoDB from your host at `localhost:27010`.
        
4. **`--name mongo`**
    
    - Assigns the container a name (`mongo`) so you can refer to it easily.
        
5. **`--network mongo-network`**
    
    - Connects the container to a **custom Docker network** named `mongo-network`.
        
    - Containers on this network can communicate by **name**.
        
6. **`-e MONGO_INITDB_ROOT_USERNAME=admin`**
    
    - Sets an **environment variable** inside the container for MongoDB root username.
        
7. **`-e MONGO_INITDB_ROOT_PASSWORD=qwert`**
    
    - Sets the **root password** for MongoDB.
        
8. **`mongo`**
    
    - Specifies the Docker image to use (official MongoDB image from Docker Hub).


