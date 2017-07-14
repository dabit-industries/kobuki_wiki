.. _chapter_basic_usage:

Basic Usage
===========
.. WARNING:: Make sure to be aware of the `safety guidelines`_.

Charging
--------
Connect the power adapter to Kobuki or dock Kobuki in the docking station. If Kobuki is turned on, you will hear a short sound when charging starts and the LED will light up appropriately.

.. |blink green| replace:: :blink-green:`Blinking Green`

+------------------+---------------+
| LED Color        | Status        |
+==================+===============+
| :green:`Green`   | fully charged |
+------------------+---------------+
| |blink green|    | charging      |
+------------------+---------------+
| :orange:`Orange` | low battery   |
+------------------+---------------+

.. NOTE:: The battery still charges if Kobuki is off, but you will not see the LED, nor hear sounds

First Run
---------
You want to see Kobuki in action without further ado? Kobuki has a special random walker mode embedded into the firmware which you can activate on start-up:

#. Turn on Kobuki.
#. Within the first 3 seconds press the B0 button and hold for 2 seconds.
#. LED2 will start blinking and Kobuki wander around.

.. NOTE:: This was introduced to the firmware in v1.1.0. In case your kobuki is not running this or a later version, please refer to the section about updating the firmware.

Software
--------
In order to gain access to all of Kobuki’ s features, you will need an external computing unit (pc/laptop/tablet/embedded board) with software which communicates with Kobuki. Officially supported systems include:

Build Your Own Kobuki Driver
Use the `Serial Protocol`_

Linux C++ Application
Use the `Kobuki C++ Driver`_

Kobuki for ROS
Use the `Kobuki ROS World`_

Alternatively, you can get started with the Turtlebot 2 Platform which runs on a Kobuki base.

.. NOTE:: Other platforms have had experimental support at one stage or another (windows/arduino/android).

Problems
--------
Reach out on the following channels:

- Kobuki User’s Mailing List: kobuki-users@yujinrobot.com
- ROS Community Answers:  http://answers.ros.org/questions/tags%3Akobuki
- Yujin Sales Support: kobuki@yujinrobot.com
- Dabit Industries Support: support@dabitindustries.com

.. NOTE:: Kobuki comes with a 1 year warranty. In case you bought Kobuki from another one of Yujin Robot’s distributors, please contact them, otherwise email Yujin Sales Support.

.. _safety guidelines: #
.. _Serial Protocol: http://yujinrobot.github.io/kobuki/enAppendixProtocolSpecification.html 
.. _Kobuki C++ Driver: http://yujinrobot.github.io/kobuki/enMainPage.html
.. _Kobuki ROS World: http://wiki.ros.org/kobuki/Tutorials/ 
.. _Turtlebot 2 Platform: http://wiki.ros.org/Robots/TurtleBot
