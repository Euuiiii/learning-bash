
## Parens 

Syntax: (...)  $(...)

--> Executes commands in a seperate child process
--> variable changes inside donot affect the main subject 
--> eg: (cd /tmp && touch file)


## Curly 

Syntax: {...;}  ${...;}

--> groups commands in the curr shell 
--> variables change will affect the active script 
--> { cd /tmp; touch file;)

