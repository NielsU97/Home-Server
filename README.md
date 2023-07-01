# HomeSmartServer

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
  - Wirequard

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
