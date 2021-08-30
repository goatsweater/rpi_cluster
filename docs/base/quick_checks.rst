Quick Checks
============

You can perform some quick checks on the server. For example, getting the 
temperature of each member of the cluster::

    ansible all -i inventory.ini -a "/opt/vc/bin/vcgencmd measure_temp" -k
    