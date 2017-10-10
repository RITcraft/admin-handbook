Managing ritcraft.net domain
============================

One of the important parts of RITcraft is our domain, used both for the website
and logging into our Minecraft server. This page documents how it is managed
and how to get help with it.


Contact information
-------------------

Owner:
  Justin W. Flory
Contact:
  jflory7 [at] gmail [dot] com
Item(s):
  \*.ritcraft.net
Purpose:
  Domain name for players to more easily find us on the Internet


Description
-----------

The ``ritcraft.net`` domain is registered to `Justin W. Flory`_ by
`Namecheap`_. The DNS nameservers were migrated from Namecheap to a
`CloudFlare`_ account. This provides a free `Content Delivery Network`_ (CDN)
for serving the main website.

The domain renewal costs are typically reimbursed to Justin from the EGS club
budget. This should be coordinated annually near the domain's expiry date.
Historically, the yearly cost is **$15.76** [1]_.

.. _`Justin W. Flory`: https://justinwflory.com
.. _`Namecheap`: https://www.namecheap.com
.. _`CloudFlare`: https://www.cloudflare.com/
.. _`Content Delivery Network`: https://en.wikipedia.org/wiki/Content_delivery_network


Current records
---------------

As of **2017-10-08**, the most important DNS records are listed here for easy
reference.

A records
^^^^^^^^^

+--------------+----------------+----------+
| Name         | Value          | CF? [2]_ |
+==============+================+==========+
| ritcraft.net | 158.69.211.161 | Y        |
+--------------+----------------+----------+

CNAME records
^^^^^^^^^^^^^

+--------------+-------------------------+----------+
| Name         | Value                   | CF? [2]_ |
+==============+=========================+==========+
| handbook     | readthedocs.io          | N        |
+--------------+-------------------------+----------+
| mc           | arguru.justinwflory.com | N        |
+--------------+-------------------------+----------+
| www          | ritcraft.net            | Y        |
+--------------+-------------------------+----------+

SRV records
^^^^^^^^^^^

+---------------------+--------------------------------+
| Name                | Value                          |
+=====================+================================+
| _minecraft._tcp.mc. | SRV 1 1 30000 mc.ritcraft.net. |
+---------------------+--------------------------------+
| _minecraft._udp.mc. | SRV 1 1 30000 mc.ritcraft.net. |
+---------------------+--------------------------------+

.. [1] Includes domain and whois protection (i.e. prevents phone number and
   permanent address from becoming searchable, public records)
.. [2] Is DNS managed by CloudFlare?

