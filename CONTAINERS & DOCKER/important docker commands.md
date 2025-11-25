
When working with Docker, images and containers pile up quickly. If you don’t manage them, your system gets messy, slow, and takes up too much space. These commands help you **list, inspect, stop, remove, and clean** your Docker environment.

**See images you have**

`docker images`

- Shows all local images with details (repo, tag, ID, size, date).
- Useful to track versions and find what you can delete.
**Inspect an image deeply**
docker inspect <image_id>
- this command gives full details (config, env vars, layers, etc.).
**Remove an image**
docker rmi <image_id>
- Deletes an image.
- Won’t work if the image is in use by a container → stop/remove container first.
**Clean everything unused (safe big cleanup)**
docker system prune
-  Removes **all** stopped containers, unused networks, dangling images, and build cache.
- Great for freeing space after development/testing.
docker ps 
* Shows containers currently running.
**Stop a container**
docker stop <container_id>
- Stops a running container.
- Can pass multiple IDs to stop several at once
**Remove a container**
docker rm <container_id>
* * Permanently deletes a stopped container to free resources.
