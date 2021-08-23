#### Steps to receive commands from Cloud
---

1. Device need to subscribe to topic, **$iothub/methods/POST/#** to receive commands from
cloud.

1. The DyoCense cloud will in create a subscription for the device on topic,
**{device_id}/$iothub/methods/POST/#**. (no changes required in device).

1. Whenever the cloud user initiate a command, it will be published to the topic,
**{device_id}/$iothub/methods/POST/{method name}/?$rid={request id}**
with a valid JSON payload. This payload structure can be defined by the device firmware
developers and can be updated in the DyoCense cloud.

1. The status of the command execution can be published by the device as an empty
message to the topic **$iothub/methods/res/{status}/?$rid={request id}**.