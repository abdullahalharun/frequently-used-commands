## IMAGES  
Docker images are a lightweight, standalone, executable package
of software that includes everything needed to run an application:
code, runtime, system tools, system libraries and settings.  

Build an Image from a Dockerfile  
`docker build -t <image_name>`  

Build an Image from a Dockerfile without the cache  
`docker build -t <image_name> . –no-cache`  

List local images  
`docker images`  

Delete an Image  
`docker rmi <image_name>`  

Remove all unused images  
`docker image prune`

Docker compose up & down  
`docker-compose -f docker-compose.yml down` 

Down & remove volumes  
`docker-compose -f docker-compose.yml up -d` 

Docker compose build with no cache  
`docker-compose -f docker-compose.yml build --no-cache`

Docker compose Up  
`docker-compose -f docker-compose.yml up -d`
