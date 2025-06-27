
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
source ~/.zshrc


