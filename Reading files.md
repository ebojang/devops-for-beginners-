reading files allows us to access and extract valuable information from various types of files. 

WRITE TO FILE WITHIN FUNCTIONS 
write a file within a bash script using a function 

**create a file and write data using simple redirection** 
#!/bin/bash

write_to_file() {
	local file_path="$1"
	 local data="$2"
	echo "$data" >  "$file_path"
	
}
write_to_file "read.txt" "Hello world"