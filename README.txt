Zend XMLRPC Vulnerabilities Fix

Vulnerability overview/description:
-----------------------------------
The XmlRpc package of Zend Framework is vulnerable to XML eXternal Entity
Injection attacks (both server and client). The SimpleXMLElement class
(SimpleXML PHP extension) is used in an insecure way to parse XML data.
External entities can be specified by adding a specific DOCTYPE element to
XML-RPC requests. By exploiting this vulnerability an application may be
coerced to open arbitrary files and/or TCP connections.

Other software that uses the XmlRpc package of Zend Framework is then also
vulnerable to XML eXternal Entity Injection attacks!

Fix:
----

Call to the libxml_disable_entity_loader function before initializing the 
SimpleXMLElement class

References:
-----------

https://www.sec-consult.com/files/20120626-0_zend_framework_xxe_injection.txt
http://www.magentocommerce.com/blog/comments/important-security-update-zend-platform-vulnerability/

Authors:
--------

Skywire - www.skywire.co.uk