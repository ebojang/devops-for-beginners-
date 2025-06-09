
what is bash scripting?
Bash is a command line tool to interact with your computer 
Bash script: A file containing a series of commands you want the computer to execute automatically.

Importance of bash?
* automates task
* manage systems 
* boost efficiency *

**.sh** indicates that these are bash script .
example touch my-first-script.sh 

**Shebang (**`#!`):
- The first line in your script: `#!/bin/bash`
    
- It tells the computer to use Bash to run the script.
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
"the shebang line"
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



