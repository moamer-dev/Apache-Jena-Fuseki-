## Apache Jena Fuseki on Docker

##### Install [Apache Jena Fuseki](https://jena.apache.org/documentation/fuseki2/) as a [Docker container](https://hub.docker.com/r/stain/jena-fuseki) on TIB test server.

- Fuseki version: 4.1.0
- Docker version: 20.10.21

##### Requirements to run the Fuseki server:
- [Docker](https://docs.docker.com/engine/install/ubuntu/).
- [stain/jena-fuseki](https://hub.docker.com/r/stain/jena-fuseki).

#### Install Docker Engine on Linux.

Using the terminal: 
- Update the apt package index:
```
 sudo apt-get update
```
- Install Docker Engine, containerd, and Docker Compose.
``` 
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
```
- Verify that the Docker Engine installation is successful by running the hello-world image:<br>
*This command downloads a test image and runs it in a container. When the container runs, it prints a confirmation message and exits.*
```
sudo docker run hello-world
```
You have now successfully installed and started Docker Engine.
<br>

--------------------------------------------------------------------------------------------------------------------------------------

#### Install Apache Jena Fuseki 2: SPARQL 1.1 server with web UI, backed by Apache Jena's TDB triple store.

Using the terminal: 
- Install Jena Fuseki Image:
```
sudo docker run -p 3030:3030 stain/jena-fuseki
```
This command will generate a random password and displays it on terminal, so you have to save it.<br>
You can now using Fuseki by going to this link ```http(s)://{your server}/3030```<br>
##### Login credentials: 
- username: ```admin```
- password: ```{generated password}```

To expose Fuseki on a different port, simply modify first part of ```-p```:
```
sudo docker run -p 8080:3030 stain/jena-fuseki
```
You can override the admin-password using the form ```-e ADMIN_PASSWORD=pw123```:
```
sudo docker run -p 3030:3030 -e ADMIN_PASSWORD=pw123 stain/jena-fuseki
```
##### Login credentials: 
- username: ```admin```
- password: ```pw123```
