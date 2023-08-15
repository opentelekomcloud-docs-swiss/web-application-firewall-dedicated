:original_name: waf_01_0154.html

.. _waf_01_0154:

Modifying the Alarm Page
========================

If a visitor is blocked by WAF, the **Default** block page of WAF is returned by default. You can also configure **Custom** or **Redirection** for the block page to be returned as required.

Prerequisites
-------------

A website has been added to WAF.

Constraints
-----------

-  The content of the text/html, text/xml, and application/json pages can be configured on the **Custom** block page to be returned.
-  The root domain name of the redirection address must be the same as the currently protected domain name (including a wildcard domain name). For example, if the protected domain name is **www.example.com** and the port is 8080, the redirection URL can be set to **http://www.example.com:8080/error.html**.

Procedure
---------

#. Log in to the management console.
#. Click |image1| in the upper left corner of the management console and select a region or project.
#. Click |image2| in the upper left corner and choose **Web Application Firewall** under **Security**.
#. In the navigation pane, choose **Website Settings**.
#.  In the **Protected Website** column, click the domain name of the website to go to the basic information page.
#. Click |image3| next to the page template name in the row where **Alarm Page** is located. In the displayed **Alarm Page** dialog box, specify **Page Template**.

   -  To use the built-in page, select **Default**. An HTTP code 418 is returned.

   -  To customize the alarm page, select **Custom** and configure following parameters.

      -  **HTTP Return Code**: return code configured on a custom page.
      -  **Block Page Type**: The options are **text/html**, **text/xml**, and **application/json**.
      -  **Page Content**: Configure the page content based on the selected value for **Block Page Type**.

   -  To configure a redirection URL, select **Redirection**.

      The root domain name of the redirection URL must be the same as the currently protected domain name (including a wildcard domain name). For example, if the protected domain name is **www.example.com** and the port is 8080, the redirection URL can be set to **http://www.example.com:8080/error.html**.

#. Click **OK**.

.. |image1| image:: /_static/images/en-us_image_0210924450.jpg
.. |image2| image:: /_static/images/en-us_image_0000001074398929.png
.. |image3| image:: /_static/images/en-us_image_0210924454.jpg
