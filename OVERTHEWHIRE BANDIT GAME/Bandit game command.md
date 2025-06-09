stage 5-6
to find a file using size 
find . -type f -size 1033c

(find .) looks for all the files and directories with the dot meaning starting from the current dir
stage 6-7
to find password on the server and owner name is bandit 7 group name bandit 6 size 33
run the below command 
find / -type f -user (usernsme) -group (groupname) -size33 (c represents bytes) **`2>/dev/null`**

-Note:  `2>/dev/null` → Suppresses permission errors from directories you can't access
run cat command filename to access content 

The password for the next level is stored in the file **data.txt** next to the word **millionth**
run command: grep millionth data.txt

when you use grep -l "word" filename - it searches for the name word in the file. it becomes case insensitive .



