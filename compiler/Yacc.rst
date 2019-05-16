=============
    Yacc
=============
%{
declarations
%}

%%

rules

%%

programs

==============
   Grammar
==============
::
	A :	body;

::
	A :	B C D ;
	A :	E F ;
	A :	G ;

	可以寫為
	A : B C D
	  | E F
	  | G
	  ;


nonterminal symbol matches the empty string::
	
	empty : ;


tokens' name declared ::
	
	%token name1 name2 . . .

start symbol ::

	%start symbol


===================
    Actions
===================


action : an arbitray C statement ::
	
	A : '(' B ')' 
				{	//action	
					hello(l,"abc");
				
				}

	XXX : YYY ZZZ
				{       printf("a message\n");
						flag = 25;
				}
	
不做事但return 1 ::

	{ $$ = 1; }


pseudo-variable 
		
		$1  $2   $3
	A :  B   C    D ;


Note                               
	prevent names beginning in "yy";
	                                
yylex 
	lexical analyzer , integered-valued func
	return token number (represent the kind of token read)

token name error
	跟保留字撞名 -> error handling

token number
	...

endmarker : token number 0 or negative











