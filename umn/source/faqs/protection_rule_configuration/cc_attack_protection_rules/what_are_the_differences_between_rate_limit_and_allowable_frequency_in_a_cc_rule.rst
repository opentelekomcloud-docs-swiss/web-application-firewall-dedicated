:original_name: waf_01_0155.html

.. _waf_01_0155:

What Are the Differences Between **Rate Limit** and **Allowable Frequency** in a CC Rule?
=========================================================================================

In a CC attack protection rule, **Rate Limit** specifies the maximum requests that a website visitor can initiate within the configured period. If the configured rate limit has been reached, WAF will respond according to the protective action configured. For example, if you configure **Rate Limit** to **10 requests** within **60 seconds** and **Protective Action** to **Block**, a maximum of 10 requests are allowed within 60 seconds. Once the website visitor initiates more than 10 requests within 60 seconds, WAF directly blocks the visitor from accessing the requested URL.

If you select **Advanced** for **Mode** and **Block dynamically** for **Protective Action**, configure **Rate Limit** and **Allowable Frequency**.

WAF blocks requests that trigger the rule based on **Rate Limit** first. Then, in the following rate limit period, WAF blocks requests that trigger the rule based on **Allowable Frequency** you configured. If blocking is triggered and **Allowable Frequency** is **0**, all requests that meet the rule conditions in the next period are blocked.

Differences
-----------

-  The rate limit period of **Allowable Frequency** is the same as that of **Rate Limit**.
-  **Allowable Frequency** is lower than or equal to **Rate Limit**, and **Allowable Frequency** can be **0**.
