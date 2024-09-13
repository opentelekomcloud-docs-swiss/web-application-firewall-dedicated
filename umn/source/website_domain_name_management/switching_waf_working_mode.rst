:original_name: waf_01_0003.html

.. _waf_01_0003:

Switching WAF Working Mode
==========================

You can change the working mode of WAF. WAF can work in **Enabled** or **Suspended** mode.

Prerequisites
-------------

The domain name of the website to be protected has been connected to WAF.

Application Scenarios
---------------------

-  **Enabled**: In this mode, WAF defends your website against attacks based on configured policies.
-  **Suspended**: If a large number of normal requests are blocked, for example, status code 418 is frequently returned, then you can switch the mode to **Suspended**. In this mode, your website is not protected because WAF only forwards requests. It does not scan for or log attacks. This mode is risky. You are advised to use the false alarm masking rules to reduce false alarms.

Impact on the System
--------------------

In the **Suspended** mode, your website is not protected because WAF only forwards requests. It does not scan for attacks. To avoid normal requests from being blocked, configure false alarm masking rules, instead of using the **Suspended** mode.

Procedure
---------

#. Log in to the management console.
#. Click |image1| in the upper left corner of the management console and select a region or project.
#. Click |image2| in the upper left corner and choose **Web Application Firewall** under **Security**.
#. In the navigation pane, choose **Website Settings**.
#. In the row containing the target website, click **Switch Mode** in the **Mode** column.
#. In the **Switch Mode** dialog box, select a working mode and then click **OK**.

.. |image1| image:: /_static/images/en-us_image_0210924450.jpg
.. |image2| image:: /_static/images/en-us_image_0000001074398929.png
