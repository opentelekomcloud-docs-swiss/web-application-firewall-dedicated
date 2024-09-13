:original_name: waf_01_0254.html

.. _waf_01_0254:

Why Are There No Protection Logs for Some Requests Blocked by WAF JavaScript Anti-Crawler Rules?
================================================================================================

After you enable the website anti-crawler protection, WAF returns a JavaScript code for the first access request to the domain name to the client browser, and then checks whether the request is from a valid browser or crawler based on the data resolved and returned by the client browser.

The normal detection process of the Website anti-crawler protection is as follows:

#. .. _waf_01_0254__li2888173031117:

   An initial client request to the website is sent to WAF first.

#. .. _waf_01_0254__li663684021114:

   WAF returns JavaScript code to the client.

#. The client resolves the JavaScript code and returns the execution result to WAF.

#. WAF checks whether the client of the request is a valid browser based on the result returned by the client.

   -  If it is valid, WAF sends the request to the origin server.
   -  If it is invalid, WAF generates an alarm log.

.. important::

   -  To enable the anti-crawler protection, the browser on the client must have JavaScript and cookies enabled.
   -  If JavaScript and cookies are not supported by the client browser, only :ref:`1 <waf_01_0254__li2888173031117>` and :ref:`2 <waf_01_0254__li663684021114>` can be performed. As a result, the following problems occur:

      -  The client fails to get the requested pages.
      -  No logs are recorded in WAF because the client does not send the execution result of parsing the JavaScript code.

   Check your services. If your website can be accessed by other means except for a browser, disable anti-crawler protection.
