.. RPi Cluster documentation master file, created by
   sphinx-quickstart on Thu Aug 12 17:18:56 2021.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Raspberry Pi Cluster
=======================================

Documentation for building a Raspberry Pi cluster from start to finish. The 
cluster is configured with ansible to have to initialize the cluster nodes.

.. graphviz::

   digraph nodes {
      "master" -> "node1";
      "master" -> "node2";
   }

.. toctree::
   :maxdepth: 2
   :caption: Contents:

   base/pi_initialization
   base/quick_checks
   resources


Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
