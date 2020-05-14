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

- Classify substrings according to role (token class)
- Communicate tokens to the parser

  - String -> ``Lexical Analysis`` -> token <class, string> -> ``Parsing``

  - token

    - <Id, "foo">, <Op, "=">, <Int, "42">
  
  
  
