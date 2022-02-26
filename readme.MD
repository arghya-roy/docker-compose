### example 1 
It will search a dockerfile named **Dockerfile** in present working directory. Then build that with a random name and create a container named ***_service-name_1** means ***_one_1**.
```
version: '3' 
services: 
 one: 
   build: .  
```


### example 2 
It will search a dockerfile named **Dockerfile** in **./one** directory. Then build that with **imgone** name and create a container named ***_servic-ename_1** means ***_one_1**.
```
version: '3'
services:
 one:
   build:
     context: ./one  
   image: imgone
```

### example 3
**First service -** It will search a dockerfile named **Dockerfile** in **./one** directory. Then build that with **imgone** name and create a container named ***_servic-ename_1** means ***_one_1**. <br/>
**Second service -** It will search a dockerfile named **Dockerfile** in **./two** directory. Then build that with **imgtwo** name and create a container named ***_servic-ename_1** means ***_two_1**. <br/>
```
version: '3'
services:
 one:
   build:
     context: ./one  
   image: imgone
 two:
   build:
     context: ./two  
   image: imgtwo
```
### Example 4 
It will search a dockerfile named **dockerfile.dev** in **./folder** directory. Then build that with **myapache** name and create a container named **myapachecont**.
```
version: '3'
services:
 testservice:
  build:           
    context: ./folder
    dockerfile: dockerfile.dev
  container_name: myapachecont
  image: myapache
```
### Example 5 
It will search a dockerfile named **dockerfile.apache** in **./myapache** directory. Then build that with **myapache** name and create a container named **myapachecont**.
And it **maps the 80 port of container with 80 port of host machine**. Set restart policy with **always**. and map the volume with host volume of **/var/www** with **/var/www** of container.

```
version: '3'
services:
 testservice:
  build: 
    context: ./myapache
    dockerfile: dockerfile.apache
  container_name: myapachecont
  image: myapache
  ports: 
    - 80:80
  restart: always
  volumes:
    - /var/www:/var/www
 ```
 ### Example 6
 It picks up a image called **hello-world** from docker hub. And make a container named **mycon** with it.
 ```
version: '3'
services:
 testservice:
  image: hello-world
  container_name: mycon
```
### Example 7 
 It picks up a image called **httpd** from docker hub. And make a container named **mycon** with it. And it **maps the 80 port of container with 80 port of host machine**. Set restart policy with **always**. and map the volume with host volume of **/var/www** with **/var/www** of container.


```
version: '3'
services:
 testservice:
  container_name: mycon
  image: httpd
  ports: 
    - 80:80
  restart: always
  volumes:
    - /var/www:/var/www
 ```

