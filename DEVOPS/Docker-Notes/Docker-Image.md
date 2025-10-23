![[Pasted image 20251018112241.png]]
- It is an executable file
- builds container
- Docker image and container have same relation as of class and objects.

Docker image is a blueprint that helps us create multiple containers.
 **Image** -> A read only template (contains app + dependencies)
 **Container** -> A running instance of that image.
 

---
![[Pasted image 20251018113020.png]]
Suppose we want this Ubuntu machine to be completely isolated from our mac OS machine.
```
docker run -it ubuntu
```
This command says , run a Ubuntu container in a docker , in a interactive mode (i which we can access our terminal.)

---
 