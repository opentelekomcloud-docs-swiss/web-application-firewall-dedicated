:original_name: waf_01_0014.html

.. _waf_01_0014:

Configuring a Web Tamper Protection Rule
========================================

WAF can cache configuration for static web pages of websites. After you configure a web tamper protection rule, WAF can:

-  Return directly the cached web page to the normal web visitor to accelerate request response.

-  Return the cached original web pages to visitors if an attacker has tampered with the static web pages. This ensures that your website visitors always get the right web pages.

-  Protect all resources in the web page path. For example, if a web tamper protection rule is configured for static page **www.example.com/admin**, WAF protects all resources in the **/admin** directory.

   So, if the URL in the value of the **Referer** request header is the same as the configured anti-tamper path, for example, **/admin**, all resources (resources ending with png, jpg, jpeg, gif, bmp, css or js) hit by the request are also cached.

Prerequisites
-------------

A website has been added to WAF.

Constraints
-----------

It takes several minutes for a new rule to take effect. After the rule takes effect, protection events triggered by the rule will be displayed on the **Events** page.

Application Scenarios
---------------------

-  Quicker response to requests

   After a web tamper protection rule is configured, WAF caches static web pages on the server. When receiving a request from a web visitor, WAF directly returns the cached web page to the web visitor.

-  Web tamper protection

   If an attacker modifies a static web page on the server, WAF still returns the cached original web page to visitors. Visitors never see the pages that were tampered with.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner of the management console and select a region or project.

#. Click |image2| in the upper left corner and choose **Web Application Firewall** under **Security**.

#. In the navigation pane, choose **Website Settings**.

#. In the **Policy** column of the row containing the domain name, click **Configure Policy**.

#. In the **Web Tamper Protection** configuration area, change **Status** if needed and click **Customize Rule** to go to the **Web Tamper Protection** page.

#. In the upper left corner of the **Web Tamper Protection** page, click **Add Rule**.

#. In the displayed dialog box, specify the parameters by referring to :ref:`Table 1 <waf_01_0014__table2046816299203>`.

   .. _waf_01_0014__table2046816299203:

   .. table:: **Table 1** Rule parameters

      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Description                                                                                                                                         | Example Value         |
      +=======================+=====================================================================================================================================================+=======================+
      | Domain Name           | Domain name of the website to be protected                                                                                                          | **www.example.com**   |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Path                  | A part of the URL, not including the domain name                                                                                                    | **/admin**            |
      |                       |                                                                                                                                                     |                       |
      |                       | A URL is used to define the address of a web page. The basic URL format is as follows:                                                              |                       |
      |                       |                                                                                                                                                     |                       |
      |                       | Protocol name://Domain name or IP address[:Port]/[Path/.../File name].                                                                              |                       |
      |                       |                                                                                                                                                     |                       |
      |                       | For example, if the URL is **http://www.example.com/admin**, set **Path** to **/admin**.                                                            |                       |
      |                       |                                                                                                                                                     |                       |
      |                       | .. note::                                                                                                                                           |                       |
      |                       |                                                                                                                                                     |                       |
      |                       |    -  The path does not support regular expressions.                                                                                                |                       |
      |                       |    -  The path cannot contain two or more consecutive slashes. For example, **///admin**. If you enter **///admin**, WAF converts **///** to **/**. |                       |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Rule Description      | A brief description of the rule. This parameter is optional.                                                                                        | None                  |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

#. Click **OK**. You can view the rule in the list of web tamper protection rules.

Other Operations
----------------

-  To disable a rule, click **Disable** in the **Operation** column of the rule. The default **Rule Status** is **Enabled**.
-  To update cache of a protected web page, click **Update Cache** in the row containing the corresponding web tamper protection rule. If the rule fails to be updated, WAF will return the recently cached page but not the latest page.
-  To delete a rule, click **Delete** in the row containing the rule.

.. |image1| image:: /_static/images/en-us_image_0210924450.jpg
.. |image2| image:: /_static/images/en-us_image_0000001074398929.png
