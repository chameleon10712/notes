Naming Conventions
====================


- **_single_leading_underscore**: weak “internal use” indicator. 

  - E.g. ``from M import *`` does not import objects whose name starts with an underscore.

- **single_trailing_underscore_**: used by convention to avoid conflicts with Python keyword, e.g.:

  - .. code:: py
  
      Tkinter.Toplevel(master, class_='ClassName')






