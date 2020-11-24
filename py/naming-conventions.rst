Naming Conventions
====================

Naming Styles
----------------

- **_single_leading_underscore**: weak “internal use” indicator. 

  - E.g. ``from M import *`` does not import objects whose name starts with an underscore.

- **single_trailing_underscore_**: used by convention to avoid conflicts with Python keyword, e.g.:

  - .. code:: py
  
      Tkinter.Toplevel(master, class_='ClassName')



Class Names
--------------


Class names should normally use the CapWords (CamelCase) convention.



Function Names
-----------------

Function names should be lowercase, with words separated by underscores as necessary to improve readability.




