## 1. Introduction
Our WiFi Energy Meter (WEM3080 and WEM3080T) can upload the data to the server of third party through the TCP/SSL interface. So you can integrate the data to your own server and build you own cloud and app.

## 2. How to integrate
There are two modes to upload the meter's data to the server of third party. 

### 2.1 TCP Socket Mode

**Description**

Working as a TCP client, the meter can post the data to remote TCP server every minute;

![](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iMeter201909-1.jpg)

![](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iMeter201909-2.jpg)

**Json Code**

```
{
  "method": "uploadsn",    
  "mac": "B0F8933C4F7E",
  "version": "1.72.7",
  "server": "em",
  "SN": "xxxx",
  "Datas": [
    [  # a phase voltage,current,power,ImportEnergy,ExportEnergy,frequency,PF
      236.0,  
      4.4,     
      -1044,
      0.92,
      0.04,
      49.99,
      1.00
    ],
    [ # b phase voltage,current,power,ImportEnergy,ExportEnergy,frequency,PF
      220.0,
      10.0,
      -1100,
      6971.88,
      1789550.92,
      49.99,
      0.50
    ],
    [ # c phase voltage,current,power,ImportEnergy,ExportEnergy,frequency,PF
      220.0,  
      10.0,
      -1213,
      8.60,
      8.44,
      49.99,
      0.55
    ]
  ]
}


```
mac: the mac of this meter

version：the firmware version of this meter

SN: the sn of this meter

**Github**

https://github.com/lewei50/iammeter

### 2.2 TLS Mode

**Description**

Working as a TLS client, the meter can post the data to remote TLS server every minute;

**Json Code**
```
{
  "method": "uploadsn",
  "mac": "B0F8933C4F7E",
  "version": "1.72.7",
  "server": "em",
  "SN": "E395281A",
  "Datas": [
    [
      236.0,
      4.4,
      -1044,
      0.92,
      0.04,
      49.99,
      1.00
    ],
    [
      220.0,
      10.0,
      -1100,
      6971.88,
      1789550.92,
      49.99,
      0.50
    ],
    [
      220.0,
      10.0,
      -1213,
      8.60,
      8.44,
      49.99,
      0.55
    ]
  ]
}
```

mac: the mac of this meter

version：the firmware version of this meter

SN: the sn of this meter

**Github**

https://github.com/lewei50/iammeter

## 3 Reference

- **QuickStart document  of single phase WiFi Energy Meter (WEM3080):** [WEM3080 Quickstart](https://www.iammeter.com/doc/iammeter/wem3080-quickstart.html)

![](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/WEM3080.png)

- **QuickStart document  of three phase WiFi Energy Meter (WEM3080T):** [WEM3080T Quickstart](https://www.iammeter.com/doc/iammeter/wem3080t-quickstart.html)

![](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/WEM3080T.jpg)

### Note

If you have a WeChat account, please follow our IAMMETER WeChat public ID.

![iammeter.jpg](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter-20181103-1.jpg)
