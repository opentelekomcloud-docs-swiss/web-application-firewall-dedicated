:original_name: waf_01_0054.html

.. _waf_01_0054:

Configuring an Information Leakage Prevention Rule
==================================================

You can add two types of information leakage prevention rules.

-  Sensitive information filtering: prevents disclosure of sensitive information (such as ID numbers, phone numbers, and email addresses).
-  Response code interception: blocks the specified HTTP status codes.

Prerequisites
-------------

A website has been added to WAF.

Constraints
-----------

It takes several minutes for a new rule to take effect. After the rule takes effect, protection events triggered by the rule will be displayed on the **Events** page.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner of the management console and select a region or project.

#. Click |image2| in the upper left corner and choose **Web Application Firewall** under **Security**.

#. In the navigation pane, choose **Website Settings**.

#. In the **Policy** column of the row containing the domain name, click **Configure Policy**.

#. In the **Information Leakage Prevention** configuration area, change **Status** if needed and click **Customize Rule**.

#. In the upper left corner of the **Information Leakage Prevention** page, click **Add Rule**.

#. In the dialog box displayed, add an information leakage prevention rule by referring to :ref:`Table 1 <waf_01_0054__table242612276178>`.

   Information leakage prevention rules prevent sensitive information (such as ID numbers, phone numbers, and email addresses) from being disclosed. This type of rule can also block specified HTTP status codes.

   **Sensitive information filtering**: Configure rules to mask sensitive information, such as phone numbers and ID numbers, from web pages. For example, you can set the following protection rules to mask sensitive information, such as ID numbers, phone numbers, and email addresses:

   **Response code interception**: An error page of a specific HTTP response code may contain sensitive information. You can configure rules to block such error pages to prevent such information from being leaked out. For example, you can set the following rule to block error pages of specified HTTP response codes 404, 502, and 503.

   .. _waf_01_0054__table242612276178:

   .. table:: **Table 1** Rule parameters

      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------+
      | Parameter             | Description                                                                                                                                                                          | Example Value                       |
      +=======================+======================================================================================================================================================================================+=====================================+
      | Path                  | A part of the URL that does not include the domain name. The URL can contain sensitive information (such as ID numbers, phone numbers, and email addresses) or a blocked error code. | **/admin\***                        |
      |                       |                                                                                                                                                                                      |                                     |
      |                       | -  Prefix match: Only the prefix of the path to be entered must match that of the path to be protected.                                                                              |                                     |
      |                       |                                                                                                                                                                                      |                                     |
      |                       |    If the path to be protected is **/admin**, set **Path** to **/admin\***.                                                                                                          |                                     |
      |                       |                                                                                                                                                                                      |                                     |
      |                       | -  Exact match: The path to be entered must match the path to be protected.                                                                                                          |                                     |
      |                       |                                                                                                                                                                                      |                                     |
      |                       |    If the path to be protected is **/admin**, set **Path** to **/admin**.                                                                                                            |                                     |
      |                       |                                                                                                                                                                                      |                                     |
      |                       |    .. note::                                                                                                                                                                         |                                     |
      |                       |                                                                                                                                                                                      |                                     |
      |                       |       -  The path supports prefix and exact matches only. Regular expressions are not supported.                                                                                     |                                     |
      |                       |       -  The path cannot contain two or more consecutive slashes. For example, **///admin**. If you enter **///admin**, the WAF engine converts **///** to **/**.                    |                                     |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------+
      | Type                  | -  **Sensitive information filtering**                                                                                                                                               | **Sensitive information filtering** |
      |                       | -  **Response code interception**: Enable WAF to block the specified HTTP response code page.                                                                                        |                                     |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------+
      | Content               | Information to be protected. Options are **Identification card**, **Phone number**, and **Email**.                                                                                   | **Identification card**             |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------+
      | Rule Description      | A brief description of the rule. This parameter is optional.                                                                                                                         | None                                |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------+

#. Click **OK**. The added information leakage prevention rule is displayed in the list of information leakage prevention rules.

Other Operations
----------------

-  To disable a rule, click **Disable** in the **Operation** column of the rule. The default **Rule Status** is **Enabled**.
-  To modify a rule, click **Modify** in the row containing the rule.
-  To delete a rule, click **Delete** in the row containing the rule.

.. |image1| image:: /_static/images/en-us_image_0210924450.jpg
.. |image2| image:: /_static/images/en-us_image_0000001074398929.png
