### BLUE/GREEN DEPLOYMENT WITH DOCKER & NGINX 

---
#### PROJECT DESCRIPTION
    Deploying a Blue/Green Nodejs service behind Nginx using pre-built container images.

### Components
- app_blue → The active environment
- app_green → The backup environment
- nginx_bluegreen → The 
reverse proxy that routes traffic to the active environment.

#### COMMANDS TO RUN
- To orchestrate nginx, app_blue, app_green, I ran:
```bash
docker compose up -d
```

- To check if my containers are up and running, I went ahead to run
```bash
docker ps 
```
When I saw that my containers are up and running, I run the command:
```bash
curl http://localhost:8080/version
```
to check if my nginx is connected to my app, and to know if nginx is already showing your app content.
After it has been tested and it works perfectly well, I went ahead and push my project to Github.
- SSH into my instance
- Update, Upgarde, Install docker and docker compose
```bash
sudo apt-get update
sudo apt upgrade
sudo apt install docker.io
sudo apt install docker compose -y 
```
- Clone the Repository into my EC2 instance
```bash
git clone https://github.com/E335-comma/Blue-Green-Deployment.git
```

- Change Directory
```bash
cd Blue-Green-deployment
```
-Start the containers
```bash
docker compose up -d
```

- Check running containers
```bash
docker ps
```
- To check the release_id, app_bool,  I ran 
```bash
curl -i http://localhost:8080/version
```
- I tested locally
```bash
curl http://localhost:8080
```
It shows the app content.
- I ensured port 8080 is opened in my security group
- Test using server public IP
```bash
curl http://18.237.101.146:8080




