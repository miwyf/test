

## 1. Introduction
Platform openHAB  (https://www.openhab.org/) is an open source home automation system. Our Wi-Fi energy meter (WEM3080/WEM3080T) can be integrated with openHAB system.



## 2. Highlight 

Our Wi-Fi energy meter has some highlight features comparing to other similar product,

- Bi-directional function enables two-way electricity (for example, "From Grid" and "To Grid") monitoring by only one meter

  [https://www.iammeter.com/doc/iammeter/solar-system.html ](https://www.iammeter.com/doc/iammeter/solar-system.html )

-  Integrated into third party server easily through HTTP, TCP or TLS

  [https://www.iammeter.com/doc/iammeter/integrate-with-thirdparty-server.html](https://www.iammeter.com/doc/iammeter/integrate-with-thirdparty-server.html)

- Support local API calling

  [https://www.iammeter.com/doc/iammeter/integrate-with-PVOutput.html ](https://www.iammeter.com/doc/iammeter/integrate-with-PVOutput.html )

  
## 3. Integrate with openHAB
### 3.1 openHAB settings

 
Step 1, open PAPER UI(HABmin), then install "HTTP Binding" and "JsonPath Transformation".

   ![img](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/openhabwps1.jpg) 

   ![img](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/openhabwps2.jpg)		 

Step 2, open the file openhabconf/services/http.cfg (create file if not exists), and add the below text into the the file. 

```javascript
iammeter.url=http://192.168.12.33/monitorjson{Authorization=Basic YWRtaW46YWRtaW4=}
iammeter.updateInterval=4000
```

​	![img](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/openhabwps3.jpg)			 

​	![img](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/openhabwps4.jpg)	 

Step 3, open the file openhab/conf/items/default.items (create file if not exists), and add the below text into the file,

```javascript
Group     gIammeter				"Meters"				 <energy>        (Home)                    ["GroundFloor"]

Number  Iammeter_Voltage       "Voltage [%0f V]"    	<energy>     	 (gIammeter)				{ http="<[iammeter:4000:JSONPATH($.Data[0])]" }
Number  Iammeter_Current       "Current [%0f A]"   		<energy>    	 (gIammeter)        		{ http="<[iammeter:30000:JSONPATH($.Data[1])]" }
Number  Iammeter_Power         "Power [%0f W]"  		<energy>    	 (gIammeter)            	{ http="<[iammeter:4000:JSONPATH($.Data[2])]" }
Number  Iammeter_Importenergy  "Importenergy [%0f kWh]" <energy>    	 (gIammeter)           		{ http="<[iammeter:30000:JSONPATH($.Data[3])]" }
Number  Iammeter_Exportgrid    "Exportgrid [%0f kWh]"  	<energy>     	 (gIammeter)            	{ http="<[iammeter:30000:JSONPATH($.Data[4])]" }

```

​	![img](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/openhabwps5.jpg)	 

 

Step 4, open the file openhab/conf/sitemaps/default.sitemap (create file if not exists),and add the below text into the file

```javascript
    Frame {
        Text item=Iammeter_Voltage label="Voltage [%.1f V]" icon="energy"
        Text item=Iammeter_Current label="Current [%.1f A]" icon="energy"
        Text item=Iammeter_Power label="Power [%.1f W]" icon="energy"
        Text item=Iammeter_Importenergy label="Importenergy [%.1f kWh]" icon="energy"
    }
```

 

​	![img](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/openhabwps6.jpg)	 

 

## 3.2 View the data on openHAB

 

Step 1, open the Basic UI and you will see the data of the meter.

   ![img](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/openhabwps7.jpg) 

Step 2, you can also add the meter to habpanel.

   ![img](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/openhabwps8.jpg) 

## 4. Purchase the meter

| Model    | Description                            | Purchase Link                                                 |
| -------- | ------------------------------ | ------------------------------------------------------------ |
| WEM3080 | Single phase Wi-Fi energy meter | [Aliexpress](https://www.aliexpress.com/item/10000025757122.html?gps-id=pcStoreJustForYou&scm=1007.23125.137358.0&scm_id=1007.23125.137358.0&scm-url=1007.23125.137358.0&pvid=242ff39d-288e-4a65-ae2d-422d4322f0e6&spm=a2g0o.store_home.smartJustForYou_639729872.0) |
| WEM3080T | Three phase Wi-Fi energy meter | [Aliexpress](https://www.aliexpress.com/item/10000025557485.html?gps-id=pcStoreLeaderboard&scm=1007.22922.122102.0&scm_id=1007.22922.122102.0&scm-url=1007.22922.122102.0&pvid=b0a9b713-410c-420b-a4d3-87cf0ee4f078&spm=a2g0o.store_home.smartLeaderboard_639729876.10000025557485) |



## 5 Reference

1. [Product Catalog](https://www.iammeter.com/doc/iammeter/product-catelogue.html)
2. [FAQ](https://www.iammeter.com/doc/iammeter/FAQ.html)
3. [Integrated in Home Assistant](https://www.iammeter.com/doc/iammeter/homeassistant.html)














