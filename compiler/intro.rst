Compilers
============


1. Lexical Analysis

2. Parsing

3. Semantic Analysis

4. Optimization

5. Code Generation

|

Lexical Analysis
------------------


- ``Token class``

  - In English:

    - Noun, verb, adjective, ...

  - In programming lanuage:

    - ``Identifier``, ``Keywords``, ``(``, ``)``, ``Numbers``, ``White Space``, ...

|

- Classify substrings according to role (``token class``)

- Communicate tokens to the parser

  - String -> ``Lexical Analysis`` -> token <class, string> -> ``Parsing``

  - token

    - <Id, "foo">, <Op, "=">, <Int, "42">
|

- An implementation must do two things:

  - Recognize substrings corresponding to tokens
  
    - The ``lexemes`` (the words of the program)
  |
  
  - Identify the token class of each ``lexeme``
  
    - token: ``<token class, lexeme>``



Parsing
--------
  

======  ====================  =================
Phase   Input                 Output
======  ====================  =================
Lexer   String of characters  String of tokens

Parser  String of tokens      Parse tree
======  ====================  =================






