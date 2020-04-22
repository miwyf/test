
## 1. Introduction
PVOutput is a free service for sharing and comparing live solar panel output and energy consumption data. By installing our WiFi energy meter in your solar system, you can easily integrate your PV data to PVOutput through the meter's open API.

## 2. Key features of WiFi energy meter

- Measure bi-directional (from grid and to grid) power and energy by same meter
- The meter's measurement can be read via WiFi LAN thourgh open API 
- The meter's readings (voltage, current, power, forward power, reverse power) are refreshed every 20 seconds.

## 3. Code examples

### 3.1 API description

api url: ip/monitorjson

method: http get

![](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iMeter20190903-1.jpg)


## 3.2 Python code example 

[Python Code on Github](https://github.com/lewei50/iammeter/blob/master/wem.py)


~~~
import requests
 
url = "http://ip/monitorjson" 
 
headers={'Authorization':'Basic YWRtaW46YWRtaW4='}
 
response = requests.request("get", url, headers=headers)
 
print(response.text)
~~~


{"status":"succeed","data":[234.00,6.235,1423,1222.67,0.00]}


voltage:234 V

current:6.25 A

active power:1433 W

import energy:1222.67 Kwh

export energy:0 Kwh



## 4. Integrate the data to PVOutput

PVOutput:[https://www.pvoutput.org](https://www.pvoutput.org)
Github Link: [https://github.com/lewei50/iammeter/](https://github.com/lewei50/iammeter/)

~~~
import wem
import PVOutput
import json
meter=wem.wem3162('http://192.168.1.8')
'''
one phase(wem3162 wem3080) meter response
{"status":"succeed","data":[235.00,1.214,189,1265.17,0.00]} 
'''

print (meter.monitorjson())
(vol,cur,power,importE,exportE)=meter.json2parameter()
print ("vol:%dV\r\ncur:%fA\r\npower:%dw\r\nimportEnergy:%fKWH\r\nexportEnergy:%fKWH\r\n"%(vol,cur,power,importE,exportE))
pv=PVOutput.PVOutputApi('siteNumber','api-key')

'''
#pvo = PVOutput.PVOutputApi("deviceId", "apiKey")
#pvo.add_status(
energy_generation,
power_generation,
energy_consumption,
power_consumption,
temperature,
voltage,
cumulative_flag,
net_flag)
#pvo.add_status(100,200,None,None,None,None,None,None)
'''

pv.add_status(importE,power,None,None,None,vol,1,None)
~~~


**QuickStart document  of single phase WiFi Energy Meter (WEM3080):** [WEM3080 Quickstart](https://www.iammeter.com/doc/iammeter/wem3080-quickstart.html)

![](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/WEM3080.png)

**QuickStart document  of three phase WiFi Energy Meter (WEM3080T):** [WEM3080T Quickstart](https://www.iammeter.com/doc/iammeter/wem3080t-quickstart.html)

![](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/WEM3080T.jpg)

**How to apply the WiFi Energy Meter in a Solar System:**[Apply in Solar System](https://www.iammeter.com/doc/iammeter/solar-system.html)

### Note

If you have a WeChat account, please follow our IAMMETER WeChat public ID.

![iammeter.jpg](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter-20181103-1.jpg)
