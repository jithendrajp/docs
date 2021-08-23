#### Steps to receive messages from cloud
---

All the one-way messages from cloud will be published on topic
**devices/{device_id}/messages/devicebound/#** and the devices can subscribe to this topic to
listen to those messages. The payload in the message will be a valid JSON defined by the cloud
user (or user facing application).
