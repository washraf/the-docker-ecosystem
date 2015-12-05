# Copy On Write

The Middleware is responsible for creating and managing the container. When a container is started it appears to have its own Linux files system that you're using. The fact is you don't; at the start of the container it links to files in the base kernel that all containers shared, and the way it handle the changes is via the copy on write model, where each change to the file system is copied to an in memory version of the base file with the changes.

####This results two main effects:
* 
The container will result a small footprint.
* 
changes in memory are faster than writing to storage.

This works in conjunction with UNION File system. Where, each image layer is read-only; this image never changes. When a container is created, Docker builds from the stack of images and then adds the read-write layer on top. That layer, combined with the knowledge of the image layers below it and some configuration data, form the container.
