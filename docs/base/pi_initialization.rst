Base configuration
==================

This guide will build the cluster on top of the Raspbian OS. Initial 
configuration is done using Ansible playbooks.

OS installation
---------------

Using Raspberry Pi Imager, install Raspberry Pi OS Lite. This will avoid 
loading the graphical interface and optimize the Pis for participating in the 
cluster.

Once the card is initialized it needs to be booted once to let the Pi configure 
the basic OS (creating partitions, etc).

After a few minutes, unplug the Pi and remove the SD card. Place the card back 
into the computer.

Initialization
--------------

There are a few files that need to be edited to ensure remote access and 
successful cluster creation. The tasks are all defined in ``pi_init.yml``, and 
can be run with::

    ansible-playbook pi_init.yml

k3s preparation
---------------

With the base Raspbian installation complete, it is now time to get prepare the 
each Raspberry Pi to run Kubernetes::

    ansible-playbook -i inventory base.yml

Cluster creation
----------------

Kubernetes will be fully installed and configured using Ansible::

    ansible-playbook -i inventory.ini cluster_init.yml

Once ansible is finished configuring everything the cluster is ready for use.
The ``pi`` user on the master node is the one that got configured to connect 
to the cluster. You can check it from there::

    ssh pi@master-ip
    pi@rpi-k8s-master:~ $ kubectl get nodes

    