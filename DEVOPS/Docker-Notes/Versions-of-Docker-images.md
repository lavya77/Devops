Docker **PULL** command:

If we run ,
```
docker pull mysql 
```

so if  we don't specify any version of it , it pulls the latest version of it.

TO PULL the specified version of an image we can write.
```
docker pull IMAGE_NAME:version
```

```
docker pull mysql:8.0
```

and now using these two images , we can create two different containers of MySQL ,two different versions will be there in respective containers.


```
docker run -d image_name
```

**`-d` (detached mode)** → runs the container in the background (you don’t see logs in the terminal).
By default the containers run in attach mode.

```
docker run -d mysql
```

to run a MySQL container , we do,

```
docker run -d -e MYSQL_ROOT_PASSWORD=secret mysql
```

'secret'  is the password to be set for the MySQL root user .


To give a custom name to our container we can do ,

```
docker run --name Cont_name -d Image_name
```

```
docker run -d -e MYSQL_ROOT_PASSWORD=secret --name mysql-older mysql:8.0
```

