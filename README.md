# QAAutomation_UnixCommands

- ### grep command [Stands for Global Regular Expression Print.]
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
	
	
- ### sed command [Stands for stream editor]	
	- This command can be used to search for a pattern in a file and replace with a new string without opening a file
	use sed -i option if you want to update the same file
	use sed -i.bak option creates a backup file before writing the source file
	
	. sed 's/unix/linux/' <filename> -> this will replace first instance of unix with linux from each line of the file but will not update file
	  - s in sed command represents substitution
	. sed 's/unix/linux/g' <filename> -> this will replace all instance of unix with linux from each line the file but will not update file  
	. sed 's/unix/linux/3' <filename> -> this will replace 3rd instance of unix with linux from each line the file but will not update file    
	. sed 's/unix/linux/3g' <filename> -> this will replace 3rd and after that instance of unix with linux from each line the file but will not update file
	. sed '2 s/unix/linux/' <filename> -> this will replace first instance of unix with linux from 2nd line of the file but will not update file
	. sed '2-4 s/unix/linux/' <filename> -> this will replace first instance of unix with linux from 2nd to 4th lines of the file but will not update file
	. sed -e 's/.*/add text &/' <filename> -> this will add string "add text" at the begining of each line
	. sed -e 's/danger.*stops//g' <filename> -> This will delete the line with ‘danger’ on start & ‘stops’ in the end & it can have any number of words in between , ‘.*’ defines that part.
	. sed Nd <filename> -> deletes nth line
	. sed $d <filename> -> delete last line from the file
	
- ### awk command []
	- 	