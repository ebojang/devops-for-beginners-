A **function** in Bash is a **reusable block of code that performs a specific task**. Functions help structure your script and avoid repeating code.
functions are defined using the function name, followed by () {
}
example
 #!/bin/bash
hello_world() {

	echo "Hello King"
}
 hello_world 


functions also accept parameters. example 
 #!/bin/bash

hello_world() {

    echo "Hello King"
}
greet() {

    name="$1"

    echo "hello $name"
}
greet "king"


PARAMETERS IN FUNCTION 

$# = number of arguments
$0 = name of the script 
$@ = for all arguments 

read command is used for interactive prompt in functions 

greet(){
local name
if [ $# -eq 0 ]
echo "what is your name"
read name 
else 
name="$1"
fi
echo "hello, $name"
}
greet