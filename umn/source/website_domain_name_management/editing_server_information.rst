:original_name: waf_01_0001.html

.. _waf_01_0001:

Editing Server Information
==========================

This topic describes how to edit or add server information for a website to be protected.

Applicable scenarios:

-  Modify server information, including **Client Protocol**, **Server Protocol**, **VPC**, **Server Address**, and **Server Port**.
-  Add server configurations.
-  Update a certificate by referring to :ref:`Updating a Certificate <waf_01_0262>`.

Prerequisites
-------------

A website has been added to WAF.

Impact on the System
--------------------

Modifying the server configuration does not affect services.

Procedure
---------

#. Log in to the management console.
#. Click |image1| in the upper left corner of the management console and select a region or project.
#. Click |image2| in the upper left corner and choose **Web Application Firewall** under **Security**.
#. In the navigation pane, choose **Website Settings**.
#.  In the **Protected Website** column, click the domain name of the website to go to the basic information page.
#. In the **Server Information** area, click |image3|.
#. On the **Edit Server Information** page, edit the server configurations (such as client protocol and associated certificate).

   .. note::

      -  For details about certificate, see :ref:`Updating a Certificate <waf_01_0262>`.
      -  WAF supports configuring of multiple backend servers. To add a backend server, click **Add**.

#. Click **OK**.

.. |image1| image:: /_static/images/en-us_image_0210924450.jpg
.. |image2| image:: /_static/images/en-us_image_0000001074398929.png
.. |image3| image:: /_static/images/en-us_image_0282893059.jpg
