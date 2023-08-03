:original_name: waf_01_0250.html

.. _waf_01_0250:

Step 1: Add a Website to WAF
============================

If your service servers are deployed on the cloud, you can add the domain name or IP address of the website to WAF so that the website traffic is forwarded to WAF for inspection.

Prerequisites
-------------

You have applied for a dedicated WAF instance.

Constraints
-----------

-  An Internet-facing load balancer has been deployed on the website you want to protect with dedicated WAF instances.
-  If your website has no layer-7 proxy server such as CDN and cloud acceleration service deployed in front of WAF and uses only layer-4 load balancers (or NAT), set **Proxy Configured** to **No**. Otherwise, **Proxy Configured** must be set to **Yes**. This ensures that WAF obtains real IP addresses of website visitors and takes protective actions configured in protection policies.

Procedure
---------

#. Log in to the management console.
#. Click |image1| in the upper left corner of the management console and select a region or project.

3. Click |image2| in the upper left corner and choose **Web Application Firewall** under **Security**.

4. In the navigation pane, choose **Website Settings**.

5. In the upper left corner of the website list, click **Add Website**.

6. Configure basic information of the domain name. :ref:`Table 1 <waf_01_0250__table7692122554811>` lists parameters.

   .. _waf_01_0250__table7692122554811:

   .. table:: **Table 1** Parameter description

      +-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------+
      | Parameter             | Description                                                                                                                                                                                                                                                                                                                            | Example Value                            |
      +=======================+========================================================================================================================================================================================================================================================================================================================================+==========================================+
      | Domain Name           | A domain name or IP address of the website to be protected. The domain name can be a single domain name or a wildcard domain name.                                                                                                                                                                                                     | Single domain name: **www.example.com**  |
      |                       |                                                                                                                                                                                                                                                                                                                                        |                                          |
      |                       | -  Single domain name: Enter a single domain name. For example, www.example.com.                                                                                                                                                                                                                                                       | Wildcard domain name: **\*.example.com** |
      |                       | -  Wildcard domain name                                                                                                                                                                                                                                                                                                                |                                          |
      |                       |                                                                                                                                                                                                                                                                                                                                        | IP address format: *XXX.XXX.1.1*         |
      |                       |    .. note::                                                                                                                                                                                                                                                                                                                           |                                          |
      |                       |                                                                                                                                                                                                                                                                                                                                        |                                          |
      |                       |       Wildcard domain names cannot contain underscores (_).                                                                                                                                                                                                                                                                            |                                          |
      |                       |                                                                                                                                                                                                                                                                                                                                        |                                          |
      |                       |    -  If the server IP address of each subdomain name is the same, enter a wildcard domain name to be protected. For example, if the subdomain names **a.example.com**, **b.example.com**, and **c.example.com** have the same server IP address, you can add the wildcard domain name **\*.example.com** to WAF to protect all three. |                                          |
      |                       |    -  If the server IP addresses of subdomain names are different, add subdomain names as single domain names one by one.                                                                                                                                                                                                              |                                          |
      +-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------+
      | Port                  | Set this parameter only if **Non-standard Port** is selected.                                                                                                                                                                                                                                                                          | 81                                       |
      |                       |                                                                                                                                                                                                                                                                                                                                        |                                          |
      |                       | -  If **Client Protocol** is **HTTP**, WAF protects services on the standard port 80 by default. If **Client Protocol** is **HTTPS**, WAF protects services on the standard port 443 by default.                                                                                                                                       |                                          |
      |                       | -  To configure a port other than ports 80 and 443, select **Non-standard Port** and select a non-standard port from the **Port** drop-down list.                                                                                                                                                                                      |                                          |
      |                       |                                                                                                                                                                                                                                                                                                                                        |                                          |
      |                       | .. note::                                                                                                                                                                                                                                                                                                                              |                                          |
      |                       |                                                                                                                                                                                                                                                                                                                                        |                                          |
      |                       |    If a non-standard port is configured, the visitors need to add the non-standard port to the end of the website address when they access the website. Otherwise, a 404 error will occur. If a 404 error occurs, see How Do I Troubleshoot 404/502/504 Errors?                                                                        |                                          |
      +-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------+
      | Server Configuration  | Address of the web server. The configuration contains the **Client Protocol**, **Server protocol**, VPC, **Server Address,** and **Server Port**.                                                                                                                                                                                      | **Client Protocol**: **HTTP**            |
      |                       |                                                                                                                                                                                                                                                                                                                                        |                                          |
      |                       | -  **Client Protocol**: Protocol used for forwarding a client requests to the dedicated WAF instance. The options are **HTTP** and **HTTPS**.                                                                                                                                                                                          | **Server Protocol**: **HTTP**            |
      |                       | -  **Server Protocol**: Protocol used for forwarding a client request to the origin server through the dedicated WAF instance. The options are **HTTP** and **HTTPS**.                                                                                                                                                                 |                                          |
      |                       |                                                                                                                                                                                                                                                                                                                                        | **VPC**: vpc-default                     |
      |                       |    .. note::                                                                                                                                                                                                                                                                                                                           |                                          |
      |                       |                                                                                                                                                                                                                                                                                                                                        | **Server Address**: *192.168.1.1*        |
      |                       |       WAF can check WebSocket and WebSockets requests, which is enabled by default.                                                                                                                                                                                                                                                    |                                          |
      |                       |                                                                                                                                                                                                                                                                                                                                        | **Server Port**: **80**                  |
      |                       | -  **VPC**: Select the VPC to which the dedicated WAF instance belongs.                                                                                                                                                                                                                                                                |                                          |
      |                       | -  **Server Address**: Private/internal IP address or domain name of the website server that a client (for example, a browser) accesses.                                                                                                                                                                                               |                                          |
      |                       | -  **Server Port**: service port of the server to which the dedicated WAF instance forwards client requests.                                                                                                                                                                                                                           |                                          |
      +-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------+
      | Certificate Name      | If **Client Protocol** is set to **HTTPS**, select a certificate.                                                                                                                                                                                                                                                                      | None                                     |
      |                       |                                                                                                                                                                                                                                                                                                                                        |                                          |
      |                       | .. important::                                                                                                                                                                                                                                                                                                                         |                                          |
      |                       |                                                                                                                                                                                                                                                                                                                                        |                                          |
      |                       |    NOTICE:                                                                                                                                                                                                                                                                                                                             |                                          |
      |                       |                                                                                                                                                                                                                                                                                                                                        |                                          |
      |                       |    -  Only .pem certificates can be used in WAF. If the certificate is not in .pem format, convert it into a .pem certificate by referring to :ref:`Importing a New Certificate <waf_01_0250__section36817893018>` before uploading the certificate.                                                                                   |                                          |
      |                       |    -  Each domain name must have a certificate associated. A wildcard domain name can only use a wildcard domain certificate. If you only have single-domain certificates, add domain names to WAF one by one.                                                                                                                         |                                          |
      +-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------+

7. Configure **Proxy Configured**.

   If your website has no layer-7 proxy server such as CDN and cloud acceleration service deployed in front of WAF and uses only layer-4 load balancers (or NAT), set **Proxy Configured** to **No**. Otherwise, **Proxy Configured** must be set to **Yes**. This ensures that WAF obtains real IP addresses of website visitors and takes protective actions configured in protection policies.

8. Click **OK**.

   You can view the added websites in the protected website list.

Verification
------------

The initial **Access Status** of a website is **Inaccessible**. After you configure a load balancer and bind an EIP to the load balancer for your website, when a request reaches the WAF dedicated instance, the access status automatically changes to **Accessible**.

.. _waf_01_0250__section36817893018:

Importing a New Certificate
---------------------------

If you set **Client Protocol** to **HTTPS**, an SSL certificate is required. You can perform the following steps to import a new certificate.

#. Click **Import New Certificate**.

   .. note::

      WAF encrypts and saves the private key to keep it safe.

   Only .pem certificates can be used in WAF. If the certificate is not in .pem format, convert it into .pem locally by referring to :ref:`Table 2 <waf_01_0250__waf_01_0002_table1292125414516>` before uploading it.

   .. _waf_01_0250__waf_01_0002_table1292125414516:

   .. table:: **Table 2** Certificate conversion commands

      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------+
      | Format                            | Conversion Method                                                                                                          |
      +===================================+============================================================================================================================+
      | CER/CRT                           | Rename the **cert.crt** certificate file to **cert.pem**.                                                                  |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------+
      | PFX                               | -  Obtain a private key. For example, run the following command to convert **cert.pfx** into **key.pem**:                  |
      |                                   |                                                                                                                            |
      |                                   |    **openssl pkcs12 -in cert.pfx -nocerts -out key.pem -nodes**                                                            |
      |                                   |                                                                                                                            |
      |                                   | -  Obtain a certificate. For example, run the following command to convert **cert.pfx** into **cert.pem**:                 |
      |                                   |                                                                                                                            |
      |                                   |    **openssl** **pkcs12** **-in** **cert.pfx** **-nokeys** **-out** **cert.pem**                                           |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------+
      | P7B                               | a. Convert a certificate. For example, run the following command to convert **cert.p7b** into **cert.cer**:                |
      |                                   |                                                                                                                            |
      |                                   |    **openssl** **pkcs7** **-print_certs** **-in** **cert.p7b** **-out** **cert.cer**                                       |
      |                                   |                                                                                                                            |
      |                                   | b. Rename certificate file **cert.cer** to **cert.pem**.                                                                   |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------+
      | DER                               | -  Obtain a private key. For example, run the following command to convert ****privatekey.der**** into **privatekey.pem**: |
      |                                   |                                                                                                                            |
      |                                   |    **openssl** **rsa** **-inform** **DER** **-outform** **PEM** **-in** **privatekey.der** **-out** **privatekey.pem**     |
      |                                   |                                                                                                                            |
      |                                   | -  Obtain a certificate. For example, run the following command to convert **cert.cer** into **cert.pem**:                 |
      |                                   |                                                                                                                            |
      |                                   |    **openssl** **x509** **-inform** **der** **-in** **cert.cer** **-out cert.pem**                                         |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------+

   .. note::

      -  Before running an OpenSSL command, ensure that the `OpenSSL <https://www.openssl.org/>`__ tool has been installed on the local host.
      -  If your local PC runs a Windows operating system, go to the command line interface (CLI) and then run the certificate conversion command.

#. Click **OK**.

.. |image1| image:: /_static/images/en-us_image_0000001260399509.jpg
.. |image2| image:: /_static/images/en-us_image_0000001081669593.png
