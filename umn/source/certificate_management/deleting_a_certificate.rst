:original_name: waf_01_0263.html

.. _waf_01_0263:

Deleting a Certificate
======================

This topic describes how to delete an expired or invalid certificate.

Prerequisites
-------------

The certificate you want to delete is not bound to a protected website.

Constraints
-----------

If a certificate to be deleted is bound to a website, unbind it from the website before deletion.

Impact on the System
--------------------

-  Deleting certificates does not affect services.
-  Deleted certificates cannot be recovered. Exercise caution when performing this operation.

Procedure
---------

#. Log in to the management console.
#. Click |image1| in the upper left corner of the management console and select a region or project.
#. Click |image2| in the upper left corner and choose **Web Application Firewall** under **Security**.
#. In the navigation pane, choose **Certificates**.
#. In the row containing the certificate you want to delete, click **Delete** in the **Operation** column.
#. In the displayed dialog box, click **OK**.

.. |image1| image:: /_static/images/en-us_image_0000001317947942.jpg
.. |image2| image:: /_static/images/en-us_image_0000001160928332.png
