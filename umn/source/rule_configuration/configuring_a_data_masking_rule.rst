:original_name: waf_01_0017.html

.. _waf_01_0017:

Configuring a Data Masking Rule
===============================

This topic describes how to configure data masking rules. You can configure data masking rules to prevent sensitive data such as passwords from being displayed in event logs.

Prerequisites
-------------

A website has been added to WAF.

Constraints
-----------

It takes several minutes for a new rule to take effect. After the rule takes effect, protection events triggered by the rule will be displayed on the **Events** page.

Impact on the System
--------------------

Sensitive data in the events will be masked to protect your website visitor's privacy.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner of the management console and select a region or project.

#. Click |image2| in the upper left corner and choose **Web Application Firewall** under **Security**.

#. In the navigation pane, choose **Website Settings**.

#. In the **Policy** column of the row containing the domain name, click **Configure Policy**.

#. In the **Data Masking** configuration area, change **Status** if needed and click **Customize Rule**.

#. In the upper left corner of the **Data Masking** page, click **Add Rule**.

#. In the displayed dialog box, specify the parameters described in :ref:`Table 1 <waf_01_0017__table4696626918715>`.

   .. _waf_01_0017__table4696626918715:

   .. table:: **Table 1** Rule parameters

      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------+
      | Parameter             | Description                                                                                                                                                                                           | Example Value                                                                                                                |
      +=======================+=======================================================================================================================================================================================================+==============================================================================================================================+
      | Path                  | Part of the URL that does not include the domain name.                                                                                                                                                | **/admin/login.php**                                                                                                         |
      |                       |                                                                                                                                                                                                       |                                                                                                                              |
      |                       | -  Prefix match: The path ending with \* indicates that the path is used as a prefix. For example, if the path to be protected is **/admin/test.php** or **/adminabc**, set **Path** to **/admin\***. | For example, if the URL to be protected is **http://www.example.com/admin/login.php**, set **Path** to **/admin/login.php**. |
      |                       | -  Exact match: The path to be entered must match the path to be protected. If the path to be protected is **/admin**, set **Path** to **/admin**.                                                    |                                                                                                                              |
      |                       |                                                                                                                                                                                                       |                                                                                                                              |
      |                       | .. note::                                                                                                                                                                                             |                                                                                                                              |
      |                       |                                                                                                                                                                                                       |                                                                                                                              |
      |                       |    -  The path supports prefix and exact matches only and does not support regular expressions.                                                                                                       |                                                                                                                              |
      |                       |    -  The path cannot contain two or more consecutive slashes. For example, **///admin**. If you enter **///admin**, WAF converts **///** to **/**.                                                   |                                                                                                                              |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------+
      | Masked Field          | A field set to be masked                                                                                                                                                                              | -  If **Masked Field** is **Params** and **Field Name** is **id**, content that matches **id** is masked.                    |
      |                       |                                                                                                                                                                                                       | -  If **Masked Field** is **Cookie** and **Field Name** is **name**, content that matches **name** is masked.                |
      |                       | -  **Params**: A request parameter                                                                                                                                                                    |                                                                                                                              |
      |                       | -  **Cookie**: A small piece of data to identify web visitors                                                                                                                                         |                                                                                                                              |
      |                       | -  **Header**: A user-defined HTTP header                                                                                                                                                             |                                                                                                                              |
      |                       | -  **Form**: A form parameter                                                                                                                                                                         |                                                                                                                              |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------+
      | Field Name            | Set the parameter based on **Masked Field**. The masked field will not be displayed in logs.                                                                                                          |                                                                                                                              |
      |                       |                                                                                                                                                                                                       |                                                                                                                              |
      |                       | .. important::                                                                                                                                                                                        |                                                                                                                              |
      |                       |                                                                                                                                                                                                       |                                                                                                                              |
      |                       |    NOTICE:                                                                                                                                                                                            |                                                                                                                              |
      |                       |    The length of a subfield cannot exceed 2,048 bytes. Only digits, letters, underscores (_), and hyphens (-) are allowed.                                                                            |                                                                                                                              |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------+
      | Rule Description      | A brief description of the rule. This parameter is optional.                                                                                                                                          | None                                                                                                                         |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------+

#. Click **OK**. The added data masking rule is displayed in the list of data masking rules.

Other Operations
----------------

-  To disable a rule, click **Disable** in the **Operation** column of the rule. The default **Rule Status** is **Enabled**.
-  To modify a rule, click **Modify** in the row containing the rule.
-  To delete a rule, click **Delete** in the row containing the rule.

.. |image1| image:: /_static/images/en-us_image_0210924450.jpg
.. |image2| image:: /_static/images/en-us_image_0000001074398929.png
