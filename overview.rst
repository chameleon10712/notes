
Programming Paradigms 程式設計範式
================================


- Imperative (procedural) 指令式程式設計

  - Machine Languages, FORTRAN, BASIC, C, Pascal
  - defines the programming process to be the development of a sequence of commands

|
- Declarative 宣告式程式設計

  - asks a programmer to describe the problem to be solved rather than an algorithm to be followed
  - database query languages (e.g., SQL, XQuery), regular expressions

|

- Object-oriented 物件導向程式設計

  - Java, C++, Visual Basic, C#
  - The object-oriented approach to a problem is to identify the objects involved and describe them as selfcontained units. 
  - polymorphism(多型)、overriding(覆寫)、overloading(多載)
  
    - `[example] <https://gist.github.com/HabaCo/a2c8ed62efc1b5d42a1c>`_
    - `[java] <https://github.com/JustinSDK/JavaSE6Tutorial/blob/master/docs/CH08.md>`_
  |
  - class
    
    - the object-oriented paradigm a template for a collection of objects is called a **class**
    - A class is a template from which objects are constructed.
  |
  - instance
  
    -  We often refer to an object as an instance of the class from which it was constructed.
  |
  - instance variable
  
    - A variable that resides within an object, such as RemainingPower, is called an **instance variable**
  |
  - methods
  
    - the procedures within an object are called **methods**
  |
  - Encapsulation 封裝
  
    - 在物件導向程式設計方法中，封裝（英語：Encapsulation）是指，一種將抽象性函式介面的實作細節部份包裝、隱藏起來的方法。同時，它也是一種防止外界呼叫端，去存取物件內部實作細節的手段，這個手段是由程式語言本身來提供的。這兩個概念有一些不同，但通常被混合使用。封裝被視為是物件導向的四項原則之一。
    - 適當的封裝，可以將物件使用介面的程式實作部份隱藏起來，不讓使用者看到，同時確保使用者無法任意更改物件內部的重要資料。它可以讓程式碼更容易理解與維護，也加強了程式碼的安全性。
    - Features that are **encapsulated** are said to be **private**. Features that are accessible from outside the object are said to be **public**.

  |
  - Generics 泛型
    
    - `[java] <https://github.com/JustinSDK/JavaSE6Tutorial/blob/master/docs/CH12.md#%E7%AC%AC-12-%E7%AB%A0-%E6%B3%9B%E5%9E%8B>`_
    

|
- Functional 

  - LISP, Haskell
  - 比起指令式編程，函數式編程更加強調程式執行的結果而非執行的過程



primitive data type 原始型別
----------------------------

- 也有稱作內建型別、基礎型別或者基本型別
- char, int, float


Composite data type
-------------------

- or compound data type
- struct (C/C++)



processor
---------

concurrency
-----------

- In computer science, concurrency is the ability of different parts or units of a program, algorithm, or problem to be executed out-of-order or in partial order, without affecting the final outcome. 


process & thread
----------------


generic
template
uml
sequence diagram
deadlock prevent
validation & verification
js concurrency


- weak type 優缺
- 優
- 缺: may perform implicit type conversion at runtime

|
|

Software Engineer
=================

- Cohesion v.s. Coupling
- UML
- sequence diagram


|
|

Computer Hardware
=================

- Processor

  - Concepts

    - Clock
    - Cache
    - Bus (FSB and BSB): Collection of wires connecting differenet devices
    - Pipeline: Implementation technique wehre multiple instructions are overlapped

  - Mesure Performance

    - Clock speed
    - type of microprocessor, the bus architecture, and the nature of the instruction set, all make a difference
      - examples : P4 3.06 GHz, P4 3.0B GHz, P4 3.0C GHz

- RAM
- Motherboard
- HardDisk
- Cards
- Ports
- BIOS
- Peripherals
- Cabinet













