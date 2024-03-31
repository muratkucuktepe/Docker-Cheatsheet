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
docker run -p PORT:PORT <image-id-or-name>   // Running an image and publishing a port. p means publish.
```
---
**- Removing images, containers etc.**
```
docker system prune      // Removes all images, containers, volumes etc.
docker system prune -a   // Removes all UNUSED, NOT RUNNING images, containers, volumes etc.
```
