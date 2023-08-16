:original_name: waf_01_0273.html

.. _waf_01_0273:

Applying for Dedicated WAF Engines
==================================

If your service servers are deployed on the cloud, you can apply for dedicated WAF engines (or dedicated WAF instances) to protect important websites through domain names or web applications with only IP addresses.

Prerequisites
-------------

-  You have obtained management console login credentials for an account with the **WAF Administrator** and **WAF FullAccess** permissions.
-  A VPC is available.
-  Resource sets have been created.

Precautions
-----------

After your application for a dedicated WAF instance succeeds, its specifications cannot be modified.

.. important::

   It takes about 10 minutes to create a dedicated WAF instance. If the instance is in the **Running** status, the instance has been created successfully.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner of the management console and select a region or project.

#. Click |image2| in the upper left corner and choose **Web Application Firewall** under **Security**.

#. If you are a first-time user for dedicated WAF instances, click **Apply for Dedicated Engine Now** on the left of the page.

   .. note::

      If you are not a first-time user for dedicated WAF instances, click **Apply for Dedicate Engine** in the upper right corner of the page.

#. On the **Apply for Web Application Firewall** page, set WAF instance parameters by referring to :ref:`Table 1 <waf_01_0273__en-us_topic_0161005736_table4295843716304>`.

   .. _waf_01_0273__en-us_topic_0161005736_table4295843716304:

   .. table:: **Table 1** Parameters of a dedicated WAF instance

      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                                                             |
      +===================================+=========================================================================================================================================================================================================================================================+
      | Region                            | Generally, a WAF instance you apply for in any region can protect web services in all regions. To make a WAF instance forward your website traffic faster, select the region nearest to your services.                                                  |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | AZ                                | Select an AZ in the selected region.                                                                                                                                                                                                                    |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Instance Name Prefix              | Set a prefix of the dedicated WAF instance name. If you apply for multiple instances at a time, the prefix to each instance name is the same.                                                                                                           |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Quantity                          | Set the number of WAF instances you want to apply for.                                                                                                                                                                                                  |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Specifications                    | Select specifications for your instance. WAF offers two types of specifications, 500 Mbit/s and 100 Mbit/s.                                                                                                                                             |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | CPU Architecture                  | Select CPU specifications for your instance.                                                                                                                                                                                                            |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | CPU Specifications                | Select CPU specifications for your instance.                                                                                                                                                                                                            |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Estimated Final Specifications    | Expected throughput for your reference.                                                                                                                                                                                                                 |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | VPC                               | Select the VPC to which the origin server belongs.                                                                                                                                                                                                      |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Service NIC                       | Select a subnet configured in the VPC.                                                                                                                                                                                                                  |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Security Group                    | Select a security group in the region or click **Manage Security Group** to go to the VPC console and create a security group. After you select a security group, the WAF instance will be protected by the access rules of the security group.         |
      |                                   |                                                                                                                                                                                                                                                         |
      |                                   | .. important::                                                                                                                                                                                                                                          |
      |                                   |                                                                                                                                                                                                                                                         |
      |                                   |    NOTICE:                                                                                                                                                                                                                                              |
      |                                   |                                                                                                                                                                                                                                                         |
      |                                   |    -  You can configure your security group as follows:                                                                                                                                                                                                 |
      |                                   |                                                                                                                                                                                                                                                         |
      |                                   |       -  Inbound rules                                                                                                                                                                                                                                  |
      |                                   |                                                                                                                                                                                                                                                         |
      |                                   |          Add an inbound rule to allow incoming network traffic to pass through over a specified port based on your service requirements. For example, if you want to allow access from port 80, you can add a rule that allows **TCP** and port **80**. |
      |                                   |                                                                                                                                                                                                                                                         |
      |                                   |       -  Outbound rules                                                                                                                                                                                                                                 |
      |                                   |                                                                                                                                                                                                                                                         |
      |                                   |          All outgoing network traffic is allowed by default.                                                                                                                                                                                            |
      |                                   |                                                                                                                                                                                                                                                         |
      |                                   |    -  If your dedicated WAF instance and origin server are not in the same VPC, enable communications between the instance and the subnet of the origin server in the security group.                                                                   |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. In the lower right corner of the page, click **Next**.

#. Confirm the configuration and click **Apply Now**.

8. Click **Back to Dedicated Engine List**. On the **Dedicated Engine** page, view the instance status.

   It takes about 10 minutes to create a dedicated WAF instance. If the instance is in the **Running** status, the instance has been created successfully.

.. |image1| image:: /_static/images/en-us_image_0000001082063409.jpg
.. |image2| image:: /_static/images/en-us_image_0000001082063411.png
