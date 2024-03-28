.. _`Setup new agent`:

Setup new agent
===============================

.. _`Nimbus`: index.md
.. _`Nimbus Agent`:

.. image:: img/Tux.png
   :width: 60
   :target: #lin_install


.. image:: img/Win.png
   :width: 60
   :target: #win_install

Overview
--------

To manage and interact with a robot, the Nimbus agent must be installed.

The Nimbus agent:

- Connects robots to Nimbus cloud services
- Installs Nimbus system software and dependencies
- Installs and manages robot configurations (devices and components)
- Gathers platform data and monitors robot status
- Enables robots to be controlled from Nimbus

.. _lin_install:

Install the nimbus agent
----------------------------

To create a new robot instance and install the Nimbus agent on your target platform (robot).

1. In the **Side bar** (navigation) pane, click **Robots**, then click **+ Create new robot**.

2. Choose your license.

3. Enter a unique name for your new robot.

4. Click **+Create**.

   A new robot instance is created and assigned to the designated fleet.

   A Linux command, containing a unique API key, is displayed. This API key is also emailed to you.

5. Your new robot's name appears in the **Robots** tab.

6. To install the Nimbus agent, copy the displayed Linux command and execute it from a terminal connected to your robot.

   In the **Robots** tab, the robot's name is listed with a green indicator.

**Note**: To display the agent installation line, enter the command ``nimbus system link``.

.. _`purchased license`: https://www.cognimbus.com/pricing


.. _win_install:

WSL2 support (WIP)
----------------------------

- It is possible to install the agent on Win11 Ubuntu 22.04 from admin powershell using
.. code-block:: bash
   :linenos:

   wsl –install

- Docker client should be installed before running the agent install script. Make sure you are able to run inside WSL2
.. code-block:: bash
   :linenos:

   docker 

- Since systemd is not yet seamlessly supported (July 2023) you will need to stop the service 

.. code-block:: bash
   :linenos:

   sudo service nimbus stop 

and run manually the agent using

.. code-block:: bash
   :linenos:

   sudo /bin/nimbusd 

- Please note that usb passthrough is only supported through Usbipd-win (WIP)




The Nimbus agent CLI
----------------------------

Overview

Many tasks performed from the Nimbus web graphical user interface (GUI) also can be accomplished through the Nimbus agent command line interface (CLI). The CLI is accessed from a terminal connected (directly or remotely) to the target (robot) platform"s, CPU board, after the Nimbus software is installed and a unique API key has been assigned to the Nimbus agent. This document explains the significance and use of each Nimbus agent command. For each command, one or more use examples are provided

The Nimbus agent

The Nimbus agent is installed as a remote procedure call (RPC) service on the robot platform. Whether using the Nimbus web GUI or the CLI, user interaction with robots connected to Nimbus Cloud Services is facilitated by the Nimbus agent.

The Nimbus Agent:

- Establishes connection between the platform and Nimbus cloud services
- Installs on the platform the Nimbus agent daemon and application dependencies
- Gathers platform information
- Installs component configurations
- Monitors connected device drivers and algorithms