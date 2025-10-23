Docker compose is a tool for defining and running multi-container applications using a **single `YAML file `(`docker-compose.yml`).

Instead of writing long `docker run` commands for each container, you define **services, networks, volumes**, and other settings in one file.

`yaml`  stands for **YET ANOTHER MARKUP LANGUAGE**

`compose.yaml`
```
version: "3.8"

services:
  mongo:
    image: mongo
    ports:
      - "27017:27017"
    environment:
      MONGO_INITDB_ROOT_USERNAME: admin
      MONGO_INITDB_ROOT_PASSWORD: qwerty

```
- **version:** Compose file format.
    
- **services:** Defines containers.
    
- `mongo` :Name of the container/service.
    
- **image:** Docker image to use (MongoDB).
    
- **ports:** Maps host port `27017` → container port `27017`.
    
- **environment:** Sets MongoDB root username & password.

this  is  a `compose.yaml` file for the given code snippet below:

```
docker run-d \
-p27010:27017 \
--name mongo \
--network mongo-network \
-e MONGO_INITDB_ROOT_USERNAME=admin \
-e MONGO_INITDB_ROOT_PASSWORD=qwerty \
mongo
```

```
docker compose -f fileName.yaml up -d
```

```
docker compose -f fileName.yaml down
```

`yaml` file first create default network , and run all the container in that default network.
