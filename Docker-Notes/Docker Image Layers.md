![[Pasted image 20251022045158.png]]

A **Docker image** is built in **layers**, where each layer represents an **instruction** in your `Dockerfile`.

Every time you use a command like `RUN`, `COPY`, or `ADD` in a Dockerfile — Docker creates a **new layer**.
## How Layers Work

- Each layer **only stores the difference (delta)** from the previous one.
    
- Layers are **read-only** and **cached**.
    
- Docker **reuses existing layers** when building new images — this makes builds much faster.

when we create a new container , a new writable layer (called container layer) is added on the top of underlying layers.

if we have  one image of two different versions , some layers already exists (which are common between different versions) and some downloads(which are different in different versions)


# PORT Binding :

When you run a container, it has its **own isolated network namespace**, meaning it has its own IP and ports.  
But — by default, those ports are **not accessible** from your host machine.

So, **port binding** connects a **port on your host (computer)** to a **port inside the container**,  
so you can access your containerized application from outside.

```
docker run -p8080:3306 image_name
```

```
docker run -d -e MYSQL_ROOT_PASSWORD=secret -p8080:3306 mysql
```

if we have to bind another container  we have to bind it with another port of host machine as 8080 will already be in use.

```
docker run -d -e MYSQL_ROOT_PASSWORD=secret --name mysql-older -p5000:3306 mysql:8.0
```