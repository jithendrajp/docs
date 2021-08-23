#### Configuration Exchange with Cloud
---

Every device connecting to DyoCense cloud will have a configuration data object in the cloud.
The configuration data will be of JSON format. The configuration data consists of two sections.

**- Desired properties section**
The properties which are edited from the DyoCense cloud will be present in this section.
If the cloud wants to change any configuration for the device, the changes will be made
in the desired properties section. The changes made on desired properties will be
informed to the device.

**- Reported properties section**
The properties reported by the edge devices will be present in this section. Whenever the
device changes any of its configuration values, it can update the reported properties
section in the configuration. The DyoCense cloud application will start reflecting this
change as soon as the changes are received.

A sample configuration object in cloud will be as below.

![](/images/AllCode/config1.png)

The $version is an incremental number, which gets incremented on each update of properties.