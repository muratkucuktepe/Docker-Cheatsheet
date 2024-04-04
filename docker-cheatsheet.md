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
**- List images**
```
docker images   // Lists all images
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
docker stop <container-id-or-name>   // Stop a running container.
```
---
**- Attaching and detaching a container**
```
docker run -p 8000:80 -d <image-id-or-name>       // Run the container in detached mode. d means detached.
docker container attach <container-id-or-name>    // Attach yourself to a detached container again
docker attach <container-id-or-name>              // Attach yourself to a detached container again
docker start -a <container-id-or-name>            // Start the container in attached mode. a means attached
```
---
**- Removing images, containers etc.**
```
docker system prune      // Removes unused containers, networks, and dangling images (images built but not referenced by any containers).
docker rm <container-id-or-name>                               // Remove one container
docker rm <container-id-or-name> -f                            // Remove a container with force. f means force
docker rm <container-id-or-name> <container-id-or-name> etc.   // Remove multiple containers at once
docker rmi <image-id-or-name>                                  // Remove one image
docker rmi <image-id-or-name> <image-id-or-name> etc.          // Remove multiple images at once
docker image prune                                             // Remove all unused images
docker image prune -a                                          // Remove all unused images including names and tags
docker run -p 3000:80 -d -rm <image-id-or-name>                // Automatically removes container if it exits. rm means remove
```
---
**- Interactive run**
```
docker run -i -t <image-id-or-name>     // 1. Way
docker run -it <image-id-or-name>       // 2. Way
docker start -a -i <container-id-or-name>   // Starts in attached and interactive mode. Start command uses detached mode by default.
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
---
**- Inspecting images**
```
docker image inspect <image-id-or-name>
```
---
**- Copying files from & into containers**
```
docker cp <source-directory> <container-name>:<destination-directory>
// Ex: docker cp dummy/. boring_vaughan:/test   // Copy from the folder dummy everything into container boring_vaughan into test folder.
// Ex: docker cp boring_vaughan:/test dummy     // Copy from the container into dummy folder.
```
---
**- Tagging and naming containers and images**
```
docker run -p 3000:80 -d -rm --name myCustomName <image-id-or-name>   // Naming a container
docker build -t nameOfTheImage:customTag                              // Naming and tagging an image
```
---
**- Renaming images**
```
docker tag <old-name> <new-name>   // Rename an image. This does NOT delete old one. It creates a clone.
// Ex: docker tag node-demo:latest myDockerHubAccount/myCustomImage 
```
---
**- Logging in and out**
```
docker login   // This asks username and password afterwards.
docker logout 
```
---
**- Pulling and pushing images**
```
docker push imageName/imageTag
docker pull imageName/imageTag   // This pulls always latest
docker run imageName/imageTag    // This pull automatically if the image is not available locally.
```
---
**- Volumes**
```
docker volume ls                      // Listing all volumes
docker volume rm <volume-name>        // 1. Way: Clear unused anonymous volumes   
docker volume prune                   // 2. Way: Clear unused anonymous volumes
docker volume create <volume-name>    // Create a named volume
docker volume inspect <volume-name>   // Inspecting a volume
docker volume rm <volume-name>        // Remove a volume. If it is used in a container, you can not remove it. Removing volume removes data as well.
docker volume prune                   // Removes unused volumes
```
```
// Summary
docker run -v app/data...                  // Anonymous volume
docker run -v data:/app/data...            // Named volume
docker run -v /path/to/code:/app/code...   // Bind mounts
```
```
// READ-ONLY volumes
// By default volumes are read and write
// This means container can not change your source code in your IDE
docker run -v /path/to/code:/app/code:ro   // Bind mounts into read only
```
