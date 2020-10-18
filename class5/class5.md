# Bison is installed on Pandora

# task 1
add ++ and -- (from both sides)

plan:
- don't touch ParserBase (automatically generated)
- add them in while.l
    - "++"         return Parser::T_INC;
    - "--"         return Parser::T_DEC;
- add them in while.y
    - line 34: %left T_INC T_DEC
    - add them into expression part
```
|
    expression T_INC
    {
        std::cout << "expression -> expression T_INC" << std::endl;
    }
|
    expression T_DEC
    {
        std::cout << "expression -> expression T_DEC" << std::endl;
    }
|
    T_INC expression
    {
        std::cout << "expression -> T_INC expression" << std::endl;
    }
|
    T_DEC expression
    {
        std::cout << "expression -> T_DEC expression" << std::endl;
    }

```

## task 2
add for loop
versions:
- for <var> := <expr> to <expr> do <stmts> done (solved this one)
- C-style for loop (this one is similarish)
