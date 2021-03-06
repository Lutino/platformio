.. _ide_qtcreator:

Qt Creator
==========

The `Qt Creator <https://github.com/qtproject/qt-creator>`_ is an open source cross-platform integrated development environment. The editor includes such features as syntax highlighting for various languages, project manager, integrated version control systems, rapid code navigation tools and code autocompletion.

This software can be used with:

* all availalbe :ref:`platforms`
* all availalbe :ref:`frameworks`

Refer to the `Sublime Text Documentation <http://doc.qt.io/qtcreator/>`_
page for more detailed information.

.. contents::

Integration
-----------

Setup New Project
^^^^^^^^^^^^^^^^^

First of all, let's create new project from Qt Creator Start Page: ``New Project`` or using ``Menu: File → New File or Project``, then select project with ``Empty Qt Project`` type (``Other Project → Empty Qt Project``), fill ``Name``, ``Create in``.

.. image:: ../_static/ide-platformio-qtcreator-1.png

On the next steps select any available kit and click Finish button.

.. image:: ../_static/ide-platformio-qtcreator-2.png

Secondly, we need to configure project with PlatformIO source code builder (click on Projects label on left menu or ``Ctrl+5`` shortcut):

.. image:: ../_static/ide-platformio-qtcreator-3.png

Thirdly, we need to add directories with header files using project file. Please fill this file with the next contents:

.. code-block:: none

    win32 {
        HOMEDIR += $$(USERPROFILE)
    }
    else {
        HOMEDIR += $$(PWD)
    }

    INCLUDEPATH += "$$HOMEDIR/.platformio/packages/framework-arduinoavr/cores/arduino"
    INCLUDEPATH += "$$HOMEDIR/.platformio/packages/toolchain-atmelavr/avr/include"

    win32:INCLUDEPATH ~= s,/,\\,g

.. image:: ../_static/ide-platformio-qtcreator-4.png

First program in Qt Creator
^^^^^^^^^^^^^^^^^^^^^^^^^^^

Simple "Blink" project will consist from two files:

1. Main "C" source file named ``main.c`` must be located in the ``src`` directory.
Let's create new text file named ``main.c`` using ``Menu: New File or Project → General → Text File``:

.. image:: ../_static/ide-platformio-qtcreator-5.png

Copy the source code which is described below to file ``main.c``.

.. code-block:: c

    #include "Arduino.h"
    #define WLED    13  // Most Arduino boards already have an LED attached to pin 13 on the board itself

    void setup()
    {
      pinMode(WLED, OUTPUT);  // set pin as output
    }

    void loop()
    {
      digitalWrite(WLED, HIGH);  // set the LED on
      delay(1000);               // wait for a second
      digitalWrite(WLED, LOW);   // set the LED off
      delay(1000);               // wait for a second
    }

2. Project Configuration File named ``platformio.ini`` must be located in the project root directory.

.. image:: ../_static/ide-platformio-qtcreator-6.png

Copy the source code which is described below to it.

.. code-block:: none

    #
    # Project Configuration File
    #
    # A detailed documentation with the EXAMPLES is located here:
    # http://docs.platformio.org/en/latest/projectconf.html
    #

    # A sign `#` at the beginning of the line indicates a comment
    # Comment lines are ignored.

    [env:arduino_uno]
    platform = atmelavr
    framework = arduino
    board = uno


Conclusion
----------

Taking everything into account, we can build project with shortcut ``Ctrl+Shift+B`` or using ``Menu: Build → Build All``:

.. image:: ../_static/ide-platformio-qtcreator-7.png
