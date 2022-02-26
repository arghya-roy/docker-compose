### example 1 
```
version: '3' 
services: 
 one: 
   build: .  # it will search a dockerfile named **Dockerfile** in present working directory. Then build that with a random name and create a container named ***_service-name_1**
```


### example 2 
```
version: '3'
services:
 one:
   build:
     context: ./one   # 
   image: imgone
 two:
   build:
     context: ./two
   image: imgtwo
```
