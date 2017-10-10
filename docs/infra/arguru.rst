Server: Arguru
==============

Arguru is the machine that hosts the RITcraft server. This page documents how
it is used and configured and other information.


Contact information
-------------------

Owner:
  Justin W. Flory
Contact:
  jflory7 [at] gmail [dot] com
Item(s):
  Intel i7-4790S Rosewill computer system
  (arguru.justinwflory.com)
Purpose:
  Host and run the RITcraft Minecraft server and various MySQL databases


Description
-----------

Arguru is a `Red Hat Enterprise Linux`_ (RHEL) 7 Server running on a self-built
machine [#]_. Arguru is inside of the `Electronic Gaming Society at RIT`_'s "club
space", a locked room in the basement of the Student Alumni Union (SAU).

The server is primarily managed by `Justin W. Flory`_ and other system
administrators (see :doc:`../roles/sysadmin` for more information about their
role). 

.. [#] While used officially for RITcraft, the machine is the personal
   property of the RITcraft founder, `Justin W. Flory`_
.. _`Electronic Gaming Society at RIT`: http://egsrit.com/
.. _`Justin W. Flory`: https://justinwflory.com
.. _`Red Hat Enterprise Linux`: https://en.wikipedia.org/wiki/Red_Hat_Enterprise_Linux


Server specs
------------

A build part list and specs can be found on `PCPartPicker`_.

- `Part list`_

- `Price breakdown by merchant`_

+----------------------+----------------------------------------------+-------------+
| Type                 | Item                                         | Price       |
+======================+==============================================+=============+
| **CPU**              | `Intel Core i7-4790S 3.2GHz Quad-Core`_      | $305.48     |
+----------------------+----------------------------------------------+-------------+
| **Motherboard**      | `ASRock H97M Anniversary Micro ATX LGA1150`_ | $71.98      |
+----------------------+----------------------------------------------+-------------+
| **Memory**           | `Team Elite Plus 8GB (2 x 4GB) DDR3-1600`_   | $36.99      |
+----------------------+----------------------------------------------+-------------+
| **Memory**           | `Team Elite Plus 16GB (2 x 8GB) DDR3-1600`_  | $72.99      |
+----------------------+----------------------------------------------+-------------+
| **Storage**          | `Seagate Barracuda 2TB 3.5" 7200RPM HD`_     | $74.99      |
+----------------------+----------------------------------------------+-------------+
| **Case**             | `Rosewill FBM-02 MicroATX Mini Tower Case`_  | $21.99      |
+----------------------+----------------------------------------------+-------------+
| **Power Supply**     | `Rosewill 550W 80+ Platinum Modular ATX`_    | $74.99      |
+----------------------+----------------------------------------------+-------------+
| **Operating System** | `Red Hat Enterprise Linux 7`_                | Free        |
+----------------------+----------------------------------------------+-------------+
| **Total**            |                                              | **$659.41** |
+----------------------+----------------------------------------------+-------------+

*Note*: Prices include shipping, taxes, rebates, and discounts

.. _`PCPartPicker`: https://pcpartpicker.com/b/tBnnTW
.. _`Part list`: https://pcpartpicker.com/list/Zqx2WX
.. _`Price breakdown by merchant`: https://pcpartpicker.com/list/Zqx2WX/by_merchant/
.. _`Intel Core i7-4790S 3.2GHz Quad-Core`: https://pcpartpicker.com/product/YZg323/intel-cpu-bx80646i74790s
.. _`ASRock H97M Anniversary Micro ATX LGA1150`: https://pcpartpicker.com/product/YDrG3C/asrock-motherboard-h97manniversary
.. _`Team Elite Plus 8GB (2 x 4GB) DDR3-1600`: https://pcpartpicker.com/product/9BDzK8/team-memory-tpd38g1600c11dc01
.. _`Team Elite Plus 16GB (2 x 8GB) DDR3-1600`: https://pcpartpicker.com/product/xNnG3C/team-memory-tpd316g1600c11dc01
.. _`Seagate Barracuda 2TB 3.5" 7200RPM HD`: https://pcpartpicker.com/product/KyCwrH/seagate-internal-hard-drive-st2000dm001
.. _`Rosewill FBM-02 MicroATX Mini Tower Case`: https://pcpartpicker.com/product/tm9KHx/rosewill-case-fbm02
.. _`Rosewill 550W 80+ Platinum Modular ATX`: https://pcpartpicker.com/product/FPs8TW/rosewill-power-supply-quark550
.. _`Red Hat Enterprise Linux 7`: https://redhat.rit.edu


PaperSpigot server
------------------

RITcraft uses `PaperSpigot`_ to run the Minecraft server. This is a fork of the
`SpigotMC`_ project with a few added features and configurations that are good
for a classic, multiplayer server.

The server runs at ``mc.ritcraft.net`` and is run on port 30000. Since port
forwarding is enabled, players connect with the default ``:25565`` port and
they will reach the server.

A simple Bash script is run inside of a new `tmux`_ session to run the server:

.. code:: bash

   java -Xms2048M -Xmx2048M -jar rit-survival-spigot.jar

Copies of the configurations and world are backed up weekly into the Google
Cloud Platform.

.. _`PaperSpigot`: https://github.com/PaperMC/Paper
.. _`SpigotMC`: https://www.spigotmc.org/wiki/about-spigot/
.. _`tmux`: https://en.wikipedia.org/wiki/Tmux


MySQL databases
---------------

Arguru also hosts various MySQL databases used for RITcraft and also other
servers running on the machine. A record of the databases is kept here.

+-----------------------+--------------------+------------------+-----------------------+
| Databases                                                                             |
+=======================+====================+==================+=======================+
| information_schema    | mysql              | rit_logblock     | space_voteroulette    |
+-----------------------+--------------------+------------------+-----------------------+
| creative_logblock     | performance_schema | rit_tradingpost  | space_zPermissions    |
+-----------------------+--------------------+------------------+-----------------------+
| creative_plotme       | reportrts          | rit_zPermissions | survival_logblock     |
+-----------------------+--------------------+------------------+-----------------------+
| creative_zPermissions | rit_dynmap         | space_logblock   | survival_zPermissions |
+-----------------------+--------------------+------------------+-----------------------+
