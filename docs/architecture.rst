Architecture
============

Early thoughts on high level device cloud architecture:

.. image:: /images/architecture.png

The MQTT broker, mosquitto, is at the center of all communication and lives on a server in Amazon EC2, Microsoft Azure, etc.  Along with the broker other applications like visualizations or control apps are hosted on the same server and can communicate with the broker directly.

Devices in your home network, or really anywhere, connect to the MQTT broker using an encrypted SSL MQTT channel.  Normally SSL is a tremendous pain to configure and manage (especially with self-signed certificates), however I've found it's easy to automate the certificate creation tasks using Ansible so it should be painless.  I want the device cloud to be secure by default and not require someone to be an expert in security to setup or run the system.

Devices can be any hardware that's powerful enough to speak MQTT's protocol.  Embedded Linux boards like the Raspberry Pi, Beaglebone Black, Arduino Yun, Intel Galileo, etc. will be very easy to configure and use with the device cloud.  I hope to even provide Ansible tasks that can deploy and configure MQTT client tools and libraries on any embedded Linux device automatically.

What about devices which don't support SSL, like an Arduino & CC3000?  In this case mosquitto has a concept of a bridge server which can act both as an MQTT broker and client.  Any MQTT messages sent to the bridge will be relayed back up to the parent broker and vice-versa.  With this setup it will be possible to build a small, low power Arduino + CC3000 device that periodically connects to the bridge over an unencrypted channel to send/receive commands.  Because the bridge lives inside your home network (which is secured with wireless encryption, right?) it's still relatively secure.  Certainly more secure than opening the broker in the cloud up to unencrypted MQTT traffic!  Again Ansible tasks should be able to turn any Linux gadget into a bridge for the device cloud easily.