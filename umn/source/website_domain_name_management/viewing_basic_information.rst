:original_name: waf_01_0020.html

.. _waf_01_0020:

Viewing Basic Information
=========================

This topic describes how to view the basic information about a protected website, switch WAF working mode, and delete a domain name of a protected website from WAF.

Prerequisites
-------------

A website has been connected to WAF.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner of the management console and select a region or project.

#. Click |image2| in the upper left corner and choose **Web Application Firewall** under **Security**.

#. In the navigation pane, choose **Website Settings**.

#. View the protected website lists. For details about parameters, see :ref:`Table 1 <waf_01_0020__table125091352115811>`.

   .. note::

      -  To change the WAF working mode, in the **Mode** column, click **Switch Mode** and select a working mode you want.
      -  To check the connection status of a website, in the **Access Status** column, click |image3| to refresh the status.
      -  To view protection logs for the last three days, in the **Protection Status over Past 3 Days** column, click **View**.
      -  To stop protecting a website, in the **Operation** column, click **Delete**.

   .. _waf_01_0020__table125091352115811:

   .. table:: **Table 1** Parameter description

      +------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                          | Description                                                                                                                                                                                                                                                                                                                                                                                             |
      +====================================+=========================================================================================================================================================================================================================================================================================================================================================================================================+
      | Protected Website                  | Domain name or IP address of a website you want to protect.                                                                                                                                                                                                                                                                                                                                             |
      +------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Mode                               | WAF mode of the protected domain name. Click **Switch** and select one of the following working modes:                                                                                                                                                                                                                                                                                                  |
      |                                    |                                                                                                                                                                                                                                                                                                                                                                                                         |
      |                                    | -  **Enabled**: WAF is enabled.                                                                                                                                                                                                                                                                                                                                                                         |
      |                                    | -  **Suspended**: WAF is disabled. If a large number of normal requests are blocked, for example, status code 418 is frequently returned, then you can switch the mode to **Suspended**. In this mode, your website is not protected because WAF only forwards requests. It does not scan for attacks. This mode is risky. You are advised to use the false alarm masking rules to reduce false alarms. |
      |                                    |                                                                                                                                                                                                                                                                                                                                                                                                         |
      |                                    | For details, see :ref:`Switching WAF Working Mode <waf_01_0003>`.                                                                                                                                                                                                                                                                                                                                       |
      +------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Access Status                      | -  **Inaccessible**: The website is not connected to WAF or cannot connect to WAF.                                                                                                                                                                                                                                                                                                                      |
      |                                    | -  **Accessible**: The website is connected to WAF.                                                                                                                                                                                                                                                                                                                                                     |
      +------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Protection Status over Past 3 Days | Protection status of the domain name over the past 3 days.                                                                                                                                                                                                                                                                                                                                              |
      +------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Policy                             | Policy configuration of the domain name. Click **Configure Policy** to configure rules. For details, see :ref:`Rule Configuration <waf_01_0007>`.                                                                                                                                                                                                                                                       |
      +------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Operation                          | To remove a protected website from WAF, click **Delete**.                                                                                                                                                                                                                                                                                                                                               |
      +------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#.  In the **Protected Website** column, click the domain name of the website to go to the basic information page.

#. View the basic information about the protected website.

   -  Update the certificate: If you select **HTTPS** for **Client Protocol**, an SSL certificate is required. To update the certificate, click |image4| next to the certificate name in the row. Then, in the displayed dialog box, upload a new certificate or select an existing certificate. For more details, see :ref:`Updating a Certificate <waf_01_0262>`.
   -  Update the TLS version and TLS cipher suite for accessing the origin server: If you select **HTTPS** for **Client Protocol**, you can change TLS version to a more secure one. To do so, click |image5| next to the TLS Configuration field. Then, in the displayed dialog box, select the desired TLS version and TLS cipher suite. For more details, see :ref:`Configuring the Minimum TLS Version and Cipher Suite <waf_01_0169>`.
   -  Modify the field of **Proxy Configured**: Click |image6|. In the displayed dialog box, select **Yes** if your web server is using a proxy.
   -  Customize the alarm page: Click |image7|. In the displayed dialog box, select **Custom** or **Redirection** and complete required configurations. By default, **Alarm Page** is **Default**.

.. |image1| image:: /_static/images/en-us_image_0210924450.jpg
.. |image2| image:: /_static/images/en-us_image_0000001074398929.png
.. |image3| image:: /_static/images/en-us_image_0269649626.png
.. |image4| image:: /_static/images/en-us_image_0210924454.jpg
.. |image5| image:: /_static/images/en-us_image_0210924454.jpg
.. |image6| image:: /_static/images/en-us_image_0210924454.jpg
.. |image7| image:: /_static/images/en-us_image_0210924454.jpg
