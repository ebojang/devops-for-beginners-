
Place custome script in a directory 
mkdir my_scripts

create a scripts and place it in my_scripts directory 
firstscript.sh >> My_scripts  or 
vim myscripts/firstscript.sh

#!/bin/bash
echo "hello world"
chmod +X firstscript.sh


NOTE 
Changes to PATH made in the terminal are temporary and lost when the session ends. 

**TO MAKE IT PERMANENT, add PATH to zshrc file** 
echo "export PATH=$PATH:~/My_scripts" >> ~/.zshrc
 RELOAD ZSHRC FILE FOR CHANGES TO TAKE EFFECT:
 RUN:
 source ~/.zshrc
 now script should be accessible anywhere 


**ENVIRONMENT VARIABLES** 

Environment variables are variables that are set in the environment and affects the  behaviour of processes on the system. They store configuration settings.
$PATH environment variable tells the system where to look for executed files. 
echo $PATH

**TO VIEW CURRENT ENVIRONMENT VARIABLE, RUN**
~ printenv or env

**SETTING TEMPORARY ENVIRONEMT VARIABLE** 

export MY_VAR="hello world"
echo $MY_VAR 

vim .zshrc
source .zshrc

to check shell run 
cat /etc/shells

environment variables can also be assigned to local variables within our script, making them easier to reference them later.

STANDARD ENVIRONMENT VARIABLES 
Provide valuable information about the system,user and runtime environment
#!/bin/bash

echo "username: $LOGNAME"
