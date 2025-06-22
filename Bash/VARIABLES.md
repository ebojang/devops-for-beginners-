allows us to save information for later use 

to declare variable
 myname= "ebrima"
echo command can be used to print a content of a variable.
A dollar sign $ is always needed Infront of the name of the variable when running it.
example ~ echo $myname
the variable content for myname is in "" example "ebrima"

**run below variable example** 
vim script name 
vim myfirstscript.sh
#! /bin/bash

name=ebrima
age=20

echo "my name is $name."
echo "i am $age years old."
wq!

run
./myfirstscript


PARAMETERS

when running a script, ypu provided parameter after the script name separated by spaces.

example
./myfirstscript.sh hello hi goodby 
edit script and insert parameter 

#! /bin/bash
echo "parameter 1: $1"
echo "parameter 2: $2"
echo "parameter 3: $3"

when executing script with parameters the values passed on the command line will be substituted into the scripts parameters

**to access all parameters passed into a script  insert the below special variable** 
echo "all parameters: $@"
"





