# QAAutomation_UnixCommands

- ### grep command [Stands for Global Regular Expression Print.]
	- This command is used to used to search for text from string/file
	
	  - grep string_to_search <filename> -> This will search for string_to_search in file and display all the lines which has string "string_to_search" __	
	  - grep string_to_search <filename1> <filename2> -> Search for string string_to_search in multiple files __	
	  - grep string_to_search * -> It will search in all files in the folder __
	  - grep -r string_to_search * -> It will search in all sub directories of the current directory__	
	  - grep -w string_to_search <filename> -> this will search whole word string_to_search__	
	  - grep -i string_to_search <filename> -> This will do case insensitive search for string string_to_search, default is case sensitive__	
	  - grep -v string_to_search <filename> -> (Reverse)This will search for string_to_search in file and will display all the lines which does NOT has string "string_to_search"__	
	  - grep -x string_to_search <filename> -> This will search in a file and return lines only when string_to_search matches complete lines__	
	  - grep -l string_to_search <filename> -> it will list names of files which has matching string_to_search__	
	  - grep -c string_to_search <filename> -> this will return the count of matches__	
	  - grep -A 2 string_to_search <filename> -> search string string_to_search, return searched line and also return 2 lines after__	
	  - grep -B 2 string_to_search <filename> -> search string string_to_search, return searched line and also return 2 lines before__	
	  - grep -C 2 string_to_search <filename> -> search string string_to_search, return searched line and also return 2 lines before and after__	
	  - grep -n string_to_search <filename> -> prints the line number along with line contents matches search criteria __	
	  - grep -m3 string_to_search <filename> -> limits the number of search results (this will print only first 3 lines) __	
	  - grep -o reg_exp_string_to_search <filename> -> displays only matched values __	
	  - grep -h string_to_search <filename> -> does not displays name of file before returned line__	
	  - grep -e string_to_search1 -e string_to_search2 <filename> -> search for multiple strings in given file (this is OR search)__
	  - grep -E "string_to_search1|string_to_search2" <filename> -> earch for multiple strings in given file (this is OR search)__	
	  - grep "string_to_search1\|string_to_search2" <filename> -> earch for multiple strings in given file (this is OR search)__	
	  - grep -f <file_with_pattern> <filename> -> takes pattern from file_with_pattern file and search in given file	
	
	
- ### sed command [Stands for stream editor]	
	- This command can be used to search for a pattern in a file and replace with a new string without opening a file
	use sed -i option if you want to update the same file
	use sed -i.bak option creates a backup file before writing the source file
	
	  - sed 's/unix/linux/' <filename> -> this will replace first instance of unix with linux from each line of the file but will not update file	
	  - s in sed command represents substitution
	  - sed 's/unix/linux/g' <filename> -> this will replace all instance of unix with linux from each line the file but will not update file  
	  - sed 's/unix/linux/3' <filename> -> this will replace 3rd instance of unix with linux from each line the file but will not update file    
	  - sed 's/unix/linux/3g' <filename> -> this will replace 3rd and after that instance of unix with linux from each line the file but will not update file
	  - sed '2 s/unix/linux/' <filename> -> this will replace first instance of unix with linux from 2nd line of the file but will not update file
	  - sed '2-4 s/unix/linux/' <filename> -> this will replace first instance of unix with linux from 2nd to 4th lines of the file but will not update file
	  - sed -e 's/.*/add text &/' <filename> -> this will add string "add text" at the begining of each line
	  - sed -e 's/danger.*stops//g' <filename> -> This will delete the line with ‘danger’ on start & ‘stops’ in the end & it can have any number of words in between , ‘.*’ defines that part.
	  - sed Nd <filename> -> deletes nth line
	  - sed $d <filename> -> delete last line from the file
	
- ### awk command []
	  NOTE :- Never miss the / and / before and after a string/expression with this command	
	  
	  - awk '{ print }' <file_name/path> -> This will print all the lines from a file
	  - awk '{ print $1 }' <file_name/path> -> This will print 1st word from file (I said word here because default seperator is space)
      - awk '/<word>/ { print }' <file_name/path> -> this will print all the files which has given word
	  - awk '/^<expression>/ { print }' <file_name/path> -> This will print all the lines from the file which STARTS with the given expression
      - awk '{ if($1 ~ /<word>/) print }' <file_name/path> -> This will print all the lines from the file which has first word matching the given word
      - awk -F: '{ print $1 }' <file_name/path> -> print first word. This example is to show how to change the filter (Using option -F: ,with this filter is : (colon)) 
      - 	  

	
- ### find command 
	- This command is used to find files in directories
	
	  - find . -> This will return the list of all files and directories in the current and sub directories
	  - find <directory> -> this will return list of all the files and directtoeies in the <directory> and sub directory
	  - find . -type d -> this will ONLY return list of directories under the current and it's subdirectories
	  - find . -type f -> this will ONLY return list of files under the current and it's subdirectories 	
	  - find . -type f -name <file_name_OR_reg_exp> -> this will only list the names of files for the given name(case sensitive) or pattern under the current and it's subdirectories 	 
	  - find . -type f -iname <file_name_OR_reg_exp> -> this will only list the names of files for the given name(case insensitive) or pattern under the current and it's subdirectories 
	  - find . -size +5M -> list all the files having size more than 5 MB in current and sub Directories (+ before 5 means more than 5)
	  - find . -maxlength 1 -> list all the files in current directory ONLY
      - find . -name *.jpg -exec rm {} + -> This will remove all the files with extension .jpg from the current and sub directories
      - 	  
	  
	  
- ### find the usage of -exec with unix command ????


- ### SSH tunneling
  	- We use tunneling when we want to access a resource which has restriction of usage. lets understand more with example
 	- There are 2 types of tunnels
    		- Local port forwarding (-L)
    		- Remote port forwardning ( -R )
 
    		Note: First section of IP:PORT refers to client(from where request will be initiated) and second section of IP:PORT refers to who is going to serve (This is important to understand when doing -L and -R) 

		**Local port forwarding** :-> Use it when you want to access a service from a remote machine but that service is not exposed. Not exposed basically means that service port is restricted by firewall.

    		Example command to access it :

    		_ssh -L 127.0.0.1:2345:127.0.0.2:5432 user@remotehostip_
		- -L : local port forwarding
  		- 127.0.0.1 : This is the localhost IP address of your/client machine
    		- 2345 : This is the port of your/client machine
  		- 127.0.0.2 : This is the localhost IP address of remote machine
    			-NOTE: if remote host is a jump box and only jump box has access to other remote host whose service you want to access then specify the IP address of the other remote box
		- 5432: remote port from which you want to access service
  

		**Remote port forwardning** :-> Use it when you want service on your machine to be exposed to remote machine.

    		_ssh -R 127.0.0.1:2345:127.0.0.2:5432 user@remotehostip_
    		- -R : Remote port forwarding
    		- 127.0.0.1 : This is the localhost of the machine from where request will be sent
    		- 2345 : This is the port of client machine(here it will be remote machine making request to your machine)
    		- 127.0.0.2 : This is the localhost of your machine
    		- 5432 : This is your machine port which is exposing service on this port
    
    		
