### **Project 3**

---

#### Investigate Available Mounts
- #### **Docker**
  - Available Mounts: There are currently 3 types of mounts you can use inside the docker container. 
Volumes, tmpfs (temporary), and Bind Mounts are the three types of mounts on docker. Volumes are managed
by the docker engine and can be shared between docker containers. TMPFS mounts are only on the container until
it is stopped, at the point the data will be lost. Bind Mounts are host machine files which mount
onto the container with only the host machine managing it.
  - How to use Mount Types: To create a volume mount, use the command "docker volume create my-vol",
To inspect it, use "docker volume inspect my-vol". To create a tmpfs mount you would only need to add 
the --tmpfs flag. For Bind Mount usage, you will be using -v or volume. Since this is mounted to another
container you will basically be storing things on two systems. Using "iv" combines options when creating
a mount. To bind different containers you will just need to implement "type=bind" when running docker.

- #### **Podman**
  - Available Mounts: bind, volume, image, tmpfs, and devpts. The default mount option for podman is bind,
which means an unknown named volume will be created and mounted into the container  when creating the 
first one. Image mounts will mount the specified image's filesystem, which can be accessed by the host machine,
and returns that specific location of the image. TMPFS allows the user to create content that is gone when
the container is stopped. Devpts is basically a virtual filesystem directory and is implemented by chanigng
the type to devpts, just like you would with image or volume mounts. 
  - How to use Mount Types: To create these mount types it is the same as you would in docker. You would just
change the "type=mounttype" to whichever one satisfies your need for the container. Below is an image from
"docs.podman.io" and shows some examples of these commands. You would implement these when you go to run your 
container. You will need to specify the source and destination of the container you are using as well.
  - ![image](https://user-images.githubusercontent.com/59904812/139154965-bb05498e-577b-4db7-b215-9341c05b2a59.png)

#### Investigate building images for container engines
- #### **Docker**
  - Build an image: Docker does include a command to build an image. By using "docker build [OPTIONS] PATH [URL] - ", it will build a docker image from a dockerfile.
An example is "docker build -t shykes/myapp:1.0.2" This grabs the file from a Git URL. 
  - How to write a build file: (Note that this is an example and the commands should be on their own separate lines
FROM ubuntu:18.04 , COPY . /app , RUN make /app , CMD python /app/app.py
FROM will specify the parent image, COPY will copy new files or directories from the source and add them to the filesystem, RUN will just run the command, and CMD will specify
what command to run within the container.

- #### **Podman**
  - Build an image: Podman also includes a command to build an image. You can use podman image build [options] [context]
  - Podmans build command contains a subset of Buildah functionality. You can use something in a similar format to Buildah, "podman pull fedora:latest"
"podman run -it fedora bash". Using the podman push and pull commands will allow you to move images from /var/lib/docker to the /var/lib/containers directory.
