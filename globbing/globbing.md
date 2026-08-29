Globbing --> pattern matching 	   is how bash expands windows into filenames. unlike regular expressions, globbing matched entire file or path names

wildcard operations

1. *
ls *.txt		--> lists all .txt files
rm draft*		--> removes files starting with draft 

2. ? 
ls file?.txt		--> matches file1.txt but not file10.txt

--> eg: like if we have file1.txt fileA.txt file_.txt file.txt file10.txt    then;
	matches: file1.txt    fileA.txt    file_.txt
	does not match : file.txt file10.txt

--> if we do test??.txt  -->  test followed by 2 characters ending in .txt so only file10.txt will be shown


diff in * and ? 
	--> ? = exactly one character
	--> * = any number of characters

3. [..] square brackets
ls img[123].jpg  		--> matches image1.jpg image2.jpg and image3.jpg
ls [a-z]*			--> matches file starting with lowercase letters
ls [!0-9]* or ls [^0-9]* 	--> matches files nto starting with a digit


  ------ Advance shell options -----

1. dotglob    --> includes hidden files (files starting with .) in glob expansion
	shopt -s gotglob
	echo *      #includes .gitignore .bashrc, etc

2. nullglob   --> if no files match the pattern, expands to nothing instrad of the literal string
	shopt -s nullglob 
	files=(*.jpg)  #if no JPGs exist, array becomes empty instead of holding *.jpg

3.globstar    --> enables recursive matching using **
	shopt -s globstar
	ls **/*.sh    #finds all .sh files in current directory and subdirectories 
 
