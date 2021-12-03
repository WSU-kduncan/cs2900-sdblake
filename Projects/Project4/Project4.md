### **Project 4**

---

#### Investigate container networking
- #### **Docker**
  - Networking Modes: **Host** - Network stack isn't isolated from the host, and the container doesn't get it's own IP address. It can be helpful with performance optimization. **None**  - This disables all networking and is typically used in custom network drivers. **Bridge** - This is the default mode for docker and is usually set when you dont specify a driver and/or your applications run inside standalone containers. 
  - Defualt Mode: Bridge
  - How to run container and bind a host: Using the command "docker run -p 80:8080 nginx" you can run the container and bind the host port (80) to the container port (8080).
 
- #### **Podman**
  - Networking Modes: Podman uses the same 3 main modes as Docker does; Bridge, Host, and None. It has a few other extras but it seems that these are the only main ones that are used. Others are priavte, slirp4netns, and ns. **Bridge** creates the network stack on the default bridge network, **None** is no networking at all and **Host** just uses the host's network stack. **Private** simply creates a new network namespace for the specified container. 
  - Default Mode: Bridge
  - How to run container and bind a host: To run the container and bind the host and container ports, you would use roughly the same command as docker, "podman run -p 8080:80" for an example. 

#### Investigate Vulnerability Scanners
  - Dockerfile linter: Using Hadolint, which is a popular open source tool for Dockerfiles that reads steps and provides suggestions about the structure of files. Using "hadolint Dockerfile-initial" will run this command. An example I found is that it will state the using COPY instead of ADD for files or to use WORKDIR to switch to a directory. 
  - Aqua Trivy: Trivy scans for vulnerabilites in container images, file systems, and configuration issues.It detects vulnerabilites of OS packages and application dependencies. From my research and what I've read, I cannot find any limits to what it can scan. As far as I can tell it may not be super efficient or fast enough for business critical applications or more complex architectures. 
