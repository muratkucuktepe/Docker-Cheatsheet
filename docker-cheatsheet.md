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
docker start <image-id-or-name>              // Start an existing container.
```
---
**- Stop container**
```
docker stop <container-id-or-name>          // Stop a running container.
```
---
**- Attaching and detaching a container**
```
docker run -p 8000:80 -d <image-id-or-name>   // Run the container in detached mode. d means detached.
docker container attach <image-id-or-name>    // Attach yourself to a detached container again
docker attach <image-id-or-name>              // Attach yourself to a detached container again
docker start -a <image-id-or-name>            // Start the container in attached mode. a means attached
```
---
**- Removing images, containers etc.**
```
docker system prune      // Removes all images, containers, volumes etc.
docker system prune -a   // Removes all UNUSED, NOT RUNNING images, containers, volumes etc.
```
---
**- Interactive run**
```
docker run -i -t <image-id-or-name>     // 1. Way
docker run -it <image-id-or-name>       // 2. Way
docker start -a -i <image-id-or-name>   // Starts in attached and interactive mode. Start command uses detached mode by default.
```
```
// -t or --tty can be used. This creates a terminal
// -i or --interactive canbe used, namely interactive mode
// It opens up a terminal for interaction. After the interaction is done, it shuts down the container.
```
---
**- Display logs**
```
docker logs <container-id-or-name>      // Displays past logs
docker logs -f <container-id-or-name>   // Display logs and keep listening logs for future logs. f means follow
```
