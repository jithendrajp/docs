#### Subscribe and Publish Message
---

Once the connection is established, device need to subscribe for the configuration and commands
topic, so that DyoCense cloud will be able to command and control the device. Also, device can
start publishing the telemetry as well as configuration changes on corresponding topics.

![](/images/AllTables/subscribeandpublish.png)

###### Example in python (MQTT Subscribe)

![](/images/AllCode/sp1.png)


###### Example in python (MQTT Publish)

![](/images/AllCode/sp2.png)


**Note:** All the messages transferred via MQTT adapter should be in proper JSON format. 
