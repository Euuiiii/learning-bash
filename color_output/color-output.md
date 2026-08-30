In bash, we disply color output by printing ANSI escape sequences with echo -e or printf

an ANSI escape code starts with \e[ (or \033[ ), followed by a color code and ends with m. Always end your text with \e[0m to reset the terminal color back to default 

## Basic Text Colors 

echo -e "\e[32mHello World\e[0m"   --> print green text

printf "\003[31mError: Operation failed\033[0m\n" --> print red text using printf --> recommended for scripts

## text formatting & backgrounds 
-> Reset : \e[0m  (clears all styling)
-> Bold : \e[1m
-> Underline : \e[4m
-> bg colors : range from \e[40m (black) to \e[47m (white)

