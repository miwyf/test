## 1.Introduction
ioBroker is an IoT platform (Fog computing). It has ability to manage your IoT system as one intelligent, robust project. Our Wi-Fi energy meter (WEM3080/WEM3080T) can be integrated with ioBroker system.


## 2.ioBroker settings
 

### 1.1 Add parser

   ![image-20200416170803091](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/iobrokerimage-20200416170803091.png) 

   ![image-20200416170901638](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/iobrokerimage-20200416170901638.png)
		 

### 1.2 Configure parser

For example your meter IP is 192.168.15.60,

**WEM3080:**

	Name				URL or file name					RegEx							Item	Type	Unit	Interval
	emw3080_voltage			http://admin:admin@192.168.15.60/monitorjson	\[(\d+\.?\d+?),\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\]	0	number	V	60000
	emw3080_current			http://admin:admin@192.168.15.60/monitorjson	\[\d+\.?\d+?,(\d+\.?\d+?),\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\]	0	number	A	60000
	emw3080_power			http://admin:admin@192.168.15.60/monitorjson	\[\d+\.?\d+?,\d+\.?\d+?,(\d+\.?\d+?),\d+\.?\d+?,\d+\.?\d+?\]	0	number	W	60000
	emw3080_ImportEnergy		http://admin:admin@192.168.15.60/monitorjson	\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,(\d+\.?\d+?),\d+\.?\d+?\]	0	number	kWh	60000
	emw3080_exportgrid		http://admin:admin@192.168.15.60/monitorjson	\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,(\d+\.?\d+?)\]	0	number	kWh	60000

**WEM3080T:**	

	Name:	emw3080t_voltage_a			
	URL or file name:	http://admin:admin@192.168.15.60/monitorjson	
	RegEx:	\[\[(\d+\.?\d+?),\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\]\]
	Item:	0		
	Type:	number	
	Unit:	V		
	Interval:	60000
	
	Name:	emw3080t_current_a			
	URL or file name:	http://admin:admin@192.168.15.60/monitorjson	
	RegEx:	\[\[\d+\.?\d+?,(\d+\.?\d+?),\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\]\]
	Item:	0		
	Type:	number	
	Unit:	A		
	Interval:	60000
	
	Name:	emw3080t_power_a			
	URL or file name:	http://admin:admin@192.168.15.60/monitorjson	
	RegEx:	\[\[\d+\.?\d+?,\d+\.?\d+?,(\d+\.?\d+?),\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\]\]
	Item:	0		
	Type:	number	
	Unit:	W		
	Interval:	60000
	
	Name:	emw3080t_ImportEnergy_a			
	URL or file name:	http://admin:admin@192.168.15.60/monitorjson	
	RegEx:	\[\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,(\d+\.?\d+?),\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\]\]
	Item:	0		
	Type:	number	
	Unit:	kWh		
	Interval:	60000
	
	Name:	emw3080t_exportgrid_a			
	URL or file name:	http://admin:admin@192.168.15.60/monitorjson	
	RegEx:	\[\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,(\d+\.?\d+?),\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\]\]
	Item:	0		
	Type:	number	
	Unit:	kWh		
	Interval:	60000
	
	Name:	emw3080t_voltage_b			
	URL or file name:	http://admin:admin@192.168.15.60/monitorjson	
	RegEx:	\[\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[(\d+\.?\d+?),\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\]\]
	Item:	0		
	Type:	number	
	Unit:	V		
	Interval:	60000
	
	Name:	emw3080t_current_b			
	URL or file name:	http://admin:admin@192.168.15.60/monitorjson	
	RegEx:	\[\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,(\d+\.?\d+?),\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\]\]
	Item:	0		
	Type:	number	
	Unit:	A		
	Interval:	60000
	
	Name:	emw3080t_power_b			
	URL or file name:	http://admin:admin@192.168.15.60/monitorjson	
	RegEx:	\[\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,(\d+\.?\d+?),\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\]\]
	Item:	0		
	Type:	number	
	Unit:	W		
	Interval:	60000
	
	Name:	emw3080t_ImportEnergy_b			
	URL or file name:	http://admin:admin@192.168.15.60/monitorjson	
	RegEx:	\[\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,(\d+\.?\d+?),\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\]\]
	Item:	0		
	Type:	number	
	Unit:	kWh		
	Interval:	60000
	
	Name:	emw3080t_exportgrid_b			
	URL or file name:	http://admin:admin@192.168.15.60/monitorjson	
	RegEx:	\[\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,(\d+\.?\d+?),\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\]\]
	Item:	0		
	Type:	number	
	Unit:	kWh		
	Interval:	60000
	
	Name:	emw3080t_voltage_c			
	URL or file name:	http://admin:admin@192.168.15.60/monitorjson	
	RegEx:	\[\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[(\d+\.?\d+?),\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\]\]
	Item:	0		
	Type:	number	
	Unit:	V		
	Interval:	60000
	
	Name:	emw3080t_current_c			
	URL or file name:	http://admin:admin@192.168.15.60/monitorjson	
	RegEx:	\[\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,(\d+\.?\d+?),\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\]\]
	Item:	0		
	Type:	number	
	Unit:	A		
	Interval:	60000
	
	Name:	emw3080t_power_c			
	URL or file name:	http://admin:admin@192.168.15.60/monitorjson	
	RegEx:	\[\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,(\d+\.?\d+?),\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\]\]
	Item:	0		
	Type:	number	
	Unit:	W		
	Interval:	60000
	
	Name:	emw3080t_ImportEnergy_c			
	URL or file name:	http://admin:admin@192.168.15.60/monitorjson	
	RegEx:	\[\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,(\d+\.?\d+?),\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\]\]
	Item:	0		
	Type:	number	
	Unit:	kWh		
	Interval:	60000
	
	Name:	emw3080t_exportgrid_c			
	URL or file name:	http://admin:admin@192.168.15.60/monitorjson	
	RegEx:	\[\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,(\d+\.?\d+?),\d+\.?\d+?,\d+\.?\d+?\]\]
	Item:	0		
	Type:	number	
	Unit:	kWh		
	Interval:	60000



![image-20200417124300352](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/iobrokerimage-20200417124102227.png)


![image-20200416172701159](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/iobrokerimage-20200416172701159.png)

	 
### 1.3 Instances -- parser.0 -- start :

   ![image-20200416171820252](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/iobrokeriobrokerimage-20200416171820252.png)

### 1.4 Objects -- parser.0: 

   ![image-20200416174124401](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/iobrokerimage-20200416174124401.png) 

 

## 3.ioBroker display(Visualisation)

 

### 3.1 Adapters -- Visualisation -- +.

   ![image-20200416174410099](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/iobrokerimage-20200416174410099.png) 

   ![image-20200416174936651](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/iobrokerimage-20200416174936651.png)

   ![image-20200416175115028](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/iobrokerimage-20200416175115028.png)

### 3.2 http://192.168.12.194:8082/vis/edit.html?main#DemoView

   ![image-20200416180640613](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/iobrokerimage-20200416180640613.png) 
   
   ![image-20200416181409670](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/iobrokerimage-20200416181409670.png)
   
   ![image-20200416182221599](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/iobrokerimage-20200416182221599.png)
   
   ![image-20200416182338712](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/iobrokerimage-20200416182338712.png)
   
   ![image-20200416182433346](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/iobrokerimage-20200416182433346.png)
   
   ![image-20200416182524302](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/iobrokerimage-20200416182524302.png)
   
   ![image-20200416182743074](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/iobrokerimage-20200416182743074.png)

 ![image-20200416183427695](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/iobrokerimage-20200416183427695.png)

or you can import widgets:

	[{"tpl":"tplFrame","data":{"visibility-cond":"==","visibility-val":1,"title":"Energy","title_color":"#ffffff","title_top":"0","title_left":"30","header_height":"17","header_color":"#5297ff","name":"Frame Energy","visibility-groups-action":"hide","signals-cond-0":"==","signals-val-0":true,"signals-icon-0":"/vis/signals/lowbattery.png","signals-icon-size-0":0,"signals-blink-0":false,"signals-horz-0":0,"signals-vert-0":0,"signals-hide-edit-0":false,"signals-cond-1":"==","signals-val-1":true,"signals-icon-1":"/vis/signals/lowbattery.png","signals-icon-size-1":0,"signals-blink-1":false,"signals-horz-1":0,"signals-vert-1":0,"signals-hide-edit-1":false,"signals-cond-2":"==","signals-val-2":true,"signals-icon-2":"/vis/signals/lowbattery.png","signals-icon-size-2":0,"signals-blink-2":false,"signals-horz-2":0,"signals-vert-2":0,"signals-hide-edit-2":false,"lc-type":"last-change","lc-is-interval":true,"lc-is-moment":false,"lc-format":"","lc-position-vert":"top","lc-position-horz":"right","lc-offset-vert":0,"lc-offset-horz":0,"lc-font-size":"12px","lc-font-family":"","lc-font-style":"","lc-bkg-color":"","lc-color":"","lc-border-width":"0","lc-border-style":"","lc-border-color":"","lc-border-radius":10,"lc-zindex":0},"style":{"left":"610px","top":"465px","width":"135px","height":"178px","background-color":"#0067d6","font-family":"Arial, sans-serif","z-index":"1","border-radius":"5px"},"widgetSet":"basic"},{"tpl":"tplValueFloat","data":{"oid":"parser.0.emw3080_voltage","visibility-cond":"==","visibility-val":1,"is_comma":"true","factor":"1","html_append_singular":"V","html_append_plural":"V","filterkey":"data","name":"Outside Temperature","visibility-groups-action":"hide","signals-cond-0":"==","signals-val-0":true,"signals-icon-0":"/vis/signals/lowbattery.png","signals-icon-size-0":0,"signals-blink-0":false,"signals-horz-0":0,"signals-vert-0":0,"signals-hide-edit-0":false,"signals-cond-1":"==","signals-val-1":true,"signals-icon-1":"/vis/signals/lowbattery.png","signals-icon-size-1":0,"signals-blink-1":false,"signals-horz-1":0,"signals-vert-1":0,"signals-hide-edit-1":false,"signals-cond-2":"==","signals-val-2":true,"signals-icon-2":"/vis/signals/lowbattery.png","signals-icon-size-2":0,"signals-blink-2":false,"signals-horz-2":0,"signals-vert-2":0,"signals-hide-edit-2":false,"lc-type":"last-change","lc-is-interval":true,"lc-is-moment":false,"lc-format":"","lc-position-vert":"top","lc-position-horz":"right","lc-offset-vert":0,"lc-offset-horz":0,"lc-font-size":"12px","lc-font-family":"","lc-font-style":"","lc-bkg-color":"","lc-color":"","lc-border-width":"0","lc-border-style":"","lc-border-color":"","lc-border-radius":10,"lc-zindex":0},"style":{"left":"626px","top":"496px","width":"105px","height":"17px","z-index":"2","font-family":"Arial, Helvetica, sans-serif","text-shadow":"","color":"#ffffff"},"widgetSet":"basic"},{"tpl":"tplValueFloat","data":{"oid":"parser.0.emw3080_current","visibility-cond":"==","visibility-val":1,"is_comma":"true","factor":"1","html_append_singular":"A","html_append_plural":"A","filterkey":"data","name":"Outside Temperature","visibility-groups-action":"hide","signals-cond-0":"==","signals-val-0":true,"signals-icon-0":"/vis/signals/lowbattery.png","signals-icon-size-0":0,"signals-blink-0":false,"signals-horz-0":0,"signals-vert-0":0,"signals-hide-edit-0":false,"signals-cond-1":"==","signals-val-1":true,"signals-icon-1":"/vis/signals/lowbattery.png","signals-icon-size-1":0,"signals-blink-1":false,"signals-horz-1":0,"signals-vert-1":0,"signals-hide-edit-1":false,"signals-cond-2":"==","signals-val-2":true,"signals-icon-2":"/vis/signals/lowbattery.png","signals-icon-size-2":0,"signals-blink-2":false,"signals-horz-2":0,"signals-vert-2":0,"signals-hide-edit-2":false,"lc-type":"last-change","lc-is-interval":true,"lc-is-moment":false,"lc-format":"","lc-position-vert":"top","lc-position-horz":"right","lc-offset-vert":0,"lc-offset-horz":0,"lc-font-size":"12px","lc-font-family":"","lc-font-style":"","lc-bkg-color":"","lc-color":"","lc-border-width":"0","lc-border-style":"","lc-border-color":"","lc-border-radius":10,"lc-zindex":0},"style":{"left":"626px","top":"525px","width":"100px","height":"17px","z-index":"2","font-family":"Arial, Helvetica, sans-serif","text-shadow":"","color":"#ffffff"},"widgetSet":"basic"},{"tpl":"tplValueFloat","data":{"oid":"parser.0.emw3080_power","visibility-cond":"==","visibility-val":1,"is_comma":"true","factor":"1","html_append_singular":"W","html_append_plural":"W","filterkey":"data","name":"Outside Temperature","visibility-groups-action":"hide","signals-cond-0":"==","signals-val-0":true,"signals-icon-0":"/vis/signals/lowbattery.png","signals-icon-size-0":0,"signals-blink-0":false,"signals-horz-0":0,"signals-vert-0":0,"signals-hide-edit-0":false,"signals-cond-1":"==","signals-val-1":true,"signals-icon-1":"/vis/signals/lowbattery.png","signals-icon-size-1":0,"signals-blink-1":false,"signals-horz-1":0,"signals-vert-1":0,"signals-hide-edit-1":false,"signals-cond-2":"==","signals-val-2":true,"signals-icon-2":"/vis/signals/lowbattery.png","signals-icon-size-2":0,"signals-blink-2":false,"signals-horz-2":0,"signals-vert-2":0,"signals-hide-edit-2":false,"lc-type":"last-change","lc-is-interval":true,"lc-is-moment":false,"lc-format":"","lc-position-vert":"top","lc-position-horz":"right","lc-offset-vert":0,"lc-offset-horz":0,"lc-font-size":"12px","lc-font-family":"","lc-font-style":"","lc-bkg-color":"","lc-color":"","lc-border-width":"0","lc-border-style":"","lc-border-color":"","lc-border-radius":10,"lc-zindex":0},"style":{"left":"626px","top":"553px","width":"103px","height":"17px","z-index":"2","font-family":"Arial, Helvetica, sans-serif","text-shadow":"","color":"#ffffff"},"widgetSet":"basic"},{"tpl":"tplValueFloat","data":{"oid":"parser.0.emw3080_ImportEnergy","visibility-cond":"==","visibility-val":1,"is_comma":"true","factor":"1","html_append_singular":"kWh","html_append_plural":"kWh","filterkey":"data","name":"Outside Temperature","visibility-groups-action":"hide","signals-cond-0":"==","signals-val-0":true,"signals-icon-0":"/vis/signals/lowbattery.png","signals-icon-size-0":0,"signals-blink-0":false,"signals-horz-0":0,"signals-vert-0":0,"signals-hide-edit-0":false,"signals-cond-1":"==","signals-val-1":true,"signals-icon-1":"/vis/signals/lowbattery.png","signals-icon-size-1":0,"signals-blink-1":false,"signals-horz-1":0,"signals-vert-1":0,"signals-hide-edit-1":false,"signals-cond-2":"==","signals-val-2":true,"signals-icon-2":"/vis/signals/lowbattery.png","signals-icon-size-2":0,"signals-blink-2":false,"signals-horz-2":0,"signals-vert-2":0,"signals-hide-edit-2":false,"lc-type":"last-change","lc-is-interval":true,"lc-is-moment":false,"lc-format":"","lc-position-vert":"top","lc-position-horz":"right","lc-offset-vert":0,"lc-offset-horz":0,"lc-font-size":"12px","lc-font-family":"","lc-font-style":"","lc-bkg-color":"","lc-color":"","lc-border-width":"0","lc-border-style":"","lc-border-color":"","lc-border-radius":10,"lc-zindex":0},"style":{"left":"626px","top":"582px","width":"102px","height":"17px","z-index":"2","font-family":"Arial, Helvetica, sans-serif","text-shadow":"","color":"#ffffff"},"widgetSet":"basic"},{"tpl":"tplValueFloat","data":{"oid":"parser.0.emw3080_exportgrid","visibility-cond":"==","visibility-val":1,"is_comma":"true","factor":"1","html_append_singular":"kWh","html_append_plural":"kWh","filterkey":"data","name":"Outside Temperature","visibility-groups-action":"hide","signals-cond-0":"==","signals-val-0":true,"signals-icon-0":"/vis/signals/lowbattery.png","signals-icon-size-0":0,"signals-blink-0":false,"signals-horz-0":0,"signals-vert-0":0,"signals-hide-edit-0":false,"signals-cond-1":"==","signals-val-1":true,"signals-icon-1":"/vis/signals/lowbattery.png","signals-icon-size-1":0,"signals-blink-1":false,"signals-horz-1":0,"signals-vert-1":0,"signals-hide-edit-1":false,"signals-cond-2":"==","signals-val-2":true,"signals-icon-2":"/vis/signals/lowbattery.png","signals-icon-size-2":0,"signals-blink-2":false,"signals-horz-2":0,"signals-vert-2":0,"signals-hide-edit-2":false,"lc-type":"last-change","lc-is-interval":true,"lc-is-moment":false,"lc-format":"","lc-position-vert":"top","lc-position-horz":"right","lc-offset-vert":0,"lc-offset-horz":0,"lc-font-size":"12px","lc-font-family":"","lc-font-style":"","lc-bkg-color":"","lc-color":"","lc-border-width":"0","lc-border-style":"","lc-border-color":"","lc-border-radius":10,"lc-zindex":0},"style":{"left":"626px","top":"610px","width":"101px","height":"17px","z-index":"2","font-family":"Arial, Helvetica, sans-serif","text-shadow":"","color":"#ffffff"},"widgetSet":"basic"},{"tpl":"tplValueFloat","data":{"oid":"parser.0.emw3080_exportgrid","visibility-cond":"==","visibility-val":1,"is_comma":"true","factor":"1","html_append_singular":"kWh","html_append_plural":"kWh","filterkey":"data","name":"Outside Temperature","visibility-groups-action":"hide","signals-cond-0":"==","signals-val-0":true,"signals-icon-0":"/vis/signals/lowbattery.png","signals-icon-size-0":0,"signals-blink-0":false,"signals-horz-0":0,"signals-vert-0":0,"signals-hide-edit-0":false,"signals-cond-1":"==","signals-val-1":true,"signals-icon-1":"/vis/signals/lowbattery.png","signals-icon-size-1":0,"signals-blink-1":false,"signals-horz-1":0,"signals-vert-1":0,"signals-hide-edit-1":false,"signals-cond-2":"==","signals-val-2":true,"signals-icon-2":"/vis/signals/lowbattery.png","signals-icon-size-2":0,"signals-blink-2":false,"signals-horz-2":0,"signals-vert-2":0,"signals-hide-edit-2":false,"lc-type":"last-change","lc-is-interval":true,"lc-is-moment":false,"lc-format":"","lc-position-vert":"top","lc-position-horz":"right","lc-offset-vert":0,"lc-offset-horz":0,"lc-font-size":"12px","lc-font-family":"","lc-font-style":"","lc-bkg-color":"","lc-color":"","lc-border-width":"0","lc-border-style":"","lc-border-color":"","lc-border-radius":10,"lc-zindex":0},"style":{"left":"626px","top":"610px","width":"101px","height":"17px","z-index":"2","font-family":"Arial, Helvetica, sans-serif","text-shadow":"","color":"#ffffff"},"widgetSet":"basic"},{"tpl":"tplValueFloat","data":{"oid":"parser.0.emw3080_ImportEnergy","visibility-cond":"==","visibility-val":1,"is_comma":"true","factor":"1","html_append_singular":"kWh","html_append_plural":"kWh","filterkey":"data","name":"Outside Temperature","visibility-groups-action":"hide","signals-cond-0":"==","signals-val-0":true,"signals-icon-0":"/vis/signals/lowbattery.png","signals-icon-size-0":0,"signals-blink-0":false,"signals-horz-0":0,"signals-vert-0":0,"signals-hide-edit-0":false,"signals-cond-1":"==","signals-val-1":true,"signals-icon-1":"/vis/signals/lowbattery.png","signals-icon-size-1":0,"signals-blink-1":false,"signals-horz-1":0,"signals-vert-1":0,"signals-hide-edit-1":false,"signals-cond-2":"==","signals-val-2":true,"signals-icon-2":"/vis/signals/lowbattery.png","signals-icon-size-2":0,"signals-blink-2":false,"signals-horz-2":0,"signals-vert-2":0,"signals-hide-edit-2":false,"lc-type":"last-change","lc-is-interval":true,"lc-is-moment":false,"lc-format":"","lc-position-vert":"top","lc-position-horz":"right","lc-offset-vert":0,"lc-offset-horz":0,"lc-font-size":"12px","lc-font-family":"","lc-font-style":"","lc-bkg-color":"","lc-color":"","lc-border-width":"0","lc-border-style":"","lc-border-color":"","lc-border-radius":10,"lc-zindex":0},"style":{"left":"626px","top":"582px","width":"102px","height":"17px","z-index":"2","font-family":"Arial, Helvetica, sans-serif","text-shadow":"","color":"#ffffff"},"widgetSet":"basic"},{"tpl":"tplValueFloat","data":{"oid":"parser.0.emw3080_power","visibility-cond":"==","visibility-val":1,"is_comma":"true","factor":"1","html_append_singular":"W","html_append_plural":"W","filterkey":"data","name":"Outside Temperature","visibility-groups-action":"hide","signals-cond-0":"==","signals-val-0":true,"signals-icon-0":"/vis/signals/lowbattery.png","signals-icon-size-0":0,"signals-blink-0":false,"signals-horz-0":0,"signals-vert-0":0,"signals-hide-edit-0":false,"signals-cond-1":"==","signals-val-1":true,"signals-icon-1":"/vis/signals/lowbattery.png","signals-icon-size-1":0,"signals-blink-1":false,"signals-horz-1":0,"signals-vert-1":0,"signals-hide-edit-1":false,"signals-cond-2":"==","signals-val-2":true,"signals-icon-2":"/vis/signals/lowbattery.png","signals-icon-size-2":0,"signals-blink-2":false,"signals-horz-2":0,"signals-vert-2":0,"signals-hide-edit-2":false,"lc-type":"last-change","lc-is-interval":true,"lc-is-moment":false,"lc-format":"","lc-position-vert":"top","lc-position-horz":"right","lc-offset-vert":0,"lc-offset-horz":0,"lc-font-size":"12px","lc-font-family":"","lc-font-style":"","lc-bkg-color":"","lc-color":"","lc-border-width":"0","lc-border-style":"","lc-border-color":"","lc-border-radius":10,"lc-zindex":0},"style":{"left":"626px","top":"553px","width":"103px","height":"17px","z-index":"2","font-family":"Arial, Helvetica, sans-serif","text-shadow":"","color":"#ffffff"},"widgetSet":"basic"},{"tpl":"tplValueFloat","data":{"oid":"parser.0.emw3080_current","visibility-cond":"==","visibility-val":1,"is_comma":"true","factor":"1","html_append_singular":"A","html_append_plural":"A","filterkey":"data","name":"Outside Temperature","visibility-groups-action":"hide","signals-cond-0":"==","signals-val-0":true,"signals-icon-0":"/vis/signals/lowbattery.png","signals-icon-size-0":0,"signals-blink-0":false,"signals-horz-0":0,"signals-vert-0":0,"signals-hide-edit-0":false,"signals-cond-1":"==","signals-val-1":true,"signals-icon-1":"/vis/signals/lowbattery.png","signals-icon-size-1":0,"signals-blink-1":false,"signals-horz-1":0,"signals-vert-1":0,"signals-hide-edit-1":false,"signals-cond-2":"==","signals-val-2":true,"signals-icon-2":"/vis/signals/lowbattery.png","signals-icon-size-2":0,"signals-blink-2":false,"signals-horz-2":0,"signals-vert-2":0,"signals-hide-edit-2":false,"lc-type":"last-change","lc-is-interval":true,"lc-is-moment":false,"lc-format":"","lc-position-vert":"top","lc-position-horz":"right","lc-offset-vert":0,"lc-offset-horz":0,"lc-font-size":"12px","lc-font-family":"","lc-font-style":"","lc-bkg-color":"","lc-color":"","lc-border-width":"0","lc-border-style":"","lc-border-color":"","lc-border-radius":10,"lc-zindex":0},"style":{"left":"626px","top":"525px","width":"100px","height":"17px","z-index":"2","font-family":"Arial, Helvetica, sans-serif","text-shadow":"","color":"#ffffff"},"widgetSet":"basic"},{"tpl":"tplValueFloat","data":{"oid":"parser.0.emw3080_voltage","visibility-cond":"==","visibility-val":1,"is_comma":"true","factor":"1","html_append_singular":"V","html_append_plural":"V","filterkey":"data","name":"Outside Temperature","visibility-groups-action":"hide","signals-cond-0":"==","signals-val-0":true,"signals-icon-0":"/vis/signals/lowbattery.png","signals-icon-size-0":0,"signals-blink-0":false,"signals-horz-0":0,"signals-vert-0":0,"signals-hide-edit-0":false,"signals-cond-1":"==","signals-val-1":true,"signals-icon-1":"/vis/signals/lowbattery.png","signals-icon-size-1":0,"signals-blink-1":false,"signals-horz-1":0,"signals-vert-1":0,"signals-hide-edit-1":false,"signals-cond-2":"==","signals-val-2":true,"signals-icon-2":"/vis/signals/lowbattery.png","signals-icon-size-2":0,"signals-blink-2":false,"signals-horz-2":0,"signals-vert-2":0,"signals-hide-edit-2":false,"lc-type":"last-change","lc-is-interval":true,"lc-is-moment":false,"lc-format":"","lc-position-vert":"top","lc-position-horz":"right","lc-offset-vert":0,"lc-offset-horz":0,"lc-font-size":"12px","lc-font-family":"","lc-font-style":"","lc-bkg-color":"","lc-color":"","lc-border-width":"0","lc-border-style":"","lc-border-color":"","lc-border-radius":10,"lc-zindex":0},"style":{"left":"626px","top":"496px","width":"105px","height":"17px","z-index":"2","font-family":"Arial, Helvetica, sans-serif","text-shadow":"","color":"#ffffff"},"widgetSet":"basic"},{"tpl":"tplFrame","data":{"visibility-cond":"==","visibility-val":1,"title":"Energy","title_color":"#ffffff","title_top":"0","title_left":"30","header_height":"17","header_color":"#5297ff","name":"Frame Energy","visibility-groups-action":"hide","signals-cond-0":"==","signals-val-0":true,"signals-icon-0":"/vis/signals/lowbattery.png","signals-icon-size-0":0,"signals-blink-0":false,"signals-horz-0":0,"signals-vert-0":0,"signals-hide-edit-0":false,"signals-cond-1":"==","signals-val-1":true,"signals-icon-1":"/vis/signals/lowbattery.png","signals-icon-size-1":0,"signals-blink-1":false,"signals-horz-1":0,"signals-vert-1":0,"signals-hide-edit-1":false,"signals-cond-2":"==","signals-val-2":true,"signals-icon-2":"/vis/signals/lowbattery.png","signals-icon-size-2":0,"signals-blink-2":false,"signals-horz-2":0,"signals-vert-2":0,"signals-hide-edit-2":false,"lc-type":"last-change","lc-is-interval":true,"lc-is-moment":false,"lc-format":"","lc-position-vert":"top","lc-position-horz":"right","lc-offset-vert":0,"lc-offset-horz":0,"lc-font-size":"12px","lc-font-family":"","lc-font-style":"","lc-bkg-color":"","lc-color":"","lc-border-width":"0","lc-border-style":"","lc-border-color":"","lc-border-radius":10,"lc-zindex":0},"style":{"left":"610px","top":"465px","width":"135px","height":"178px","background-color":"#0067d6","font-family":"Arial, sans-serif","z-index":"1","border-radius":"5px"},"widgetSet":"basic"}]



![image-20200416183503571](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/iobrokerimage-20200416183503571.png)

 ## 4.Reference

1. [API reference](https://www.iammeter.com/doc/iammeter/integrate-with-PVOutput.html)

2. [integrated in third-party server](https://www.iammeter.com/doc/iammeter/integrate-with-thirdparty-server.html)

3. [FAQ](https://www.iammeter.com/doc/iammeter/FAQ.html)

 

 

 

 
