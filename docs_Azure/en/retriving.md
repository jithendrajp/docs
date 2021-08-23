#### Retrieving complete configuration from cloud
---

This can be used when the device re-establishes the connectivity with cloud after a disconnection.
This will help in syncing the configuration changes happened in cloud when the device was
disconnected.

1. First, a device subscribes to **$iothub/twin/res/#** to receive the configuration data.

1. The DyoCense cloud will in create a subscription for the device on topic,
**{device_id}/$iothub/twin/res/#**. (no changes required in device).

1. Then, device sends an empty message to topic -
**$iothub/twin/GET/?$rid={request id}**, with a populated value for request ID. 

1. The DyoCense cloud then sends a response message containing the device twin data on
topic **{device_id}/$iothub/twin/res/{status}/?$rid={request id}**, using the same
request ID as the request. The received payload will be exactly same as the configuration
object depicted in above section.
The possible values of **{status}** are as in below table.

    |         |            | 
    | ------------- |:-------------:| 
    | 200      | Successfully retrieved| 
    | 400      | Bad request      |   
    | 500 | Internal server error. Retry again     |    