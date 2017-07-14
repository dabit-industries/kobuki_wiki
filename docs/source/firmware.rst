.. _chapter_firmware:

Firmware
========

Communication
-------------
- Baud rate: 115200 BPS, Data bit: 8 bit, Stop bit: 1 bit, No Parity
- Electronic protocol: USB / RS232 (@ DB25 connector)

Protocol Specification
----------------------
The driver communicates with the robot by using predefined protocol. In general, the driver sends the commands to the robot and the robot sends some feedback data or sensor readings. This command and feedback data are converted into bytestreams for communication via serial interface. The protocol specify that rules and forms of bytestream.

For more detailed information, visit:
- http://yujinrobot.github.com/kobuki/enAppendixProtocolSpecification.html

Version Checking
----------------
Every time the robot comes alive (because it is connected or powered on), the driver checks the compatibility between software (i.e. driver) and firmware. Firmware versions are of the form M.m.p, where:

- M(ajor) represents a deep rebuild of the code that almost surely breaks protocol compatibility. In consequence, if mayor version doesn’t match, the driver will show an error, suggest the required update and shutdown.
- m(inor) represents a new feature that could not work if the driver is outdated, but the protocol itself is spared. In consequence, if minor version doesn’t match, the driver will show a warning suggesting the required update and continue working.
- p(atch) represents a fix on the code and is not checked at all.

You can check which firmware version your robot is running on the log (check the first lines on stdout at driver startup), by running the version_info program included on the kobuki driver, or if you are using ROS, just echoing /mobile_base/version_info topic. Generally speaking, it’s recommended to upgrade the firmware to the latest stable version.

Special Firmware Modes
----------------------

Activating
~~~~~~~~~~
Kobuki has some special firmware modes, which can be activated on startup.
Currently implemented are:
#. Random walker mode
#. Arduino/Embedded board support mode

To activate one of them, follow these instructions:
#. Turn on Kobuki.
#. Within in the first 3 seconds press and hold button BO(I) / B1 (II) for 2 seconds.
#. If you see LED2(I) / LED1(II) switching between red and green, your chosen mode is activated.

.. NOTE:: These modes have been introduced to the firmware with version 1.1.0. In case your Kobuki is not running this or a later version, please refer to the section about updating the firmware.

Random Walker Mode
~~~~~~~~~~~~~~~~~~
In the random walker mode Kobuki is driving around until it hits an object with the bumper or a cliff is detected. In both cases, Kobuki will stop, turn by a random amount of degrees and continue driving .

.. NOTE:: In this mode Kobuki’s wheel drop sensors are not activated. So, be careful when lifting up Kobuki!

Arduino / Embedded Board Support Mode
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
In this mode the serial port (DB25 connector) gives access to basic controls of Kobuki. You can hook up the digital/analog inputs/outpus of your Arduino or other embedded boards and start writing simple control programs.

Below is the special pin setting listed. Please refer to the serial port description for the name to pin mapping.
- DI0: Not used
- DI1: Not used
- DI2: Not used
- DI3: Not used
- DO0: Bumper left (pressed/released)
- DO1: Bumper centre (pressed/released)
- DO2: Bumper right (pressed/released)
- DO3: Wheel drop sensors (at least one wheel is dropped / none is dropped)
- AI0: Wheel speed right (0V - full speed backward, 3.3V - full speed forward)
- AI1: Wheel speed left (0V - full speed backward, 3.3V - full speed forward)
- AI2: Not used
- AI3: Not used

All other pins (GND, RX, TX etc.) remain unchanged.

.. NOTE:: To enable the motors you need to press button B0.

