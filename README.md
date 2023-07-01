# HomeSmartServer

## System Setup
Hardware Raspberry Pi 4 - 8 GB
Operating System: Raspbian OS Lite 64-bit
Docker:
  - Portainer
  - Pi-Hole
  - Home Assistant
  - Cloudflare
  - Homer
  - Mosquitto MQTT
  - Grafana
  - Node-red
  - Wirequard

### Install Docker
``curl -sSL https://get.docker.com | sh``
``sudo usermod -aG docker $USER``

You can check if docker is installed correctly
``docker version``
``docker run hello-world``

### Install Portainer
With Portainer you can manage you docker containers in a GUI instead of using the commandline
``sudo docker pull portainer/portainer-ce:latest``
``sudo docker run -d -p 9000:9000 --name=portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:latest``

### Creating docker containers
Using commandline:
Go to the directory where your docker-compose.yaml is located
``docker compose up``

Using portainer:
Stacks --> Add stack
Upload your docker-compose.yaml or copy code in Web Editor
