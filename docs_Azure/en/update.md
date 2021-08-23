#### Update configuration changes to cloud
---

Whenever a configuration value is changed in the device, it shall report the change to the cloud
to sync the reported properties of the configuration object.

1. (Optional) If the device wants to implement retry logic for sending the reported
properties, the acknowledgement topic may be subscribed by device. This may be
required to ensure the reported properties are successfully saved to cloud even though
the initial attempt was failed due to any reasons such as network drop, etc.
The device can subscribe to **$iothub/twin/res/#**.

1. The DyoCense cloud will in create a subscription for the device on topic,
**{device_id}/$iothub/twin/res/#**. (no changes required in device).

1. The device shall send the reported properties on topic
**$iothub/twin/PATCH/properties/reported/?$rid={request id}**
with a payload structure, as below

    ![](/images/AllCode/update1.png)

   
4. DyoCense cloud will publish the acknowledgement for the reported properties on the
topic **{device_id}/$iothub/twin/res/{status}/?$rid={request id}**
with a payload, as below,

    ![](/images/AllCode/update2.png)
   

Where “new version” will be the version number after updating desired properties.