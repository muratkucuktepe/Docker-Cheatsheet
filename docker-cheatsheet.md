**- Building an image**
```
docker build .   // Build image for current directory
```
---
**- Display processes (containers)**
```
docker ps -a   // Display all containers. ps means process
docker ps      // Display just running containers.
```
---
**- Run container**
```
docker run -p PORT:PORT <image-id-or-name>   // Running a brand new container with an image for the first time and publishing a port. p means publish.
docker start <container-id-or-name>          // Start an existing container.
```
---
**- Stop container**
```
docker stop <container-id-or-name>          // Stop a running container.
```
---
**- Attaching and detaching a container**
```
docker run -p 8000:80 -d <container-id-or-name>   // Run the container in detached mode. d means detached.
docker container attach <container-id-or-name>    // Attach yourself to a detached container again
docker attach <container-id-or-name>              // Attach yourself to a detached container again
docker start -a <container-id-or-name>            // Start the container in attached mode. a means attached
```
---
**- Removing images, containers etc.**
```
docker system prune      // Removes all images, containers, volumes etc.
docker system prune -a   // Removes all UNUSED, NOT RUNNING images, containers, volumes etc.
```
---
**- Display logs**
```
docker logs <container-id-or-name>      // Displays past logs
docker logs -f <container-id-or-name>   // Display logs and keep listening logs for future logs. f means follow
```
