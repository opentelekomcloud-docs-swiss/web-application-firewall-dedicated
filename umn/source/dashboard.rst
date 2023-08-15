:original_name: waf_01_0021.html

.. _waf_01_0021:

Dashboard
=========

This topic describes how to view event logs, including attack and request statistics, event distribution, top 10 attacked domain names, top 10 attack source IP addresses, and top 10 attacked URLs in a specified time range, such as yesterday, today, past 3 days, past 7 days, or past 30 days.

Prerequisites
-------------

-  A domain name has been added and connected to WAF.
-  WAF protection is enabled.
-  At least one protection rule has been configured for the domain name.

Specification Limitations
-------------------------

On the **Dashboard** page, protection data of a maximum of 30 days can be viewed.

How to Calculate QPS
--------------------

The QPS calculation method varies depending on the time range. For details, see :ref:`Table 1 <waf_01_0021__table397244618286>`.

.. _waf_01_0021__table397244618286:

.. table:: **Table 1** QPS calculation

   +----------------------------+--------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
   | Time Range                 | Average QPS Description                                                                                            | Peak QPS Description                                            |
   +============================+====================================================================================================================+=================================================================+
   | **Yesterday** or **Today** | The QPS curve is made with the average QPSs in every minute.                                                       | The QPS curve is made with each peak QPS in every minute.       |
   +----------------------------+--------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
   | **Past 3 days**            | The QPS curve is made with the average QPSs in every five minutes.                                                 | The QPS curve is made with each peak QPS in every five minutes. |
   +----------------------------+--------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
   | **Past 7 days**            | The QPS curve is made with the maximum value among the average QPSs in every five minutes at a 10-minute interval. | The QPS curve is made with each peak QPS in every 10 minutes.   |
   +----------------------------+--------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
   | **Past 30 days**           | The QPS curve is made with the maximum value among the average QPSs in every five minutes at a one-hour interval.  | The QPS curve is made with the peak QPSs in every hour.         |
   +----------------------------+--------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+

.. note::

   Queries Per Second (QPS) indicates the number of requests per second. For example, an HTTP GET request is also called a query. The number of requests is the total number of requests in a specific time range.

Procedure
---------

#. Log in to the management console.
#. Click |image1| in the upper left corner of the management console and select a region or project.
#. Click |image2| in the left upper corner and choose **Security** > **Web Application Firewall** to go to the **Dashboard** page.
#. Select a protected website from the **All protected websites** drop-down list, specify the time range (**Yesterday**, **Today**, **Past 3 days**, **Past 7 days**, or **Past 30 days**), and then select the **Attacks** tab or **Requests** tab to view protection details.

   -  **Attacks**: shows the total number of attacked pages within a certain period of time.
   -  **Requests**: shows the page views of the website, making it easy for you to view the total number of pages accessed by visitors in a certain period of time.

   .. table:: **Table 2** Parameter description of event logs

      +-----------------------------------+--------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                        | Remarks                                                                                                                                          |
      +===================================+====================================================================+==================================================================================================================================================+
      | Requests                          | Total number of requests to the specified domain name              | N/A                                                                                                                                              |
      +-----------------------------------+--------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
      | Peak Value                        | Maximum number of requests to the specified domain name per second | N/A                                                                                                                                              |
      +-----------------------------------+--------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
      | Attacks                           | Number of attacks on the specified domain name                     | N/A                                                                                                                                              |
      +-----------------------------------+--------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
      | Attack Sources                    | Number of sources that attack the specified domain name            | N/A                                                                                                                                              |
      +-----------------------------------+--------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
      | Event Distribution                | Types of attack events                                             | -  Click any color area in the event distribution circle under **Event Distribution** to view the type, number, and proportion of an attack.     |
      |                                   |                                                                    | -  To stop displaying information about a specific type of event, click the corresponding legend with the same color to the right of the circle. |
      +-----------------------------------+--------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
      | Top 10 Attacked Domain Names      | Number of attacks on top 10 attacked domain names                  | N/A                                                                                                                                              |
      +-----------------------------------+--------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
      | Top 10 Attack Source IP Addresses | Number of attacks of top 10 attack source IP addresses             | N/A                                                                                                                                              |
      +-----------------------------------+--------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
      | Top 10 Attacked URLs              | Number of attacks on top 10 attacked URLs                          | N/A                                                                                                                                              |
      +-----------------------------------+--------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+

.. |image1| image:: /_static/images/en-us_image_0210924450.jpg
.. |image2| image:: /_static/images/en-us_image_0212852906.png
