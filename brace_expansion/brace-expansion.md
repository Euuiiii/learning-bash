## Brace-expansion


Brace expansion is a built in bash feature used to generate arbitary string combinations or sequences. It runs before any other expansion (including globbing) and does not rely on actual diles existinf on the filesystem.


syntax:  
    echo file.{txt,png,jpg} --> comma seperated lists (no spaces inside braces)

    echo {1..5} --> sequential numeric ranges

    echo {a..e} --> sequential alphabetical ranges


features:
    pattern --> example --> output --> use case 

    list expansion --> mkdir -p project/{src,bin,doc} --> project/src/ project/bin project/doc  --> creating folder structures

    file backup --> cp app.js{,.bak} --> cp app.js      app.js.bak --> quick file duplication

    zero padding --> echo {01..05} --> 01 02 03 04 05 --> sequential file generation

    stepping --> echo {0..10..2} --> 0 2 4 6 8 10 --> skipping numbers in loops

    nesting --> echo {A,B}{1..2} --> A1 A2 B1 B2 --> matrix/cartesian products


## brace expansion vs exitglob (extended globbing)

timing : brace expansion happens first before globs are evaluated
existence : brace expansion does not check if files exist. It purely generates strings
spaces : do not put unescaped spaces inside braces or bash will treat it as literal text instead of expanding it 


