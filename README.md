# QAAutomation_UnixCommands

- ### grep command [acronym that stands for Global Regular Expression Print.]
	- This command is used to used to search for text from string/file
	
	. grep string_to_search <filename> -> This will search for string_to_search in file and display all the lines which has string "string_to_search" __
	. grep string_to_search <filename1> <filename2> -> Search for string string_to_search in multiple files __
	. grep string_to_search * -> It will search in all files in the folder __
	. grep -r string_to_search * -> It will search in all sub directories of the current directory__
	. grep -w string_to_search <filename> -> this will search whole word string_to_search__
	. grep -i string_to_search <filename> -> This will do case insensitive search for string string_to_search, default is case sensitive__
	. grep -v string_to_search <filename> -> (Reverse)This will search for string_to_search in file and will display all the lines which does NOT has string "string_to_search"__
	. grep -x string_to_search <filename> -> This will search in a file and return lines only when string_to_search matches complete lines__
	. grep -l string_to_search <filename> -> it will list names of files which has matching string_to_search__
	. grep -c string_to_search <filename> -> this will return the count of matches__
	. grep -A 2 string_to_search <filename> -> search string string_to_search, return searched line and also return 2 lines after__ 
	. grep -B 2 string_to_search <filename> -> search string string_to_search, return searched line and also return 2 lines before__
	. grep -C 2 string_to_search <filename> -> search string string_to_search, return searched line and also return 2 lines before and after__
	. grep -n string_to_search <filename> -> prints the line number along with line contents matches search criteria __
	. grep -m3 string_to_search <filename> -> limits the number of search results (this will print only first 3 lines) __
	. grep -o reg_exp_string_to_search <filename> -> displays only matched values
	. grep -h string_to_search <filename> -> does not displays name of file before returned line
	. grep -e string_to_search1 -e string_to_search2 <filename> -> search for multiple strings in given file (this is OR search)
	. grep -E "string_to_search1|string_to_search2" <filename> -> earch for multiple strings in given file (this is OR search)
	. grep "string_to_search1\|string_to_search2" <filename> -> earch for multiple strings in given file (this is OR search)
	. grep -f <file_with_pattern> <filename> -> takes pattern from file_with_pattern file and search in given file	
	
	
	