## Context-free grammars:

Online tool to try/test/play with: https://web.stanford.edu/class/archive/cs/cs103/cs103.1156/tools/cfg/ (Links to an external site.)

Non terminals to the left

S -> aA | b
A -> c | cA

b
ac
acc
accc
...

## task 1
Let's create a context-free grammar to recognize&check the syntax of a list like this:

[apple; pear; plum]

Terminal symbols of the grammar are:
o (open bracket), e (element), s (semicolon), c (closing bracket)

So the upper list should be recognized as: oesesec
Other valid worlds are: oc, oec, oesec etc.

S -> oc | oAc
A -> esA | e

## task 2
Let's create a context free grammar to recognize C sytle function declarations:

char is_part( string s, int index );
int total_sum( int x, int y );

Terminal symbols:
id (identifier), op (open parenthesis), cp (closing parenthesis), co (comma), se (semicolon)

The above example should be recognized as id id op id id co id id cp se id id op id id co id id cp se

S -> id id op A cp se S | id id op cp se | empty
A -> id id | id id co A


## task 3

First create a simple lexical analyzer (a few regexps for variables, number literals, keywords, assignment operator, whitespace) to recognize the below example as a sequence of words. Then create a context-free grammar to describe the syntax of this simple language.

!x1 := 5
if !x1 odd then !2y := 4
if !2y even then !x1 := 2


S -> STATEMENTS
STATEMENTS -> STATEMENT | STATEMENT STATEMENTS
STATEMENT -> ASSIGNMENT | IF
ASSIGNMENT -> var assign constant
IF -> if var COND then ASSIGNMENT
COND -> even | odd

extension1: Right hand side of operator should handle variable names

S -> STATEMENTS
STATEMENTS -> STATEMENT | STATEMENT STATEMENTS
STATEMENT -> ASSIGNMENT | IF
ASSIGNMENT -> var assign EXPR
IF -> if var COND then ASSIGNMENT
COND -> even | odd
EXPR -> constant | variable
