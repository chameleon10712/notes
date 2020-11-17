Terms
=======

Callable
----------

A callable is anything that can be called.


- `Stackoverflow - What is a “callable”? <https://stackoverflow.com/a/111255>`_



|

Metaclass
------------

A metaclass is the class of a class. A class defines how an instance of the class (i.e. an object) behaves while a metaclass defines how a class behaves. A class is an instance of a metaclass.

- `Stackoverflow - What are metaclasses in Python? <https://stackoverflow.com/a/100146>`_


|


Mixin
-------

In ``object-oriented programming languages``, a ``mixin`` (or ``mix-in``) is a class that contains methods for use 
by other classes without having to be the parent class of those other classes. 
How those other classes gain access to the mixin's methods depends on the language. 
Mixins are sometimes described as being "included" rather than "inherited".

Mixins encourage code reuse and can be used to avoid the inheritance ambiguity 
that multiple inheritance can cause(the "``diamond problem``"),
or to work around lack of support for multiple inheritance in a language.
A mixin can also be viewed as an interface with implemented methods. 
This pattern is an example of enforcing the ``dependency inversion principle``.


- **Diamond Problem**

  .. raw:: html

    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/8/8e/Diamond_inheritance.svg/440px-Diamond_inheritance.svg.png" width="100px">



- **Dependency Inversion Principle**

  - In object-oriented design, the dependency inversion principle is a specific form of decoupling software modules. 
    When following this principle, the conventional dependency relationships established from high-level, 
    policy-setting modules to low-level, dependency modules are reversed, thus rendering high-level modules 
    independent of the low-level module implementation details. The principle states:
    
    |
    1. High-level modules should not depend on low-level modules. Both should depend on abstractions (e.g., interfaces).
    2. Abstractions should not depend on details. Details (concrete implementations) should depend on abstractions.


|
