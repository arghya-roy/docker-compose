### example 1 
It will search a dockerfile named **Dockerfile** in present working directory. Then build that with a random name and create a container named ***_service-name_1**.
```
version: '3' 
services: 
 one: 
   build: .  # it will search a dockerfile named Dockerfile in present working directory. Then build that with a random name and create a container named *_service-name_1.
```


### example 2 
It will search a dockerfile named **Dockerfile** in **./one** directory. Then build that with **imgone** name and create a container named ***_servic-ename_1**.
```
version: '3'
services:
 one:
   build:
     context: ./one  # It will search a dockerfile named Dockerfile in ./one directory. Then build that with imgone name and create a container named *_servic-ename_1. 
   image: imgone
```

### example 3
**First service -** It will search a dockerfile named **Dockerfile** in **./one** directory. Then build that with **imgone** name and create a container named ***_servic-ename_1**. <br/>
**Second service -** It will search a dockerfile named **Dockerfile** in **./two** directory. Then build that with **imgtwo** name and create a container named ***_servic-ename_1**. <br/>
```
version: '3'
services:
 one:
   build:
     context: ./one  # It will search a dockerfile named Dockerfile in ./one directory. Then build that with imgone name and create a container named *_servic-ename_1. 
   image: imgone
 two:
   build:
     context: ./two  # # It will search a dockerfile named Dockerfile in ./two directory. Then build that with imgtwo name and create a container named *_servic-ename_1.
   image: imgtwo
```
