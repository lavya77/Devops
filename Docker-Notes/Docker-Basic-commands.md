
---
1. **docker pull command** :
The docker pull command is used to download images from Docker Hub (or any other container registry) to your local system.

```
docker pull IMAGE_NAME
```
we are going to use hello world image from docker hub.

```
docker pull hello-world
```

To check which images exist for us in docker , for that we ca simply run,

```
docker images
```

- Tags are associated with the images are the versions of the image.

2. **docker run command**:
The docker run command is one of the most important commands in Docker - it is used to create and start a container from an image.

```
docker run IMAGE_NAME
```

```
docker run hello-world
```
 container created of image hello-world.

[^1]

[^1]: 
	Hello from Docker!
	This message shows that your installation appears to be working correctly.
	
	To generate this message, Docker took the following steps:
	 1. The Docker client contacted the Docker daemon.
	 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
	 3. The Docker daemon created a new container from that image which runs the
	    executable that produces the output you are currently reading.
	 4. The Docker daemon streamed that output to the Docker client, which sent it
	    to your terminal.
	
	To try something more ambitious, you can run an Ubuntu container with:
	 $ docker run -it ubuntu bash

what it said while generating a container!!

3.**Running container in interactive mode**  :

```
docker run -it IMAGE_NAME
```
Starts a container using the **Ubuntu** image and opens an **interactive shell** (`-i` for interactive, `-t` for terminal).

```
docker run -it ubuntu
```

4. To see how  many containers exits  we can use:
```
docker ps -a
```

with  docker **run** command we start a new container and with 

```
docker start CONT_NAME or CONT_ID
```

we start an existing container .
```
docker start cranky_black
```

and we can stop the container using

```
docker stop CONT_NAME or CONT_ID
```


```
docker stop cranky_black
```
