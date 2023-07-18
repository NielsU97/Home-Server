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

I used <a href="https://community.home-assistant.io/t/rounded-dashboard-guide/543043" target="_blank">Leon's layout</a> for creating the Dashboard.
<br>
<br>
<h2 align="center">
<img src="https://github.com/NielsU97/HomeSmartServer/blob/main/www/Images/hass_mobile_display.png" width="800">
</h2>	
</br>
<h2> Wall Dashboard Example</h2> 
Here i used the same theme as the Mobile Dashboard, but added a side bar using the <a href="https://github.com/DBuit/sidebar-card" target="_blank">custom-sidebar</a>  template.
<br>
<br>
<h2 align="center">
<img src="https://github.com/NielsU97/HomeSmartServer/blob/main/www/Images/hass_home_display.png" width="800">
</h2>	
</br>
<p><a href="https://github.com/NielsU97/HomeDisplay" target="_blank">Klik Here</a> if you want to know how i display the dashboard on a Raspberry Pi</p>
</br>
<h2> MQTT - ITHO Daalderop</h2> 
I added the ITHO Daalderop fan with MQTT using ESP8266 and CC1101.  
<a href="https://community.home-assistant.io/t/guide-controlling-itho-daalderop-fan-with-esp8266-and-cc1101/446808" target="_blank">Klik here</a> for setting up the ESP controller. 
<br>
<br>
If you don't have MQTT installed on your Raspberry Pi,
<a href="https://github.com/NielsU97/Home-Server/tree/main/Mosquitto" target="_blank">klik here</a> for the docker compose file.
<br>
<br>
<h3> Fan pre-set button</h3> 
<h2 align="center">
<img src="https://github.com/NielsU97/HomeSmartServer/blob/main/www/Images/hass_fan_preset_button.gif" width="300">
</h2>	
Install custom button-card in HACS.
<br>
<br>

```
type: grid
square: true
columns: 5
cards:
  - type: custom:button-card
    icon: mdi:fan-off
    aspect_ratio: 1/1
    tap_action:
      action: call-service
      service: fan.set_preset_mode
      service_data:
        preset_mode: 'off'
        entity_id: fan.ecofan
    state:
      - operator: template
        value: |
          [[[
            return states['fan.ecofan'].attributes.preset_mode == "off"
          ]]]
        styles:
          card:
            - border-radius: 24px
            - background-color: var(--red)
          icon:
            - color: var(--black)
  - type: custom:button-card
    icon: mdi:fan-auto
    aspect_ratio: 1/1
    tap_action:
      action: call-service
      service: fan.set_preset_mode
      service_data:
        preset_mode: Auto
        entity_id: fan.ecofan
    state:
      - operator: template
        value: |
          [[[
            return states['fan.ecofan'].attributes.preset_mode == "Auto"
          ]]]
        styles:
          card:
            - border-radius: 24px
            - background-color: var(--green)
          icon:
            - color: var(--black)
  - type: custom:button-card
    icon: mdi:fan-speed-1
    aspect_ratio: 1/1
    tap_action:
      action: call-service
      service: fan.set_preset_mode
      service_data:
        preset_mode: Low
        entity_id: fan.ecofan
    state:
      - operator: template
        value: |
          [[[
            return states['fan.ecofan'].attributes.preset_mode == "Low"
          ]]]
        styles:
          card:
            - border-radius: 24px
            - background-color: var(--green)
          icon:
            - color: var(--black)
  - type: custom:button-card
    icon: mdi:fan-speed-2
    aspect_ratio: 1/1
    tap_action:
      action: call-service
      service: fan.set_preset_mode
      service_data:
        preset_mode: Medium
        entity_id: fan.ecofan
    state:
      - operator: template
        value: |
          [[[
            return states['fan.ecofan'].attributes.preset_mode == "Medium"
          ]]]
        styles:
          card:
            - border-radius: 24px
            - background-color: var(--green)
          icon:
            - color: var(--black)
  - type: custom:button-card
    icon: mdi:fan-speed-3
    aspect_ratio: 1/1
    tap_action:
      action: call-service
      service: fan.set_preset_mode
      service_data:
        preset_mode: High
        entity_id: fan.ecofan
    state:
      - operator: template
        value: |
          [[[
            return states['fan.ecofan'].attributes.preset_mode == "High"
          ]]]
        styles:
          card:
            - border-radius: 24px
            - background-color: var(--green)
          icon:
            - color: var(--black)
``` 
</br>
<h2 align="center"> More information coming soon </h2> 