:original_name: waf_01_0008.html

.. _waf_01_0008:

Configuring Basic Web Protection Rules
======================================

After this function is enabled, WAF can defend against common web attacks, such as SQL injections, XSS, remote overflow vulnerabilities, file inclusions, Bash vulnerabilities, remote command execution, directory traversal, sensitive file access, and command/code injections. You can also enable other preset rules in basic web protection, such as webshell detection, search engines, scanners, script tools, and other crawlers.

.. important::

   Basic web protection has two modes: **Block** and **Log only**.

Prerequisites
-------------

A website has been added to WAF.

.. _waf_01_0008__section61533550183130:

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner of the management console and select a region or project.

#. Click |image2| in the upper left corner and choose **Web Application Firewall** under **Security**.

#. In the navigation pane, choose **Website Settings**.

#. In the **Policy** column of the row containing the domain name, click **Configure Policy**.

#. In the **Basic Web Protection** configuration area, change **Status** and **Mode** as needed by referring to :ref:`Table 1 <waf_01_0008__table42360431192825>`.

   .. _waf_01_0008__table42360431192825:

   .. table:: **Table 1** Parameter description

      +-----------------------------------+-----------------------------------------------------+
      | Parameter                         | Description                                         |
      +===================================+=====================================================+
      | Status                            | Status of Basic Web Protection                      |
      |                                   |                                                     |
      |                                   | -  |image3|: enabled.                               |
      |                                   | -  |image4|: disabled.                              |
      +-----------------------------------+-----------------------------------------------------+
      | Mode                              | -  **Block**: WAF blocks and logs detected attacks. |
      |                                   | -  **Log only**: WAF only logs detected attacks.    |
      +-----------------------------------+-----------------------------------------------------+

#. In the **Basic Web Protection** configuration area, click **Advanced Settings**.

#. Enable protection types you need by referring to :ref:`Table 3 <waf_01_0008__table1054818371898>`.

   a. Set the protection level.

      In the upper part of the page, set **Protection Level** to **Low**, **Medium**, or **High**. The default value is **Medium**.

      .. table:: **Table 2** Protection levels

         +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Protection Level                  | Description                                                                                                                                                                                                                                |
         +===================================+============================================================================================================================================================================================================================================+
         | Low                               | WAF only blocks the requests with obvious attack signatures.                                                                                                                                                                               |
         |                                   |                                                                                                                                                                                                                                            |
         |                                   | If a large number of false alarms are reported, **Low** is recommended.                                                                                                                                                                    |
         +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Medium                            | The default level is **Medium**, which meets a majority of web protection requirements.                                                                                                                                                    |
         +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | High                              | At this level, WAF provides the finest granular protection and can intercept attacks with complex bypass features, such as Jolokia cyber attacks, common gateway interface (CGI) vulnerability detection, and Druid SQL injection attacks. |
         |                                   |                                                                                                                                                                                                                                            |
         |                                   | To let WAF defend against more attacks but make minimum effect on normal requests, observe your workloads for a period of time first. Then, configure a false alarm masking rule and select **High**.                                      |
         +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   b. Set the protection type.

      .. important::

         By default, **General Check** and **Scanner** are enabled. You can enable other protection types by referring to :ref:`Table 3 <waf_01_0008__table1054818371898>`.

   .. _waf_01_0008__table1054818371898:

   .. table:: **Table 3** Protection types

      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Type                              | Description                                                                                                                                                                                                                                                                                       |
      +===================================+===================================================================================================================================================================================================================================================================================================+
      | General Check                     | Defends against attacks such as SQL injections, XSS, remote overflow vulnerabilities, file inclusions, Bash vulnerabilities, remote command execution, directory traversal, sensitive file access, and command/code injections. SQL injection attacks are mainly detected based on semantics.     |
      |                                   |                                                                                                                                                                                                                                                                                                   |
      |                                   | .. note::                                                                                                                                                                                                                                                                                         |
      |                                   |                                                                                                                                                                                                                                                                                                   |
      |                                   |    If you enable **General Check**, WAF checks your websites based on the built-in rules.                                                                                                                                                                                                         |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Webshell Detection                | Protects against web shells from upload interface.                                                                                                                                                                                                                                                |
      |                                   |                                                                                                                                                                                                                                                                                                   |
      |                                   | .. note::                                                                                                                                                                                                                                                                                         |
      |                                   |                                                                                                                                                                                                                                                                                                   |
      |                                   |    If you enable **Webshell Detection**, WAF detects web page Trojan horses inserted through the upload interface.                                                                                                                                                                                |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Search Engine                     | Uses web crawlers, such as Googlebot and Baiduspider, to find pages for search engines.                                                                                                                                                                                                           |
      |                                   |                                                                                                                                                                                                                                                                                                   |
      |                                   | .. note::                                                                                                                                                                                                                                                                                         |
      |                                   |                                                                                                                                                                                                                                                                                                   |
      |                                   |    If you disable **Search Engine**, WAF does not block POST requests from the Googlebot or Baiduspider. If you want to block POST requests from Baiduspider, use the configuration described in :ref:`Configuration Example - Blocking Baidu POST Requests <waf_01_0008__section1978194713716>`. |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Scanner                           | Scans for vulnerabilities, viruses, and performs other types of web scans, such as OpenVAS and Nmap.                                                                                                                                                                                              |
      |                                   |                                                                                                                                                                                                                                                                                                   |
      |                                   | .. note::                                                                                                                                                                                                                                                                                         |
      |                                   |                                                                                                                                                                                                                                                                                                   |
      |                                   |    If you enable **Scanner**, WAF detects the scanner crawlers, such as OpenVAS and Nmap.                                                                                                                                                                                                         |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Script Tool                       | Executes automatic tasks and program scripts, such as HttpClient, OkHttp, and Python programs.                                                                                                                                                                                                    |
      |                                   |                                                                                                                                                                                                                                                                                                   |
      |                                   | .. note::                                                                                                                                                                                                                                                                                         |
      |                                   |                                                                                                                                                                                                                                                                                                   |
      |                                   |    If your application uses scripts such as HttpClient, OkHttp, and Python, disable **Script Tool**. Otherwise, WAF will identify such script tools as crawlers and block the application.                                                                                                        |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Other                             | Crawlers for other purposes, such as site monitoring, access proxy, and web page analysis.                                                                                                                                                                                                        |
      |                                   |                                                                                                                                                                                                                                                                                                   |
      |                                   | .. note::                                                                                                                                                                                                                                                                                         |
      |                                   |                                                                                                                                                                                                                                                                                                   |
      |                                   |    If you enable **Other**, WAF detects the crawler programs for various purposes.                                                                                                                                                                                                                |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Protection Effect
-----------------

If **General Check** is enabled and **Mode** is set to **Block** for your domain name, to verify WAF is protecting your website (**www.example.com**) against general check items:

#. Clear the browser cache and enter the domain name in the address box of a browser to check whether the website is accessible.

   -  If the website is inaccessible, connect the website domain name to WAF by following the instructions in :ref:`Step 1: Add a Website to WAF <waf_01_0250>`.
   -  If the website is accessible, go to :ref:`Step 2 <waf_01_0008__li2057953372517>`.

#. .. _waf_01_0008__li2057953372517:

   Clear the browser cache and enter **http://www.example.com?id=1%27%20or%201=1** in the address box of the browser to simulate an SQL injection attack.

#. Return to the WAF console. In the navigation pane, choose **Events**. On the displayed page, view or :ref:`download events data <waf_01_0077>`.

.. _waf_01_0008__section1978194713716:

Configuration Example - Blocking Baidu POST Requests
----------------------------------------------------

To allow the search engine of Baidu or Google and block the POST request of Baidu:

#. Set **Status** of **Search Engine** to |image5| by referring to :ref:`Procedure <waf_01_0008__section61533550183130>`.
#. Configure a rule by referring to :ref:`Configuring a Precise Protection Rule <waf_01_0010>`.

   -  Set **Method** to **POST**.
   -  Configure the **User Agent** field to include Baiduspider.

.. |image1| image:: /_static/images/en-us_image_0210924450.jpg
.. |image2| image:: /_static/images/en-us_image_0000001074398929.png
.. |image3| image:: /_static/images/en-us_image_0234013391.png
.. |image4| image:: /_static/images/en-us_image_0234013368.png
.. |image5| image:: /_static/images/en-us_image_0234013368.png
