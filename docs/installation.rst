.. _installation:

Installation
============

**PlatformIO** is written in `Python <https://www.python.org/downloads/>`_ and
works on Mac OS X, Linux, Windows OS and *ARM*-based credit-card sized
computers (`Raspberry Pi <http://www.raspberrypi.org>`_,
`BeagleBone <http://beagleboard.org>`_,
`CubieBoard <http://cubieboard.org>`_).

.. contents::

System requirements
-------------------

* **Operating systems:**
    * Mac OS X
    * Linux, +ARM
    * Windows
* `Python 2.6 or Python 2.7 <https://www.python.org/downloads/>`_

All commands below should be executed in
`Command-line <http://en.wikipedia.org/wiki/Command-line_interface>`_
application:

* *Mac OS X / Linux* this is *Terminal* application.
* *Windows* this is
  `Command Prompt <http://en.wikipedia.org/wiki/Command_Prompt>`_ (``cmd.exe``)
  application.

.. warning::
    If you are going to run *PlatformIO* from **subprocess**, you
    :ref:`MUST DISABLE <faq_troubleshooting_pioblocksprompt>` all prompts.
    It will allow you to avoid blocking.


Troubleshooting
---------------

For further details, frequently questions, please refer to :ref:`faq`.

Installation Methods
--------------------

Please *choose one of* the following installation methods:

Super-Quick (Mac / Linux)
~~~~~~~~~~~~~~~~~~~~~~~~~

To install or upgrade *PlatformIO* paste that at a *Terminal* prompt
(**you might need** to run ``sudo`` first):

.. code-block:: bash

    python -c "$(curl -fsSL https://raw.githubusercontent.com/platformio/platformio/master/scripts/get-platformio.py)"


Installer Script (Mac / Linux / Windows)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

To install or upgrade *PlatformIO*, download
`get-platformio.py <https://raw.githubusercontent.com/platformio/platformio/master/scripts/get-platformio.py>`_
script. Then run the following (you might need to run ``sudo`` first):

.. code-block:: bash

    python get-platformio.py


On *Windows OS* it may look like:

.. code-block:: bash

    C:\Python27\python.exe get-platformio.py

Full Guide
~~~~~~~~~~

1. Check a ``python`` version (only 2.6-2.7 is supported):

.. code-block:: bash

    $ python --version

*Windows OS* Users only:

    * `Download Python 2.7 <https://www.python.org/downloads/>`_ and install it.
    * Add to PATH system variable ``;C:\Python27;C:\Python27\Scripts;`` and
       reopen *Command Prompt* (``cmd.exe``) application. Please read this
       article `How to set the path and environment variables in Windows
       <http://www.computerhope.com/issues/ch000549.htm>`_.


2. Check a ``pip`` tool for installing and managing *Python* packages:

.. code-block:: bash

    $ pip search platformio

You should see short information about ``platformio`` package.

If your computer does not recognize ``pip`` command, try to install it first
using `these instructions <https://pip.pypa.io/en/latest/installing.html>`_.

3. Install a ``platformio`` and related packages:

.. code-block:: bash

    $ pip install platformio && pip install --egg scons

For upgrading the ``platformio`` to new version please use this command:

.. code-block:: bash

    $ pip install -U platformio


Development Version
~~~~~~~~~~~~~~~~~~~

.. warning::
    We don't recommend to use ``develop`` version in production.

1. If you had have already installed PlatformIO, please uninstall it:

.. code-block:: bash

    $ pip uninstall platformio

2. Install the latest PlatformIO from the ``develop`` branch:

.. code-block:: bash

    $ pip install https://github.com/platformio/platformio/archive/develop.zip

If you want to be up-to-date with the latest ``develop`` version of PlatformIO,
then you need to perform step #2 each time if you see the new commits in
`PlatformIO GitHub repository <https://github.com/platformio/platformio/commits/develop>`_.
