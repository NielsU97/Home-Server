  <br>
  <h1 align="center">Home Smart Server</h1>
  <br>
 <h2 align="center">
<img src="https://github.com/NielsU97/HomeSmartServer/blob/main/www/Images/docker_setup.png" width="500">
  </br>
</br>  
<h2>	 
<h3 align="center">Running Multiple Applications on a Raspberry Pi</h3>                                                                                                                                      
<h2> System Setup </h2> 
Hardware Raspberry Pi 4 - 8 GB <br>
Operating System: Raspbian OS Lite 64-bit <br>
Docker: <br> 
  - Portainer <br> 
  - Pi-Hole <br> 
  - Home Assistant <br> 
  - Cloudflare <br> 
  - Homer <br> 
  - Mosquitto MQTT <br> 
  - Grafana <br> 
  - Node-red <br> 
  - Wireguard <br> 
  - ... <br> 
</br>
<h2> Get started </h2> 

`SSH` - Connect to your Pi using Secure Shell (Command prompt)
```
# Hostname or IP address
ssh username@hostname

ssh username@192.xxx.x.xx
```
Or use PuTTY instead of command prompt. 

`Command 1` - Check and Update your Pi
```
sudo apt-get update -y
sudo apt-get upgrade -y
```

</br>

<h2> Install Docker </h2> 

`Command 1` - Install Docker
```
curl -sSL https://get.docker.com | sh
```

`Command 2` - Add user to group Docker
```
sudo usermod -aG docker $USER
```

`Command 3` - You can check if docker is installed correctly
```
docker version
docker run hello-world
```
</br>
<h2> Install Portainer </h2> 
With Portainer you can manage you docker containers in a GUI instead of using the commandline <br></br>

`Command 1` - Pull portainer images
```
sudo docker pull portainer/portainer-ce:latest
```

`Command 2` - Run Portainer container
```
sudo docker run -d -p 9000:9000 --name=portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:latest
```
</br>
<h2> Creating docker containers </h2> 

`Option 1` - Using commandline: <br>
Go to the directory where your docker-compose.yaml is located <br>
```
docker compose up
``` 


`Option 2` - Using portainer: <br>
Stacks --> Add stack <br>
Upload your docker-compose.yaml or copy code in Web Editor <br>
<br>

<h3 align="center">For the Docker Compose examples, navigate to the folder of the application you wish to install.</h3>
