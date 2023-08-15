:original_name: waf_01_0251.html

.. _waf_01_0251:

Step 2: Configure a Load Balancer
=================================

To ensure your dedicated WAF instance reliability, after you add a website to it, use Elastic Load Balance (ELB) to configure a load balancer and a health check for the dedicated WAF instance.

Prerequisites
-------------

-  You have added a website to a dedicated WAF instance.

-  You have created a load balancer.

-  Related ports have been enabled in the security group to which the dedicated WAF instance belongs.

   You can configure your security group as follows:

   -  Inbound rules

      Add an inbound rule to allow incoming network traffic to pass through over a specified port based on your service requirements. For example, if you want to allow access from port 80, add a rule that allows **TCP** and port **80**.

   -  Outbound rules

      Retain the default settings. All outgoing network traffic is allowed by default.

Constraints
-----------

The listening port of the dedicated WAF instance must be the same as that configured in :ref:`Step 1: Add a Website to WAF <waf_01_0250>`.

Procedure
---------

#. Log in to the management console.
#. Click |image1| in the upper left corner of the management console and select a region or project.
#. Click |image2| in the upper left corner of the page and choose **Elastic Load Balance** under **Network** to go to the ELB console.
#. Click the name of your load balancer in the **Name** column to go to the **Basic Information** page.
#. Click the **Listeners** tab, click **Add Listener**, and configure the listener name, front-end protocol, and port.
#. Click **Next: Configure Backend Server Group**.

   .. important::

      If you select **Round robin** for **Load Balancing Algorithm**, disable **Sticky Session**. If you enable **Sticky Session**, the same requests will be forwarded to the same dedicated WAF instance. If this instance becomes faulty, an error will occur when the requests come to it next time.

#. Click **Next: Configure Health Check**.

   .. important::

      -  Set the **Port** to the port of the website configured in :ref:`Step 1: Add a Website to WAF <waf_01_0250>`, which is the service port listened by the WAF instance.
      -  In the health check configuration, **Protocol** can only be set to **TCP**, or the health check will fail and ELB will not forward traffic to the backend WAF.

#. Click **Next: Confirm**.
#. Click **Submit**.
#. Go to the page of the added listener, select the **Backend Server Groups** tab, and click **Add**.
#. In the **Add Backend Server** dialog box, select the dedicated WAF instance you have created.
#. Click **Next** and configure a port for the dedicated engine.

   .. important::

      The listening port of the dedicated WAF instance must be the same as that configured in :ref:`Step 1: Add a Website to WAF <waf_01_0250>`. If you configure a standard port for the website, set the HTTP listening port to **80** and HTTPS listening port to **443**.

#. Click **Finish**.

.. |image1| image:: /_static/images/en-us_image_0210924450.jpg
.. |image2| image:: /_static/images/en-us_image_0212852906.png
