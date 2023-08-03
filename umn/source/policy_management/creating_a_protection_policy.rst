:original_name: waf_01_0074.html

.. _waf_01_0074:

Creating a Protection Policy
============================

A policy is a combination of rules, such as basic web protection, blacklist, whitelist, and precise protection rules. A policy can be applied to multiple domain names, but only one policy can be used for a domain name. This topic describes how to add a policy to your WAF instance.

Prerequisites
-------------

A website has been added to WAF.

Constraints
-----------

-  A protected website domain name can use only one policy.

Procedure
---------

#. Log in to the management console.
#. Click |image1| in the upper left corner of the management console and select a region or project.
#. Click |image2| in the upper left corner and choose **Web Application Firewall** under **Security**.
#. In the navigation pane on the left, choose **Policies**.
#. In the upper left corner, click **Add Policy**.
#. In the displayed dialog box, enter the policy name and click **Confirm**. The added policy will be displayed in the policy list.
#. In the **Policy Name** column, click the policy name. On the displayed page, add rules to the policy by referring to :ref:`Rule Configurations <waf_01_0007>`.

Other Operations
----------------

-  To modify a policy name, click |image3| next to the policy name. In the dialog box displayed, enter a new policy name.
-  To delete a rule, click **More** > **Delete** in the **Operation** column.

.. |image1| image:: /_static/images/en-us_image_0210924450.jpg
.. |image2| image:: /_static/images/en-us_image_0000001074398929.png
.. |image3| image:: /_static/images/en-us_image_0301168075.png
