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
Hardware: Raspberry Pi 4 - 8 GB <br>
Operating System: Raspbian OS Lite 64-bit <br>
Docker with containerized applications: <br> 
<ol>
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
</ol>
</br>
<h2> Get started </h2> 

`SSH` - Connect to your Pi using Secure Shell (Command prompt) with Hostname or IP address
```
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

`Command 3` - Install Docker Compose Plugin
```
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
```

`Command 4` - You can check if docker is installed correctly
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
`Login` - Login Portainer
</br>
Go to your webbrowser and fill in your Raspberry Pi IP address or Hostname with the Port number.
```
http://192.xxx.x.xx:9000
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
</br>
<h2> Remote acces your applications </h2> 

`Option 1` - VPN <br>
If you have installed WireGuard or another VPN, you can access your local network remotely, including your applications. <br>

`Option 2` - DuckDNS <br>
You can remote access your applications by port forwarding it through DuckDNS. <br>


`Option 3` - Cloudflare <br>
I use Cloudflare to remotely access my applications. It's more secure because it uses HTTPS instead of HTTP, and you don't have to worry about port forwarding. <br>
https://www.youtube.com/watch?v=ZvIdFs3M5ic
<br>