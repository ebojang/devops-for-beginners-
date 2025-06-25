==**ERROR HANDLING**== 
Helps script stop execution without crashing. 

**SET -E**
When set-e is place in a start of a script. the script will stop executing as soon as any command returns a non zero 0 exit code.
the script stop at the error 

**SET -U** 
forces bash script to stop executing once it encounters an uninitialized variable.
example 
#!/bin/bash 
set -u

echo "the value of variable x is: $x"

once this is run. the script will stop as no variable has been defined above.

**SET -X** 
prints out each command before executing 
example1
#!/bin/bash 
set -x
echo " this is a test"
x=10
echo "the value of x is: $x"

EXAMPLE 2 OF SET -X
#!/bin/bash 
set -x
echo " this is a test"
x=10
Y=20
z=$(() x + y))
echo "the value of z is: $z"

**SET -EUX** 

#!/bin/bash 
set -eux
echo "this is a test"
echo "the value of  x is: $x"
nonexistentcommand


**extra set commands** 
set -o runs similar ways as set -u- it helps you catch uninitialized variables.

set -o errexit runs the same way as set -e