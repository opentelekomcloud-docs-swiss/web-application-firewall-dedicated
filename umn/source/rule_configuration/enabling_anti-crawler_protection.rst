:original_name: waf_01_0015.html

.. _waf_01_0015:

Enabling Anti-Crawler Protection
================================

This topic describes how to enable anti-crawler rules.

Prerequisites
-------------

A website has been added to WAF.

Constraints
-----------

-  Cookies must be enabled and JavaScript supported by any browser used to access a website protected by anti-crawler protection rules.

-  It takes several minutes for a new rule to take effect. After the rule takes effect, protection events triggered by the rule will be displayed on the **Events** page.

-  If your service is connected to CDN, exercise caution when using this function.

   CDN caching may impact Anti-Crawler performance and page accessibility.

Procedure
---------

#. Log in to the management console.
#. Click |image1| in the upper left corner of the management console and select a region or project.
#. Click |image2| in the upper left corner and choose **Web Application Firewall** under **Security**.
#. In the navigation pane, choose **Website Settings**.
#. In the **Policy** column of the row containing the domain name, click **Configure Policy**.
#. By default, **Anti-Crawler** is disabled. To enable it, click |image3|. In the displayed warning dialog box, confirm the information and click **OK**.

   .. important::

      If you enable both a cloud acceleration service, such as CDN, and the **Anti-Crawler** function on your website, access exceptions may occur depending on the acceleration configuration of such service.

.. |image1| image:: /_static/images/en-us_image_0210924450.jpg
.. |image2| image:: /_static/images/en-us_image_0000001074398929.png
.. |image3| image:: /_static/images/en-us_image_0000001082058711.png
