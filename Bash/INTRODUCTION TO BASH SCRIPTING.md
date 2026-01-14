
**what is bash scripting?**
Bash is a command line tool to interact with your computer. Bash is also a shell
A shell allows us to enter a command and presents us with a result of those commands as an output.

TO CHANGE DEFAULT SHELL?
use command chsh

Set Alias on bash?
$ alias dt=date

Bash script: A file containing a series of commands you want the computer to execute automatically.

**Importance of bash?**
* automates task
* manage systems 
* boost efficiency *

**.sh** indicates that these are bash script .
example touch my-first-script.sh 

**Shebang (**`#!`):
- The first line in your script: `#!/bin/bash`
    
- It tells the computer to use Bash to run the script.
-the path after the !  /bin/bash represents the path to the interpreter

VIM EDITOR 
Insert mode allows you to edit file, add test or remove text

To copy text in vim or bash, move the cursor to the intended line and type on the yy on the keyboard.
to paste : move cursor to the line you want to paste and press p
to save : use upercase ZZ
To delete letter: move cursor to the letter and type x
to delete: move a cursor to the line and moce dd
to delete 3 lines from the current line : d3d
undo: type u 
to redo changes: ctrl r 
to find string: run /"string name or word " or example /genius
 ?"string" finds the string and search upwards 

#### Basic Concepts

- **Variables**:
    
    - Store values: `name="Ebrima"`
        
    - Use them: `echo "Hello, $name"`
        
- **Comments**:
    
    - Add explanations with `#`.  
        Example: `# This line says hello`
        
- **Conditionals**:
    
    - Make decisions with `if` statements.  
        Example:
        
        ```
        if [ $name == "Alice" ]; then echo "Hi Alice!" fi
        ```
        
- **Loops**:
    
    - Repeat actions with `for` or `while`.  
        Example:
        
        ```
        for i in 1 2 3; do echo "Number $i" done


Running my first script:

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


**ADDING COMMENTS ON SCRIPT**
Comments are lines in a script that are not executed as part of a code. instead act as a informative text for the one reading the script.
to add comment, start your line with a hash symbo # and anything after that will be treated as a comment 
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
