[Purchase the meter on e-Store](https://devicebit-iot.aliexpress.com/)

https://www.home-assistant.io/integrations/iammeter/

## 1. Introduction

HomeAssistant (https://www.home-assistant.io/) is an open source home automation system. Our WiFi energy meter (WEM3080/WEM3080T) can be integrated with HomeAssistant system. 

![img](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter-ha-20200312-1.jpg)            


## 2. Integrate with HomeAssistant

### 2.1 Install HA software
Install the latest version of Home Assistant (0.107.0.dev20200310 or later version)

![](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter-ha-20200312-2.jpg)
       

### 2.2  Configuration

To use the Iammeter sensors in your installation, add the following to your `configuration.yaml` file:

   ```yaml
   # Example configuration.yaml entry
   sensor:
     - platform: iammeter
       host: 192.168.1.6
       name: meter
   ```
![](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter-ha-20200312-3.jpg)

>> **Tips:** You can find your meter and check its host IP address by double clicking its icon in the network of your PC which is connected to the same home Wi-Fi network
![Network](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter-31-20190809-L5.jpg)
    
### 2.3 Find your meter in HA 
Restart the server manangement and reconnect to it, then you will see the entity of the meter if the meter is already connected to the internet.

![](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter-ha-20200312-4.jpg)       

![](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter-ha-20200312-5.jpg)

  ### 2.4 Sensors

   Sensors available in the library:

   - **Single Phase WiFi Energy Meter (WEM3080)**

   | name                 | Unit | Description                  |
   | -------------------- | ---- | ---------------------------- |
   | wem3080_voltage      | V    | Voltage.                     |
   | wem3080_current      | A    | current.                     |
   | wem3080_power        | W    | active power.                |
   | wem3080_importenergy | kWh  | Energy consumption from gird |
   | wem3080_exportgrid   | kWh  | Energy export to grid        |

   - **Three Phase WiFi Energy Meter (WEM3080T)**

   | name                    | Unit | Description           |
   | ----------------------- | ---- | --------------------- |
   | wem3080t_voltage_a      | V    | A phase voltage       |
   | wem3080t_current_a      | A    | A phase current       |
   | wem3080t_power_a        | W    | A phase active power  |
   | wem3080t_importenergy_a | kWh  | A phase import energy |
   | wem3080t_exportgrid_a   | kWh  | A phase export energy |
   | wem3080t_frequency_a    | kWh  | A phase frequency     |
   | wem3080t_pf_a           | kWh  | A phase power factor  |
   |                         |      |                       |
   | wem3080t_voltage_b      | V    | B phase voltage       |
   | wem3080t_current_b      | A    | B phase current       |
   | wem3080t_power_b        | W    | B phase active power  |
   | wem3080t_importenergy_b | kWh  | B phase import energy |
   | wem3080t_exportgrid_b   | kWh  | B phase export energy |
   | wem3080t_frequency_b    | kWh  | B phase frequency     |
   | wem3080t_pf_b           | kWh  | B phase power factor  |
   |                         |      |                       |
   | wem3080t_voltage_c      | V    | C phase voltage       |
   | wem3080t_current_c      | A    | C phase current       |
   | wem3080t_power_c        | W    | C phase active power  |
   | wem3080t_importenergy_c | kWh  | C phase import energy |
   | wem3080t_exportgrid_c   | kWh  | C phase export energy |
   | wem3080t_frequency_c    | kWh  | C phase frequency     |
   | wem3080t_pf_c           | kWh  | C phase power factor  |

### 2.5 Edit your lovelace

![](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter-ha-20200312-6.jpg)       

![](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter-ha-20200312-7.jpg)
   ​           

  Here you can add the card manually

![](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter-ha-20200312-8.jpg)       
  
Or you can copy and paste the following code

![](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter-ha-20200312-9.jpg)        

   ```yaml
   cards:
     - cards:
         - entity: sensor.meter_voltage
           max: 300
           min: 100
           name: voltage
           theme: default
           type: gauge
         - entity: sensor.meter_power
           max: 5000
           min: 0
           name: power
           theme: default
           type: gauge
       type: horizontal-stack
     - entities:
         - entity: sensor.meter_voltage
           name: voltage
         - entity: sensor.meter_power
           name: power
         - entity: sensor.meter_importenergy
           name: importenergy
         - entity: sensor.meter_exportgrid
           name: exportgrid
       type: glance
     - entities:
         - entity: sensor.meter_power
         - entity: sensor.meter_voltage
         - entity: sensor.meter_importenergy
       hours_to_show: 24
       refresh_interval: 0
       type: history-graph
   type: vertical-stack
   ```
Save and then you will see the meter's data.

![](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter-ha-20200312-10.jpg)
     
## 3. Reference

- **QuickStart document  of single phase WiFi Energy Meter (WEM3080):** [WEM3080 Quickstart](https://www.iammeter.com/doc/iammeter/wem3080-quickstart.html)

![](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/WEM3080.png)

- **QuickStart document  of three phase WiFi Energy Meter (WEM3080T):** [WEM3080T Quickstart](https://www.iammeter.com/doc/iammeter/wem3080t-quickstart.html)

![](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/WEM3080T.jpg)



