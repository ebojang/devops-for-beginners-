if statement allows you to make a decision and execute different code block based on conditions. Conditions are formed using comparison  and logical operators.
IF SCRICPT TEMPLATE 
if (code block to be executed )
then 
(echo "code block statement)
fi 

NOTE:
The code block statement is always between the **"then and fi"

conditions in the IF **statement are formed using comparison operators
Example 
eq= equals ne= not equal to le=less than  gt = greater than 

==**Combine TWO OR MORE IF STATEMENTS**== 
Example 
#!/bin/bash
mynum=200
if ( $mynum -eq 200)
 then 
    echo "you are a star."
   else 
	   echo "the variable does not equal to 200."
fi 

ADDITIONAL INFO 
An ! before the conditional block reverses the check 
example 
#!/bin/bash
mynum=200
if ( !  $mynum -eq 200)
 then 
    echo "you are a star."
   else 
	   echo "the variable does not equal to 200."
fi 

when we run this script, 
it will echo 
"the variable does not equal to 200"

**NESTED IF STATEMENT** 
allows the evaluation of multiple conditions and execution of code blocks based on the results

example 
exam
#!/bin/bash
Age=20
Grade=85
if [ $age -gt 20 ] ; then
	echo "you are eligible based on age "
	if [  $grade -ge 80 ] ; then
	 echo " you are eligible based on grade."	
	 echo " you are eligible for scholarship."
fi
   else 
	   echo "sorry your grade is not high enough"
	else 
		echo "sorry, you are not eligible for scholarship."   
fi 


**ELSELIF**
means else if 
if the previous statement is not correct or true try this if statement 


==**EXIT CODES IN BASH**== 
let us know whether a previous command was successful or failed.
to run exit code 
run echo $?
if successful it will give you 0
when unsuccessful it will give you 1 or more 
example ls -l /etc
echo $?

==**while loops**==
while loops continues to run until a particular condition is met only then it will stop running.
it starts with keyword while (condition)

#!/bin/bash 
while ( -f ~/testfile )
do 
	echo "the test file exist"
done
echo "the file no longer exist"


==**FOR LOOPS**== 
are used for automating tasks or
executing a set of commands against each items in a set

#!/bin/bash 
for (( i=1; i<=5; 1++)) 
do 
	echo "Number: $i"
done
echo "the file no longer exist"

**BREAK AND CONTINUE** 

Gives you the flexibility to interupt a loop when necessary
**EXAMPLE OF BREAK** 

#!/bin/bash 
for (( i=1; i<=5; i++)) 
do 
	 If [ $1 -eq 3 ]
	 then
		 break
		fi	 
	echo "Number: $i"
done
this ends the the loop prematurely.


**example of continue statement**

#!/bin/bash 
for (( i=1; i<=5; i++)) 
do 
	 If [ $1 -eq 3 ]
	 then
		 continue
		fi	 
	echo "Number: $i"
done
echo "the file no longer exist"

this skips echo number3 and then continue the loop
