:original_name: waf_01_0282.html

.. _waf_01_0282:

Viewing Certificate Information
===============================

This topic describes how to view certificate details, including the certificate name, domain name a certificate is used for, and expiration time.

Prerequisites
-------------

You have created or pushed a certificate to WAF.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner of the management console and select a region or project.

#. Click |image2| in the upper left corner and choose **Web Application Firewall** under **Security**.

#. In the navigation pane, choose **Certificates**.

#. View the certificate information. :ref:`Table 1 <waf_01_0282__table14874354152011>` describes the parameters.

   .. _waf_01_0282__table14874354152011:

   .. table:: **Table 1** Parameter description

      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                                                                                                                                   |
      +===================================+===============================================================================================================================================================================================================================================================================================================================+
      | Name                              | Certificate name.                                                                                                                                                                                                                                                                                                             |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Domain Name                       | The domain names protected by the certificate Each domain name must be bound to a certificate. One certificate can be used for multiple domain names.                                                                                                                                                                         |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Expired                           | Certificate expiration time.                                                                                                                                                                                                                                                                                                  |
      |                                   |                                                                                                                                                                                                                                                                                                                               |
      |                                   | It is recommended that you update the certificate before it expires. Otherwise, all WAF protection rules will be unable to take effect, and there can be massive impacts on the origin server, even more severe than a crashed host or website access failures. For details, see :ref:`Updating a Certificate <waf_01_0262>`. |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Other Operations
----------------

-  To change the certificate name, move the cursor over the name of the certificate, click |image3|, and enter a certificate name.

   .. important::

      If the certificate is in use, unbind the certificate from the domain name first. Otherwise, the certificate name cannot be changed.

-  To view details about a certificate, click **View** in the **Operation** column of the certificate.
-  To delete a certificate, locate the row of the certificate and click **Delete** in the **Operation** column.

.. |image1| image:: /_static/images/en-us_image_0269497434.jpg
.. |image2| image:: /_static/images/en-us_image_0000001160928332.png
.. |image3| image:: /_static/images/en-us_image_0269115287.png
