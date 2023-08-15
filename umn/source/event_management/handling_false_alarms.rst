:original_name: waf_01_0024.html

.. _waf_01_0024:

Handling False Alarms
=====================

If you confirm that an attack event on the **Events** page is a false alarm, you can handle the event as false alarm by ignoring the URL and rule ID in basic web protection, or by deleting or disabling the corresponding protection rule you configured. After an attack event is handled as a false alarm, the event will not be displayed on the **Events** page anymore.

WAF detects attacks by using built-in basic web protection rules and custom rules you configured (such as CC attack protection, precise access protection, blacklist, whitelist, and geolocation access control rules). WAF will respond to detected attacks based on the protective actions (such as **Block** and **Log only**) defined in the rules and display attack events on the **Events** page.

Prerequisites
-------------

There is at least one false alarm event in the event list.

Constraints
-----------

-  Only attack events blocked or recorded by preconfigured basic web protection rules can be handled as false alarms.
-  For events generated based on custom rules (such as a CC attack protection rule, precise protection rule, blacklist rule, whitelist rule, or geolocation access control rule), they cannot be handled as false alarms. To ignore such an event, delete or disable the custom rule hit by the event.
-  An attack event can only be handled as a false alarm once.

Impact on the System
--------------------

The attack event will not be displayed on the **Events** page.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner of the management console and select a region or project.

#. Click |image2| in the upper left corner and choose **Web Application Firewall** under **Security**.

#. In the navigation pane on the left, choose **Events**.

#. Select the **Search** tab. Select a website from the **All protected websites** drop-down list. Then, select **Yesterday**, **Today**, **Past 3 days**, **Past 7 days**, **Past 30 days**, or a custom time range.

   .. table:: **Table 1** Parameters in the event list

      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Description                                                                                                                                                               | Example Value         |
      +=======================+===========================================================================================================================================================================+=======================+
      | Time                  | When the attack occurred                                                                                                                                                  | 2021/02/04 13:20:04   |
      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Source IP Address     | Public IP address of the web visitor/attacker                                                                                                                             | None                  |
      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Domain Name           | Attacked domain name                                                                                                                                                      | www.example.com       |
      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | URL                   | Attacked URL                                                                                                                                                              | /admin                |
      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Malicious Load        | The location or part of the attack that causes damage or the number of times that the URL was accessed.                                                                   | id=1 and 1='1         |
      |                       |                                                                                                                                                                           |                       |
      |                       | .. note::                                                                                                                                                                 |                       |
      |                       |                                                                                                                                                                           |                       |
      |                       |    -  In a CC attack, the malicious load indicates the number of times that the URL was accessed.                                                                         |                       |
      |                       |    -  For blacklist protection events, the malicious load is left blank.                                                                                                  |                       |
      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Event Type            | Type of attack                                                                                                                                                            | SQL injection         |
      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Protective Action     | Protective actions configured in the rule. The options are **Block**, **Log only**, and **Verification code**.                                                            | Block                 |
      |                       |                                                                                                                                                                           |                       |
      |                       | .. note::                                                                                                                                                                 |                       |
      |                       |                                                                                                                                                                           |                       |
      |                       |    If an access request matches a web tamper protection rule, information leakage prevention rule, or data masking rule, the protective action is marked as **Mismatch**. |                       |
      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Operation             | You can perform the following operations in the **Operation** column:                                                                                                     | Details               |
      |                       |                                                                                                                                                                           |                       |
      |                       | -  Click **Details** to view details about the attack event.                                                                                                              |                       |
      |                       | -  Click **Handle False Alarm** to handle the attack event as a false alarm.                                                                                              |                       |
      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

   .. note::

      To view event details, click **Details** in the **Operation** column of the event list.

#. After you confirm that an event is a false alarm, click **Handle False Alarm** in the **Operation** column of the row and add a false alarm masking rule. :ref:`Table 2 <waf_01_0024__table1326514293541>` describes parameters.

   .. _waf_01_0024__table1326514293541:

   .. table:: **Table 2** Parameter description

      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------+
      | Parameter             | Description                                                                                                                                                                                         | Example Value                              |
      +=======================+=====================================================================================================================================================================================================+============================================+
      | Domain Name           | Domain name where an attack occurred. WAF auto-fills the field.                                                                                                                                     | None                                       |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------+
      | Path                  | Part of the URL (excluding the domain name) that a false alarm is reported for. The default value is the source path of the event.                                                                  | None                                       |
      |                       |                                                                                                                                                                                                     |                                            |
      |                       | -  Prefix match: If you select **Prefix is**, the entered path is used as the prefix. For example, if the path to be protected is **/admin/test.php** or **/adminabc**, set **Path** to **/admin**. |                                            |
      |                       | -  Exact match: The path to be entered must be **Equal to** the path to be protected. For example, if the path to be protected is **/admin/test.php**, set **Path** to **/admin/test.php**.         |                                            |
      |                       |                                                                                                                                                                                                     |                                            |
      |                       | .. note::                                                                                                                                                                                           |                                            |
      |                       |                                                                                                                                                                                                     |                                            |
      |                       |    -  The path supports prefix and exact matches. Regular expressions are not supported.                                                                                                            |                                            |
      |                       |    -  The path cannot contain two or more consecutive slashes. For example, **///admin**. If you enter **///admin**, WAF converts **///** to **/**.                                                 |                                            |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------+
      | Rule                  | The item that the false alarm masking rule takes effect for. The options are:                                                                                                                       | Attack type                                |
      |                       |                                                                                                                                                                                                     |                                            |
      |                       | -  **ID**: Configure the rules by ID of the hit rule.                                                                                                                                               |                                            |
      |                       | -  **Attack type**: Configure the rule by attack type.                                                                                                                                              |                                            |
      |                       | -  **All built-in rules**: all checks enabled in :ref:`Basic Web Protection <waf_01_0008>`.                                                                                                         |                                            |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------+
      | ID                    | ID of a built-in rule, which is automatically read.                                                                                                                                                 | 060015                                     |
      |                       |                                                                                                                                                                                                     |                                            |
      |                       | This parameter is mandatory when **Rule** is set to **ID**.                                                                                                                                         |                                            |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------+
      | Attack Type           | Automatically obtained attack type.                                                                                                                                                                 | Remote File Inclusion                      |
      |                       |                                                                                                                                                                                                     |                                            |
      |                       | This parameter is mandatory when **Rule** is set to **Attack type**.                                                                                                                                |                                            |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------+
      | Rule Description      | A brief description of the rule. This parameter is optional.                                                                                                                                        | SQL injection attacks are not intercepted. |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------+
      | Advanced Settings     | To ignore attacks of a specific field, specify the field in the **Advanced Settings** area. After you add the rule, WAF will stop blocking attack events of the specified field.                    | Params                                     |
      |                       |                                                                                                                                                                                                     |                                            |
      |                       | Select a target field from the first drop-down list box on the left. The following fields are supported: **Params**, **Cookie**, **Header**, **Body**, and **Multipart**.                           | All                                        |
      |                       |                                                                                                                                                                                                     |                                            |
      |                       | -  If you select **Params**, **Cookie**, or **Header**, configure subfields as required.                                                                                                            |                                            |
      |                       | -  If you select **Cookie**, the **Domain Name** and **Path** can be empty.                                                                                                                         |                                            |
      |                       |                                                                                                                                                                                                     |                                            |
      |                       | .. note::                                                                                                                                                                                           |                                            |
      |                       |                                                                                                                                                                                                     |                                            |
      |                       |    If **All** is selected, WAF will not block all attack events of the selected field.                                                                                                              |                                            |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------+

#. Click **OK**.

Verification
------------

A false alarm will be deleted within about a minute after the handling configuration is done. It will no longer be displayed in the attack event details list. You can refresh the browser cache and request the page for which the false alarm masking rule is configured to check whether the configuration takes effect.

Other Operations
----------------

If an event is handled as a false alarm, the rule hit will be added to the false alarm masking rule list. You can go to the **Policies** page and then switch to the False Alarm Masking page to manage the rule, including querying, disabling, deleting, and modifying the rule. For details, see :ref:`Configuring a False Alarm Masking Rule <waf_01_0016>`.

.. |image1| image:: /_static/images/en-us_image_0210924450.jpg
.. |image2| image:: /_static/images/en-us_image_0000001074398929.png
