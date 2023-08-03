:original_name: waf_01_0272.html

.. _waf_01_0272:

Specifications
==============

WAF is deployed in dedicated mode. The following tables describe specifications and functions of the dedicated WAF instances.

Dedicated Mode
--------------

:ref:`Table 1 <waf_01_0272__table680245522517>` describes dedicated WAF instances.

.. _waf_01_0272__table680245522517:

.. table:: **Table 1** Dedicated mode description

   +-----------------------------------+-------------------------------------------------------------------------------------------------------------------+
   | Item                              | Description                                                                                                       |
   +===================================+===================================================================================================================+
   | Deployment mode                   | Dedicated WAF instances                                                                                           |
   +-----------------------------------+-------------------------------------------------------------------------------------------------------------------+
   | Application scenarios             | Service servers are deployed on the cloud.                                                                        |
   |                                   |                                                                                                                   |
   |                                   | Suitable for large enterprise websites that have a large service scale and have customized security requirements. |
   +-----------------------------------+-------------------------------------------------------------------------------------------------------------------+
   | Protection objects                | Domain names or IP addresses                                                                                      |
   +-----------------------------------+-------------------------------------------------------------------------------------------------------------------+
   | Advantages                        | -  Enable cloud and on-premises deployment.                                                                       |
   |                                   | -  Enable exclusive use of WAF instance.                                                                          |
   |                                   | -  Meet requirements for protection against large-scale traffic attacks.                                          |
   |                                   | -  Deploy dedicated WAF instances in a VPC to reduce network latency.                                             |
   +-----------------------------------+-------------------------------------------------------------------------------------------------------------------+

Service Scale
-------------

For more details, see :ref:`Table 2 <waf_01_0272__en-us_topic_0110861186_table15136121131817>`.

.. _waf_01_0272__en-us_topic_0110861186_table15136121131817:

.. table:: **Table 2** Service specifications

   +-------------------------------------------------------------------------+---------------------------------------------------------+
   | Service metrics                                                         | Specifications                                          |
   +=========================================================================+=========================================================+
   | Peak rate of normal service requests                                    | -  2,000 QPS (WAF instance specifications: 100 Mbit/s)  |
   |                                                                         | -  10,000 QPS (WAF instance specifications: 500 Mbit/s) |
   +-------------------------------------------------------------------------+---------------------------------------------------------+
   | Service bandwidth threshold (Origin servers are deployed on the cloud.) | -  100 Mbit/s (WAF instance specifications: 100 Mbit/s) |
   |                                                                         | -  500 Mbit/s (WAF instance specifications: 500 Mbit/s) |
   +-------------------------------------------------------------------------+---------------------------------------------------------+
   | Number of domains                                                       | 2,000 (Supports 2,000 top-level domain names)           |
   +-------------------------------------------------------------------------+---------------------------------------------------------+
   | Peak rate of CC attack protection                                       | 500,000 QPS                                             |
   +-------------------------------------------------------------------------+---------------------------------------------------------+
   | CC attack protection rules                                              | 100                                                     |
   +-------------------------------------------------------------------------+---------------------------------------------------------+
   | Precise protection rules                                                | 100                                                     |
   +-------------------------------------------------------------------------+---------------------------------------------------------+
   | IP address blacklist and whitelist rules                                | 100                                                     |
   +-------------------------------------------------------------------------+---------------------------------------------------------+
   | Geolocation access control rules                                        | 100                                                     |
   +-------------------------------------------------------------------------+---------------------------------------------------------+
   | Web tamper protection rules                                             | 100                                                     |
   +-------------------------------------------------------------------------+---------------------------------------------------------+
   | Information leakage prevention rules                                    | 100                                                     |
   +-------------------------------------------------------------------------+---------------------------------------------------------+
   | False alarm masking rules                                               | 1,000                                                   |
   +-------------------------------------------------------------------------+---------------------------------------------------------+
   | Data masking rules                                                      | 100                                                     |
   +-------------------------------------------------------------------------+---------------------------------------------------------+

.. important::

   -  The number of domains is the total number of top-level domain names (for example, example.com), single domain names/subdomain names (for example, www.example.com), and wildcard domain names (for example, \*.example.com).
   -  If a domain name maps to different ports, each port is considered to represent a different domain name. For example, **www.example.com:8080** and **www.example.com:8081** are counted towards your quota as two distinct domain names.
