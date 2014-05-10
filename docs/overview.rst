Overview
========

What is a device cloud?
-----------------------

I consider a device cloud to be a service that provides both a broker for communication between devices and a host for applications that interact with devices. The broker allows devices to communicate to other devices or applications without having to be tightly coupled or directly connected to each other. The device cloud is also an easily accessible host for applications that interact with devices, such as visualizations of data or control of device functionality.

Why do you want a device cloud?
-------------------------------

* Discovering and connecting to your devices over the internet is hard! Dynamic IP addresses, NAT, firewalls, and more prevent you from easily accessing your home network and devices. Hosting your own device cloud on the internet allows devices to connect and communicate without the trouble of opening connectivity to your home network.
* Not all devices can be connected and online all the time. A device cloud allows for asynchronous communication between devices. For example a sensor or actuator can periodically connect to your device cloud to record data or receive new instructions; because the device isn't connected all the time it can greatly reduce its power consumption.
* You have total control over the data and services available to your devices. You aren't limited by what a 3rd party provides or concerned about what they might do with your data. You own the entire infrastructure and can mold it to your needs.

Project Goals
-------------

* Automate the setup and maintenance of services that form a personal device cloud. Setup should be an easily repeatable process from a single command or script.
* Target running the device cloud on cheap, low end cloud infrastructure like Amazon EC2's micro instance free tier.
* Build on existing tools, services, and protocols--don't reinvent the wheel! Many of the services to build a device cloud exist today, they just need to be put together into an easy to use package.
* Document how to connect popular development hardware like the Raspberry Pi, Beaglebone Black, and Arduino to a device cloud.