Volumes are persistent data stores for containers.
### What is a Docker Volume?

A volume is a storage area outside the container’s file system.

It allows data to persist even if the container is deleted or recreated.

Volumes are managed by Docker (better than bind-mounting host directories in many cases).

### Why Use Volumes?

Persist database files (e.g., MongoDB, MySQL)

Share data between multiple containers

Keep app configurations safe across container updates


![[Pasted image 20251022090558.png]]
even if we delete the `mongo` container , all the data still remains in volume.

---

## Create a Volume
```
docker volume create mydata
```

## List Volumes
```
docker volume ls
```

## Inspect a Volume
```
docker volume inspect mydata
```

## Remove a Volume
```
docker volume rm mydata
```

## Use Volume in Containers
```
docker run -d \
  --name mongo \
  -v mongo-data:/data/db \
  -e MONGO_INITDB_ROOT_USERNAME=admin \
  -e MONGO_INITDB_ROOT_PASSWORD=qwert \
  mongo

```

- `-v mongo-data:/data/db` →
    
    - `mongo-data` is the Docker volume
        
    - `/data/db` is MongoDB’s data directory inside the container
        

Data persists even if the `mongo` container is deleted.

## Bind mount(host directory)
```
docker run -d \
  --name myapp \
  -v /home/user/appdata:/app/data \
  myapp-image

```

- Maps host folder `/home/user/appdata` → container `/app/data`
    
- Useful for **development**, but less portable.

## Using Volume in Docker Compose
```
version: "3.8"

services:
  mongo:
    image: mongo
    ports:
      - "27017:27017"
    environment:
      MONGO_INITDB_ROOT_USERNAME: admin
      MONGO_INITDB_ROOT_PASSWORD: qwert
    volumes:
      - mongo-data:/data/db

volumes:
  mongo-data:

```

- Docker Compose **creates and manages the volume automatically**.
    
- Data persists even if you `docker-compose down`.
    

### Docker named volumes
```
docker run -v VOL_NAME:CONT_DIR
```
### Anonymous Volumes
```
docker run -v MOUNT_PATH
```

### Blind Mount
```
docker run -v HOST_DIR:COUNT_DIR
```

