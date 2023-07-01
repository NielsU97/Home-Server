# HomeSmartServer
I have a Raspberry Pi that serves multiple purposes, including functioning as a VPN server, Smart Home, providing local network adblocking, and much more. <br> <br>

I use Docker to run all these different applications. By using Docker, I can seamlessly manage and deploy various software components while ensuring their isolation and portability. Docker enables me to streamline the execution of these different applications, allowing for efficient resource utilization and simplified maintenance. <br> <br>

Docker is an open-source platform that allows you to automate the deployment, scaling, and management of applications using containerization. It provides a lightweight, isolated environment called a container, which contains all the dependencies and libraries required for an application to run consistently across different systems. Docker simplifies the process of packaging software and its dependencies into standardized units, making it easier to deploy and run applications in various computing environments. <br> <br>

## System Setup
Hardware Raspberry Pi 4 - 8 GB <br>
Operating System: Raspbian OS Lite 64-bit <br>
Docker:
  - Portainer
  - Pi-Hole
  - Home Assistant
  - Cloudflare
  - Homer
  - Mosquitto MQTT
  - Grafana
  - Node-red
  - Wireguard

### Install Docker
``curl -sSL https://get.docker.com | sh`` <br>
``sudo usermod -aG docker $USER`` <br>

You can check if docker is installed correctly <br>
``docker version`` <br>
``docker run hello-world`` <br>

### Install Portainer
With Portainer you can manage you docker containers in a GUI instead of using the commandline <br>
``sudo docker pull portainer/portainer-ce:latest`` <br>
``sudo docker run -d -p 9000:9000 --name=portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:latest`` <br>

### Creating docker containers
Using commandline: <br>
Go to the directory where your docker-compose.yaml is located <br>
``docker compose up`` <br>

Using portainer: <br>
Stacks --> Add stack <br>
Upload your docker-compose.yaml or copy code in Web Editor <br>
