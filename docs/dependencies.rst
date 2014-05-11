Dependencies
============

If you're running Windows, you will need to install vagrant and virtualbox to setup an Ubuntu linux virtual machine for executing the playbooks.  Don't worry!  Vagrant makes the setup and usage of a virtual machine extremely easy.

TODO: Put in details on setting up vagrant.

If you're running Mac OS X or Linux you should have everything you need to get started.

You will need to install the following software:

Python
------

You probably have this installed already, to check open up a terminal and run::

    python --version

Any Python version >2.6 should work.  If you see an error that Python is not installed, please install the latest version of Python 2.7.

pip
---

pip is a Python package manager which can install all the required Python dependencies.  To install pip execute::

    wget https://bootstrap.pypa.io/get-pip.py
    sudo python get-pip.py

Ansible
-------

Ansible is the automation tool that will set up and configure the machines in the device cloud.  Install Ansible by executing::

    sudo pip install ansible

boto
----

boto is a Python package for interacting with Amazon's AWS cloud services.  If you are using Amazon AWS to host your device cloud you will need to install boto by executing::

    sudo pip install boto
