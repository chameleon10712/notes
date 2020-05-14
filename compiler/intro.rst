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

- Classify substrings according to role (``token class``)

  - Token class
  
    - In English:
      
      - Noun, verb, adjective, ...
      
    - In programming lanuage:
    
      - Identifier, Keywords, '(', ')', Numbers, ...

- Communicate tokens to the parser

  - String -> ``Lexical Analysis`` -> token <class, string> -> ``Parsing``

  - token

    - <Id, "foo">, <Op, "=">, <Int, "42">
|

- An implementation must do two things:

  - Recognize substrings corresponding to tokens
  
    - The ``lexemes``
  |
  
  - Identify the token class of each ``lexeme``



Parsing
--------
  

======  ====================  =================
Phase   Input                 Output
======  ====================  =================
Lexer   String of characters  String of tokens

Parser  String of tokens      Parse tree
======  ====================  =================






