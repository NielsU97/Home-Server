  <br>
  <h1 align="center">Pi-Hole</h1>
  <h2 align="center">Docker Compose</h2>
  <br>
 <h2 align="center">
<img src="https://github.com/NielsU97/HomeSmartServer/blob/main/www/Images/pihole_example.png" width="500">
  </br>
</br>  
<h2>	   
<h3 align="center">Network-wide ad blocking</h3>                                                                                                                                      
<h2> Compose file </h2> 
Edit the compose file to your needs. For example where the config folder is located, password, et cetera. 
<br>
<br> 
More information about Pi-Hole Docker: https://github.com/pi-hole/docker-pi-hole/
<br>and information about Pi-Hole it self: https://docs.pi-hole.net/ 
</br>
<br>               
<h2> Creating the docker container </h2> 

`Option 1` - Using commandline: 
<br>
Go to the directory where your docker-compose.yaml is located 
<br>
```
docker compose up
``` 

`Option 2` - Using portainer: 
<br>
Stacks --> Add stack 
<br>
Upload your docker-compose.yaml or copy code in Web Editor 
<br>
<br>
<h2> Login to Pi-Hole Dashboard</h2> 

When installed go to your web browser and fill in your Raspberry Pi IP address or Hostname with admin. 
<br>
```
http://192.168.X.XXX/admin
http://Hostname/admin
``` 
You can login with the password you created in the compose file.
<br> 
<img src=https://github.com/NielsU97/HomeSmartServer/blob/main/www/Images/pihole_login.png width="500"> 
<br> 
<br>
<h2> Using Pi-Hole  </h2> 

`Option 1` - Network wide 
<br>
To block ads on your network, follow these steps:

    1. Log in to your router's administration panel.
    2. Locate the DNS settings section.
    3. Enter your Raspberry Pi's IP address as the primary DNS.
    4. Repeat step 3, entering the same IP address as the secondary DNS.
    5. Save the changes.

By configuring your router with your Raspberry Pi's IP address as the primary and secondary DNS, all DNS requests on your network will be routed through Pi-Hole. Once the changes are saved, ads should be blocked on all devices connected to your network.
<br>
<img src=https://github.com/NielsU97/HomeSmartServer/blob/main/www/Images/pihole_router.png width="700"> 
<br>
<br>
`Option 2` - Device 
<br>
Instead of ad-blocking network-wide, you can also set it separately on your devices, such as your phone.
<br>
<img src=https://github.com/NielsU97/HomeSmartServer/blob/main/www/Images/pihole_device.png width="200"> 
<br>
<h3 align="center">For Pi-Hole blocklists klik <a href="https://firebog.net/" target="_blank">Here</a></p> 
</h2>	</h3>