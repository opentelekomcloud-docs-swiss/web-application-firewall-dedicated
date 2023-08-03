:original_name: waf_01_0081.html

.. _waf_01_0081:

Adding a Reference Table
========================

This topic describes how to create a reference table to batch configure protection metrics of a single type, such as **Path**, **User Agent**, **IP**, **Params**, **Cookie**, **Referer**, and **Header**. A reference table can be referenced by CC attack protection rules and precise protection rules.

Prerequisites
-------------

A website has been added to WAF.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner of the management console and select a region or project.

#. Click |image2| in the upper left corner and choose **Web Application Firewall** under **Security**.

#. In the navigation pane, choose **Website Settings**.

#. In the **Policy** column of the row containing the domain name, click **Configure Policy**.

#. In the **CC Attack Protection** or **Precise Protection** area, click **Customize Rule**.

#. Click **Reference Table Management** in the upper left corner of the list.

#. On the **Reference Table Management** page, click **Add Reference Table**.

#. In the **Add Reference Table** dialog box, specify the parameters by referring to :ref:`Table 1 <waf_01_0081__table22291637155812>`.

   .. _waf_01_0081__table22291637155812:

   .. table:: **Table 1** Parameter description

      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Description                                                                                                                                                                 | Example Value         |
      +=======================+=============================================================================================================================================================================+=======================+
      | Name                  | Table name you entered                                                                                                                                                      | test                  |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Type                  | -  **Path**: A URL to be protected, excluding a domain name                                                                                                                 | **Path**              |
      |                       |                                                                                                                                                                             |                       |
      |                       | -  **User Agent**: A user agent of the scanner to be protected                                                                                                              |                       |
      |                       |                                                                                                                                                                             |                       |
      |                       | -  **IP**: An IP address of the visitor to be protected.                                                                                                                    |                       |
      |                       |                                                                                                                                                                             |                       |
      |                       | -  **Params**: A request parameter to be protected                                                                                                                          |                       |
      |                       |                                                                                                                                                                             |                       |
      |                       | -  **Cookie**: A small piece of data to identify web visitors                                                                                                               |                       |
      |                       |                                                                                                                                                                             |                       |
      |                       | -  **Referer**: A user-defined request resource                                                                                                                             |                       |
      |                       |                                                                                                                                                                             |                       |
      |                       |    For example, if the protected path is **/admin/xxx** and you do not want visitors to be able to access it from *www.test.com*, set **Value** to **http://www.test.com**. |                       |
      |                       |                                                                                                                                                                             |                       |
      |                       | -  **Header**: A user-defined HTTP header                                                                                                                                   |                       |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Value                 | Value of the corresponding **Type**. Wildcards are not allowed.                                                                                                             | **/buy/phone/**       |
      |                       |                                                                                                                                                                             |                       |
      |                       | .. note::                                                                                                                                                                   |                       |
      |                       |                                                                                                                                                                             |                       |
      |                       |    Click **Add** to add more than one value.                                                                                                                                |                       |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

#. Click **OK**. You can then view the added reference table in the reference table list.

Other Operations
----------------

-  To modify a reference table, click **Modify** in the row containing the reference table.
-  To delete a reference table, click **Delete** in the row containing the reference table.

.. |image1| image:: /_static/images/en-us_image_0210924450.jpg
.. |image2| image:: /_static/images/en-us_image_0000001074398929.png
