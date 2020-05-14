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
--

- LA Examples

  
  .. code::
    
    if(i==j)
      z = 0;
    else
      z = 1;
  
  - ``lookahead``
  
    - 在 parsing 到 ``else`` 的 ``e`` 的時候，需要先看下一個 character 才能決定 ``e`` 是單獨的字還是屬於其他 token 的一部分 (``else`` 的一部分)，這個動作叫做 ``lookahead``
    - minimize the amount of ``lookahead`` will simplify the implementation of LA
    - Maximal Munch (or longest match)
    
      - 例如在 ``==`` 的 case 裡面， ``=`` 跟 ``==`` 都符合定義，這時候選 longest match ``==``
  
  |
  - ``unbounded lookahead``
  
|

Parsing
--------
  

======  ====================  =================
Phase   Input                 Output
======  ====================  =================
Lexer   String of characters  String of tokens

Parser  String of tokens      Parse tree
======  ====================  =================






