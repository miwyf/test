## 1. Introduction

Node-RED is a programming tool for wiring together hardware devices, APIs and online services in new and interesting ways.
Our Wi-Fi energy meter (WEM3080/WEM3080T) can be integrated with Node-Red system.


## 2. Node-RED settings

 

Step 1, open Node-RED, then import the flowing code to new flow:

   ```json
   [{"id":"d3cdff25.7e38","type":"tab","label":"IamMeter","disabled":false,"info":""},{"id":"d1a8ac7f.855a1","type":"inject","z":"d3cdff25.7e38","name":"","topic":"","payload":"","payloadType":"date","repeat":"60","crontab":"","once":false,"onceDelay":0.1,"x":142,"y":333,"wires":[["e393add.ec73f5"]]},{"id":"da96de90.da3b5","type":"debug","z":"d3cdff25.7e38","name":"","active":true,"tosidebar":true,"console":false,"tostatus":false,"complete":"true","targetType":"full","x":634,"y":65,"wires":[]},{"id":"b6c9827e.6a018","type":"ui_text","z":"d3cdff25.7e38","group":"21ee6458.a3032c","order":2,"width":0,"height":0,"name":"voltage","label":"voltage","format":"{{msg.payload}}V","layout":"row-spread","x":855.5,"y":92,"wires":[]},{"id":"264bf1ac.4074fe","type":"function","z":"d3cdff25.7e38","name":"EMW3162","func":"let dataArr = msg.payload.data;\n\nlet result = [];\nfor(var item in dataArr) {\n    result.push({\n        payload: dataArr[item]\n    });\n}\n\nreturn result;","outputs":5,"noerr":0,"x":672,"y":171,"wires":[["b6c9827e.6a018"],["7ed17cb4.385654"],["cac3c7fc.fef2d8"],["b60363db.e6117"],["1e4aa427.f2aecc"]]},{"id":"7ed17cb4.385654","type":"ui_text","z":"d3cdff25.7e38","group":"21ee6458.a3032c","order":3,"width":0,"height":0,"name":"current","label":"current","format":"{{msg.payload}}A","layout":"row-spread","x":855,"y":131,"wires":[]},{"id":"cac3c7fc.fef2d8","type":"ui_text","z":"d3cdff25.7e38","group":"21ee6458.a3032c","order":4,"width":0,"height":0,"name":"power","label":"power","format":"{{msg.payload}}W","layout":"row-spread","x":846,"y":168,"wires":[]},{"id":"b60363db.e6117","type":"ui_text","z":"d3cdff25.7e38","group":"21ee6458.a3032c","order":5,"width":0,"height":0,"name":"importenergy","label":"importenergy","format":"{{msg.payload}}kWh","layout":"row-spread","x":864,"y":206,"wires":[]},{"id":"1e4aa427.f2aecc","type":"ui_text","z":"d3cdff25.7e38","group":"21ee6458.a3032c","order":6,"width":0,"height":0,"name":"exportgrid","label":"exportgrid","format":"{{msg.payload}}kWh","layout":"row-spread","x":856,"y":240,"wires":[]},{"id":"2ce6b919.c548e6","type":"function","z":"d3cdff25.7e38","name":"EMW3080","func":"let dataArr = msg.payload.Data;\n\nlet result = [];\nfor(var item in dataArr) {\n    result.push({\n        payload: dataArr[item]\n    });\n}\n\nreturn result;","outputs":5,"noerr":0,"x":668,"y":365,"wires":[["2c8a409d.ea6fd","5b512445.9fc61c"],["7dbe541b.cf491c"],["2eac0900.01bde8","6b5c615e.bf59c","a5c8ad7c.9355e"],["11421a85.8f9da5","767fe81b.32b648"],["c432f7f7.f5c1f8"]]},{"id":"2c8a409d.ea6fd","type":"ui_text","z":"d3cdff25.7e38","group":"ff6e2d23.dc38b","order":2,"width":0,"height":0,"name":"voltage","label":"voltage","format":"{{msg.payload}}V","layout":"row-spread","x":856,"y":300,"wires":[]},{"id":"7dbe541b.cf491c","type":"ui_text","z":"d3cdff25.7e38","group":"ff6e2d23.dc38b","order":3,"width":0,"height":0,"name":"current","label":"current","format":"{{msg.payload}}A","layout":"row-spread","x":856.5,"y":334,"wires":[]},{"id":"2eac0900.01bde8","type":"ui_text","z":"d3cdff25.7e38","group":"ff6e2d23.dc38b","order":4,"width":0,"height":0,"name":"power","label":"power","format":"{{msg.payload}}W","layout":"row-spread","x":844.5,"y":371,"wires":[]},{"id":"11421a85.8f9da5","type":"ui_text","z":"d3cdff25.7e38","group":"ff6e2d23.dc38b","order":5,"width":0,"height":0,"name":"importenergy","label":"importenergy","format":"{{msg.payload}}kWh","layout":"row-spread","x":864.5,"y":405,"wires":[]},{"id":"c432f7f7.f5c1f8","type":"ui_text","z":"d3cdff25.7e38","group":"ff6e2d23.dc38b","order":6,"width":0,"height":0,"name":"exportgrid","label":"exportgrid","format":"{{msg.payload}}kWh","layout":"row-spread","x":855.5,"y":444,"wires":[]},{"id":"c49d128f.28928","type":"function","z":"d3cdff25.7e38","name":"EMW3080TA","func":"let dataArr = msg.payload.Datas[0];\n\nlet result = [];\nfor(var item in dataArr) {\n    result.push({\n        payload: dataArr[item]\n    });\n}\n\nreturn result;","outputs":5,"noerr":0,"x":667,"y":562,"wires":[["8711bf95.71d24"],["93d7a1a1.22831"],["ef61e3f7.608d2"],["d7581758.057ea8"],["4dad54eb.dbcb6c"]]},{"id":"8711bf95.71d24","type":"ui_text","z":"d3cdff25.7e38","group":"16c2f050.5800a","order":1,"width":0,"height":0,"name":"voltageA","label":"voltageA","format":"{{msg.payload}}V","layout":"row-spread","x":854,"y":492,"wires":[]},{"id":"93d7a1a1.22831","type":"ui_text","z":"d3cdff25.7e38","group":"16c2f050.5800a","order":2,"width":0,"height":0,"name":"currentA","label":"currentA","format":"{{msg.payload}}A","layout":"row-spread","x":855.5,"y":531,"wires":[]},{"id":"ef61e3f7.608d2","type":"ui_text","z":"d3cdff25.7e38","group":"16c2f050.5800a","order":3,"width":0,"height":0,"name":"powerA","label":"powerA","format":"{{msg.payload}}W","layout":"row-spread","x":853.5,"y":568,"wires":[]},{"id":"d7581758.057ea8","type":"ui_text","z":"d3cdff25.7e38","group":"16c2f050.5800a","order":4,"width":0,"height":0,"name":"importenergyA","label":"importenergyA","format":"{{msg.payload}}kWh","layout":"row-spread","x":873.5,"y":602,"wires":[]},{"id":"4dad54eb.dbcb6c","type":"ui_text","z":"d3cdff25.7e38","group":"16c2f050.5800a","order":5,"width":0,"height":0,"name":"exportgridA","label":"exportgridA","format":"{{msg.payload}}kWh","layout":"row-spread","x":864.5,"y":641,"wires":[]},{"id":"3dc60ef2.b88b82","type":"function","z":"d3cdff25.7e38","name":"EMW3080TB","func":"let dataArr = msg.payload.Datas[1];\n\nlet result = [];\nfor(var item in dataArr) {\n    result.push({\n        payload: dataArr[item]\n    });\n}\n\nreturn result;","outputs":5,"noerr":0,"x":665,"y":763,"wires":[["c532c61f.486988"],["5c3a3fb.686b0c"],["1bcbcfb7.59c88"],["23ad147c.27414c"],["ddca25cb.7bfa48"]]},{"id":"c532c61f.486988","type":"ui_text","z":"d3cdff25.7e38","group":"72a7ac05.204694","order":6,"width":0,"height":0,"name":"voltageB","label":"voltageB","format":"{{msg.payload}}V","layout":"row-spread","x":852,"y":693,"wires":[]},{"id":"5c3a3fb.686b0c","type":"ui_text","z":"d3cdff25.7e38","group":"72a7ac05.204694","order":7,"width":0,"height":0,"name":"currentB","label":"currentB","format":"{{msg.payload}}A","layout":"row-spread","x":853.5,"y":732,"wires":[]},{"id":"1bcbcfb7.59c88","type":"ui_text","z":"d3cdff25.7e38","group":"72a7ac05.204694","order":8,"width":0,"height":0,"name":"powerB","label":"powerB","format":"{{msg.payload}}W","layout":"row-spread","x":851.5,"y":769,"wires":[]},{"id":"23ad147c.27414c","type":"ui_text","z":"d3cdff25.7e38","group":"72a7ac05.204694","order":9,"width":0,"height":0,"name":"importenergyB","label":"importenergyB","format":"{{msg.payload}}kWh","layout":"row-spread","x":871.5,"y":803,"wires":[]},{"id":"ddca25cb.7bfa48","type":"ui_text","z":"d3cdff25.7e38","group":"72a7ac05.204694","order":10,"width":0,"height":0,"name":"exportgridB","label":"exportgridB","format":"{{msg.payload}}kWh","layout":"row-spread","x":862.5,"y":842,"wires":[]},{"id":"9efa0110.ee472","type":"function","z":"d3cdff25.7e38","name":"EMW3080TC","func":"let dataArr = msg.payload.Datas[2];\n\nlet result = [];\nfor(var item in dataArr) {\n    result.push({\n        payload: dataArr[item]\n    });\n}\n\nreturn result;","outputs":5,"noerr":0,"x":673,"y":963,"wires":[["a3c4aaef.2815d8"],["e1307fb8.3c656"],["f717196b.d0c3d8"],["c0ad635.4f6cba"],["e2ff4a33.e2f278"]]},{"id":"a3c4aaef.2815d8","type":"ui_text","z":"d3cdff25.7e38","group":"9b42ebd1.3d80e8","order":11,"width":0,"height":0,"name":"voltageC","label":"voltageC","format":"{{msg.payload}}V","layout":"row-spread","x":850,"y":893,"wires":[]},{"id":"e1307fb8.3c656","type":"ui_text","z":"d3cdff25.7e38","group":"9b42ebd1.3d80e8","order":12,"width":0,"height":0,"name":"currentC","label":"currentC","format":"{{msg.payload}}A","layout":"row-spread","x":851.5,"y":932,"wires":[]},{"id":"f717196b.d0c3d8","type":"ui_text","z":"d3cdff25.7e38","group":"9b42ebd1.3d80e8","order":13,"width":0,"height":0,"name":"powerC","label":"powerC","format":"{{msg.payload}}W","layout":"row-spread","x":849.5,"y":969,"wires":[]},{"id":"c0ad635.4f6cba","type":"ui_text","z":"d3cdff25.7e38","group":"9b42ebd1.3d80e8","order":14,"width":0,"height":0,"name":"importenergyC","label":"importenergyC","format":"{{msg.payload}}kWh","layout":"row-spread","x":869.5,"y":1003,"wires":[]},{"id":"e2ff4a33.e2f278","type":"ui_text","z":"d3cdff25.7e38","group":"9b42ebd1.3d80e8","order":15,"width":0,"height":0,"name":"exportgridC","label":"exportgridC","format":"{{msg.payload}}kWh","layout":"row-spread","x":860.5,"y":1042,"wires":[]},{"id":"5b512445.9fc61c","type":"ui_gauge","z":"d3cdff25.7e38","name":"","group":"ff6e2d23.dc38b","order":1,"width":0,"height":0,"gtype":"gage","title":"voltage","label":"V","format":"{{value}}","min":0,"max":"500","colors":["#008fd5","#e6e600","#ca3838"],"seg1":"260","seg2":"280","x":1036,"y":295,"wires":[]},{"id":"6b5c615e.bf59c","type":"ui_gauge","z":"d3cdff25.7e38","name":"","group":"21ee6458.a3032c","order":1,"width":0,"height":0,"gtype":"gage","title":"power","label":"W","format":"{{value}}","min":0,"max":"5000","colors":["#008fd5","#e6e600","#ca3838"],"seg1":"3000","seg2":"4000","x":1026,"y":361,"wires":[]},{"id":"a5c8ad7c.9355e","type":"ui_chart","z":"d3cdff25.7e38","name":"","group":"6f7772ee.b5e23c","order":1,"width":0,"height":0,"label":"power","chartType":"line","legend":"false","xformat":"HH:mm:ss","interpolate":"linear","nodata":"","dot":false,"ymin":"","ymax":"","removeOlder":1,"removeOlderPoints":"30","removeOlderUnit":"3600","cutout":0,"useOneColor":false,"colors":["#1f77b4","#aec7e8","#ff7f0e","#2ca02c","#98df8a","#d62728","#ff9896","#9467bd","#c5b0d5"],"useOldStyle":false,"outputs":1,"x":1143,"y":333,"wires":[[]]},{"id":"767fe81b.32b648","type":"ui_chart","z":"d3cdff25.7e38","name":"","group":"6f7772ee.b5e23c","order":1,"width":0,"height":0,"label":"importenergy","chartType":"line","legend":"false","xformat":"HH:mm:ss","interpolate":"linear","nodata":"","dot":false,"ymin":"","ymax":"","removeOlder":1,"removeOlderPoints":"30","removeOlderUnit":"3600","cutout":0,"useOneColor":false,"colors":["#1f77b4","#aec7e8","#ff7f0e","#2ca02c","#98df8a","#d62728","#ff9896","#9467bd","#c5b0d5"],"useOldStyle":false,"outputs":1,"x":1164,"y":394,"wires":[[]]},{"id":"e393add.ec73f5","type":"function","z":"d3cdff25.7e38","name":"host","func":"//iammeter IP\nmsg.host = '192.168.15.60'\n\nreturn msg;","outputs":1,"noerr":0,"x":298,"y":332,"wires":[["fdfb7f96.83829"]]},{"id":"fdfb7f96.83829","type":"http request","z":"d3cdff25.7e38","name":"api","method":"GET","ret":"obj","paytoqs":false,"url":"http://{{{host}}}/monitorjson","tls":"","persist":false,"proxy":"","authType":"basic","x":427,"y":333,"wires":[["da96de90.da3b5","2ce6b919.c548e6","264bf1ac.4074fe","c49d128f.28928","3dc60ef2.b88b82","9efa0110.ee472"]]},{"id":"21ee6458.a3032c","type":"ui_group","z":"","name":"EMW3162","tab":"ec1ba79a.2cff38","order":3,"disp":true,"width":"6","collapse":true},{"id":"ff6e2d23.dc38b","type":"ui_group","z":"","name":"EMW3080","tab":"ec1ba79a.2cff38","order":4,"disp":true,"width":"6","collapse":true},{"id":"16c2f050.5800a","type":"ui_group","z":"","name":"EMW3080TA","tab":"ec1ba79a.2cff38","order":5,"disp":true,"width":"6","collapse":true},{"id":"72a7ac05.204694","type":"ui_group","z":"","name":"EMW3080TB","tab":"ec1ba79a.2cff38","order":6,"disp":true,"width":"6","collapse":true},{"id":"9b42ebd1.3d80e8","type":"ui_group","z":"","name":"EMW3080TC","tab":"ec1ba79a.2cff38","order":7,"disp":true,"width":"6","collapse":true},{"id":"6f7772ee.b5e23c","type":"ui_group","z":"","name":"Graph","tab":"ec1ba79a.2cff38","order":2,"disp":true,"width":"6","collapse":true},{"id":"ec1ba79a.2cff38","type":"ui_tab","z":"","name":"Home","icon":"dashboard","order":1,"disabled":false,"hidden":false}]
   ```

   ![image-20200402102137302](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/noderedimage-20200402102137302.png)

   ![image-20200402102222586](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/noderedimage-20200402102222586.png)

   ![20200402100505](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/nodered20200402100505.png)

Step 2, open host, then change the host IP as your meter's IP and select the function same with your meter's type.


   ![image-20200402102813592](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/noderedimage-20200402102813592.png)

Step 3, deploy 


   ![image-20200402103610075](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/noderedimage-20200402103610075.png)

 

## 3.Node-RED display


Open the UI http://xxx.xxx.xxx.xxx:1880/ui

   ![image-20200402103854834](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/noderedimage-20200402103854834.png)


## 4.Reference

1. [API reference](https://www.iammeter.com/doc/iammeter/integrate-with-PVOutput.html)

2. [integrated in third-party server](https://www.iammeter.com/doc/iammeter/integrate-with-thirdparty-server.html)

3. [FAQ](https://www.iammeter.com/doc/iammeter/FAQ.html)











