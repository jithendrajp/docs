#### Listen to configuration changes from cloud
---

Whenever the users are making device configuration change in DyoCense cloud, the changes
need to be synced with the device

1. The device need to subscribe to topic **$iothub/twin/PATCH/properties/desired/#** to
receive changes applied on desired properties.

1. The DyoCense cloud will in create a subscription for the device on topic,
**{device_id}/$iothub/twin/PATCH/properties/desired/#**. (no changes required in
device).

1. When a change is occurred in desired properties of the device, the cloud will publish the
desired properties on **{device_id}/$iothub/twin/PATCH/properties/desired/PATCH/?$version={new version}**

Where,
**new version** is the incremental version number of the desired properties.

Below you can see a sample payload data that will be received on the topic when these
parameters are modified by cloud.

![](/images/AllCode/listenconfig.png)

