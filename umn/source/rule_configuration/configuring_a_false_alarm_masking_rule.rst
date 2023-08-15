:original_name: waf_01_0016.html

.. _waf_01_0016:

Configuring a False Alarm Masking Rule
======================================

You can add false alarm masking rules to let WAF ignore certain rule IDs or event types (for example, skip XSS checks for a specific URL).

Prerequisites
-------------

A website has been added to WAF.

Constraints
-----------

-  It takes several minutes for a new rule to take effect. After the rule takes effect, protection events triggered by the rule will be displayed on the **Events** page.
-  You can configure a false alarm masking rule by referring to :ref:`Handling False Alarms <waf_01_0024>`. After handling a false alarm, you can view the rule in the false alarm masking rule list.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner of the management console and select a region or project.

#. Click |image2| in the upper left corner and choose **Web Application Firewall** under **Security**.

#. In the navigation pane, choose **Website Settings**.

#. In the **Policy** column of the row containing the domain name, click **Configure Policy**.

#. In the **False Alarm Masking** configuration area, click **Status** if needed. Then, click **Customize Rule**.

#. In the upper left corner of the **False Alarm Masking** page, click **Add Rule**.

#. Add a false alarm masking rule by referring to :ref:`Table 1 <waf_01_0016__table15761232696>`.

   .. _waf_01_0016__table15761232696:

   .. table:: **Table 1** Parameters for adding a false alarm masking rule

      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------+
      | Parameter             | Description                                                                                                                                                                                                                                                                                            | Example Value                              |
      +=======================+========================================================================================================================================================================================================================================================================================================+============================================+
      | Domain Name           | Enter a single domain name that matches the wildcard domain name being protected by the current policy.                                                                                                                                                                                                | www.example.com                            |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------+
      | Path                  | Part of the URL (excluding the domain name) that a false alarm is reported for.                                                                                                                                                                                                                        | Equal to                                   |
      |                       |                                                                                                                                                                                                                                                                                                        |                                            |
      |                       | -  Prefix match: If you select **Prefix is**, the entered path is used as the prefix. For example, if the path to be protected is **/admin/test.php** or **/adminabc**, set **Path** to **/admin**.                                                                                                    | /admin                                     |
      |                       | -  Exact match: The path to be entered must be **Equal to** the path to be protected. For example, if the path to be protected is **/admin/test.php**, set **Path** to **/admin/test.php**.                                                                                                            |                                            |
      |                       |                                                                                                                                                                                                                                                                                                        |                                            |
      |                       | .. note::                                                                                                                                                                                                                                                                                              |                                            |
      |                       |                                                                                                                                                                                                                                                                                                        |                                            |
      |                       |    -  The path supports prefix match and exact match method only but does not support regular expressions.                                                                                                                                                                                             |                                            |
      |                       |    -  The path cannot contain two or more consecutive slashes. For example, **///admin**. If you enter **///admin**, the WAF engine converts **///** to **/**.                                                                                                                                         |                                            |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------+
      | Rule                  | The item that the false alarm masking rule takes effect for. The options are:                                                                                                                                                                                                                          | Attack type                                |
      |                       |                                                                                                                                                                                                                                                                                                        |                                            |
      |                       | -  **ID**: Configure the rule by event ID.                                                                                                                                                                                                                                                             |                                            |
      |                       | -  **Attack type**: Configure the rule by attack event type, such as XSS and SQL injection. One type contains one or more rule IDs.                                                                                                                                                                    |                                            |
      |                       | -  **All built-in rules**: all checks enabled in :ref:`Basic Web Protection <waf_01_0008>`.                                                                                                                                                                                                            |                                            |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------+
      | ID                    | This parameter is mandatory when **Rule** is set to **ID**.                                                                                                                                                                                                                                            | 041046                                     |
      |                       |                                                                                                                                                                                                                                                                                                        |                                            |
      |                       | ID of an attack event on the **Events** page. If the event type is **Custom**, it has no event ID. Click **Handle False Alarm** in the row containing the attack event to obtain the ID. To configure false alarm masking on the **Events** page, refer to :ref:`Handling False Alarms <waf_01_0024>`. |                                            |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------+
      | Attack Type           | This parameter is mandatory when **Rule** is set to **Attack type**.                                                                                                                                                                                                                                   | SQL injection                              |
      |                       |                                                                                                                                                                                                                                                                                                        |                                            |
      |                       | Select an attack type from the drop-down list box.                                                                                                                                                                                                                                                     |                                            |
      |                       |                                                                                                                                                                                                                                                                                                        |                                            |
      |                       | WAF can defend against XSS attacks, web shells, SQL injection attacks, malicious crawlers, remote file inclusions, local file inclusions, command injection attacks, and other attacks.                                                                                                                |                                            |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------+
      | Rule Description      | A brief description of the rule. This parameter is optional.                                                                                                                                                                                                                                           | SQL injection attacks are not intercepted. |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------+
      | Advanced Settings     | To ignore attacks of a specific field, specify the field in the **Advanced Settings** area. After you add the rule, WAF will stop blocking attack events of the specified field.                                                                                                                       | Params                                     |
      |                       |                                                                                                                                                                                                                                                                                                        |                                            |
      |                       | Select a target field from the first drop-down list box on the left. The following fields are supported: **Params**, **Cookie**, **Header**, **Body**, and **Multipart**.                                                                                                                              | All                                        |
      |                       |                                                                                                                                                                                                                                                                                                        |                                            |
      |                       | -  If you select **Params**, **Cookie**, or **Header**, you can select **All** or **Specified field** to configure a subfield.                                                                                                                                                                         |                                            |
      |                       | -  If you select **Body** or **Multipart**, you can select **All**.                                                                                                                                                                                                                                    |                                            |
      |                       | -  If you select **Cookie**, the **Domain Name** and **Path** can be empty.                                                                                                                                                                                                                            |                                            |
      |                       |                                                                                                                                                                                                                                                                                                        |                                            |
      |                       | .. note::                                                                                                                                                                                                                                                                                              |                                            |
      |                       |                                                                                                                                                                                                                                                                                                        |                                            |
      |                       |    If **All** is selected, WAF will not block all attack events of the selected field.                                                                                                                                                                                                                 |                                            |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------+

#. Click **OK**.

Other Operations
----------------

-  To disable a rule, click **Disable** in the **Operation** column of the rule. The default **Rule Status** is **Enabled**.
-  To modify a rule, click **Modify** in the row containing the rule.
-  To delete a rule, click **Delete** in the row containing the rule.

.. |image1| image:: /_static/images/en-us_image_0210924450.jpg
.. |image2| image:: /_static/images/en-us_image_0000001074398929.png
