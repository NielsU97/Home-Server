  <br>
  <h1 align="center">Home Assistant</h1>
  <br>
 <h2 align="center">
<img src="https://github.com/NielsU97/HomeSmartServer/blob/main/www/Images/hass_logo.png" width="200">
  </br>
</br>  
<h2>	
<h3 align="center">Smart Home</h3>                                                                                                                                        
<h2> Install Home Assistant </h2> 
<br>I did not install Home Assistant using Docker Compose. It is possible that Home Assistant cannot be installed via Docker Compose.
</br>
<br>

`Command 1` - Pull image: 
<br>
```
docker pull homeassistant/home-assistant 
``` 
</br>

`Command 2` - Run Docker Container: 
<br>

```
docker run -d \
--name homeassistant \
--privileged \
--restart=unless-stopped \
-e TZ=Europe/Amsterdam \
-v /homeassistant:/config \
--network=host \
ghcr.io/home-assistant/home-assistant:stable
``` 
<h2> Mobile App Dashboard Example</h2> 

I used Leon's layout for creating the Dashboard: https://community.home-assistant.io/t/rounded-dashboard-guide/543043
<br>
<br>
<h2 align="center">
<img src="https://github.com/NielsU97/HomeSmartServer/blob/main/www/Images/hass_mobile_display.png" width="800">
</h2>	
</br>
<h2 align="center"> More information coming soon </h2> 