Both [ (brackets) and test evaluate conditional expresion in bash but they differ in syntax and capabiilties especially when compared to [[ (double brackets) 

test / [ --> POSIX standard command/builtin --> requires ] if using [ --> unquotes variables split and expand --> -a(AND), -o(OR) --> pattern/regex (basic equality --> =) 

[[ (bash extension) --> bash keyword --> requires ]] --. safe from word splitting and globbing --> && (AND) --> pattern matching (==) and regex (=~) 


key diff:

1. test and [ are identical under the hood. In fact, [ is literally the test command it just requires a closing ] as its final argument
        test -f "/etc/passwd"
        [ -f "/etc/passwd" ]       
both lines do the exact same thing 

2. [ vs [[  --> while { follows strixt POSIX standards for maximum portability across diff shells (sh, dash , zsh), [[ is enhanced suntax native to bash, zsh and ksh

 -> variabl equoting 
    #In [: fails with a syntax error if $name is empty or containes spaces
    [ $name = "Alice" ]

    #In [[: works safely without quotes even if $name is empty or has spaces
    [[ $name == "Alice"s 

--> Boolean Operators 
    #In [: uses legacy -a and -o flags
    [ "$age" -gt 18 -a "$status" = "active" ]

    #in [[: Uses standard && and || operators
    [[ $age - gt 18 && $status == "active" ]]

--> Pattern & regex matching 
    #Wildcard pattern matching
    [[ $filename = *.txt ]]
    
    #Regulat expression marchinf (eg, checks if variable is digits only)
    [[ $input =~ ^[0-9]+$ ]]

