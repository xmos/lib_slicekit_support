.. include:: ../../../README.rst

API
---

This library runs a some initial code on booting to configure the ports
for the sliceKIT Core Board to either route ports 1A,1B,1C and 1D on
tile[0] to the SPI flash during the application or to the STAR and
TRIANGLE slice card slots.

To use the library just include it in the USED_MODULES list in your
application makefile. There is no need to call any specific function
in your application, the code will run on boot automatically.

The default is to route the ports to the slice card slots. SPI Flash
will still work for booting but cannot be accessed during the
application. To route these ports to flash during the application
create a ``slicekit_conf.h`` file in your application and set the
following define::

  #define SLICEKIT_ENABLE_FLASH 1

If you do enable flash, then clearly you will not be able to access
the pins on the slice cards connected to these ports.

If this library is used when the application target is not
``SLICEKIT-L2``, ``SLICEKIT-U16``, ``SLICEKIT-A16`` or
``SLICEKIT-L16`` then this module will do nothing.

|appendix|

Known Issues
------------

There are no known issues.

.. include:: ../../../CHANGELOG.rst
