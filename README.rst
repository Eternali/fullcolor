*********
FULLCOLOR
*********

fullcolor is a simple python module meant to make it easy to print text in full 24bit colouring. 

Instead of the usual 256 different colors, fullcolor enables users to use the full 16.7 million color gammut.
Support for this does depend on the terminal, but if unsupported, it should fallback to 256 colors with no user intervention.

Currently it provides the ability to:
 * set the foreground or background to any color that can be expressed as a 6 digit hex code or (R, G, B) tuple
 * convert between RGB, HEX (supports both 3 and 6 digit hex codes), and terminal color encodings (though this should rarely ever be used).
 * allows users to extend color modes to print in (modifying the Tmode enum will automatically update the Color classes slots)
 * reset terminal color
 * has a default set of colors for simple use cases
 * has some common functions to demonstrate use (currently this just includes a rainbow function)


USAGE:

To import base color class
.. code:: python
  from fullcolor.colors import Color

To import common colors:
.. code:: python
  from fullcolor.common import CommonColors

Sample print statements:
.. code:: python
  :linenos:
  from fullcolor.colors import Color, Tmode
  from fullcolor.common import CommonColors as cc, rainbow

  # print green background, red foreground, then reset terminal colors
  print(cc.GREEN.bg + cc.RED.fg + 'Christmas tree.' + cc.RT)

  # create custom colors and use them
  custom1 = Color('561f0a')
  custom2 = Color((100, 240, 100))
  custom3 = Color('#a02')
  print(custom1.fg + custom2.bg + 'This is gonna be ' + custom3.bg + 'ugly.' + custom1.rt)

  # print a nice rainbow
  print(rainbow())
  # customize the rainbow
  print(rainbow(cols=80, printchar='#', mode=Tmode.fg))

