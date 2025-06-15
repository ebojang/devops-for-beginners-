**==MY FIRST SCRIPT==** 
**"the shebang line"**
#! /bin/bash 
first create a file and at the end .sh to indicate this is a bash script.
example touch greet.sh or my-first-script.sh 
~ vi greet.sh 
#! /bin/bash
echo "Welcome king"
:wq!
NOTE
Bash script are executables therefore executable permission needs to be granted 
~ chmod +x (filename)
enter  ls -l to confirm 

To run the script the following commands can be used :
* *./(scriptname)  example ./greet.sh** 
* sh greet.sh
* bash greet.sh 
*

==**ADDING COMMENTS ON SCRIPT**==

Comments are lines in a script that are not executed as part of a code. instead act as a informative text for the one reading the script.
to add comment, start your line with a hash symbol # and anything after that will be treated as a comment 
example 
#this is my first comment 
~echo "hello world"
there are two types of comments 
single line and multi line comments 
**single line** # this is my first comment
**multi line** starts with colon (:) followed by quotation ' and closed by '
**example** 
: ' this is my second comment
    in bash'

==**TO RUN SCRIPT WITHOUT SPECIFYING ITS PATH**== 

Place script in one of the directories that are in the PATH ENVIRONMENT VARIABLE.
PATH- is an environment variable that specifies a set of directories where executable programs are located. This allows you to run programs from the command line without specifying their full paths.

RUN
**~ echo $PATH**
this gives you several directories separated by colons : 

![[Pasted image 20250615143352.png]]any executables files placed in any of these directories can be run from anywhere in the terminal 

**example run:**
sudo mv my-first-script /usr/local/bin/(name of the script)
sudo chmod +x /usr/local/bin/(name of script)
