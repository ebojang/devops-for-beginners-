Linux benefits 
* **open source nature** - this aids users to modify, distribute and even sell modifications to the OS under their own term 
* **cost effectiveness** - most Linux distributions are free download and use 
* **security** - permission and user features alongside regular updates help keep system secure from malware and vulnerabilities. 
* customizability 
* reliability 
**
==**POPULAR LINUX COMMANDS== 
Linux file system directories 
**Ls  (list directory) - view the content of a directory 
ls -l shows a detailed list of files in a long format
ls -R list directories recursively. eg devops/cloud/support
devops:
cloud
./cloud:
support

**lso**f : lists on its standard output file information about files opened  by  processes

 **==CD COMMAND==** 
 
**Cd (change directory)**-  navigate through the Linux files and directories 
- . (current directory). This is the directory you are currently in.
- .. (parent directory). Takes you to the directory above your current.
- ~ (home directory). This directory defaults to your “home directory”. Such as /home/pete.
- - (previous directory). This will take you to the previous directory you were just at.
**Cd ..** -  takes you one directory up  

**Pwd (print/ present working directory)** – shows your current working directory 
touch -  allows you to create new empty files.

**file** -filenames aren’t required to represent the contents of the file . to find out what kind of a file a file is . run 
$ file (filename)
**less.**  if you are viewing text files larger than a simple output, less is more.
$ less /home/pete/Documents/text1

**find command**
$ find /home -name puppies.jpg
find /home -type d -name MyFolder
You can see that I set the type of file I’m trying to find as (d) for directory and

==**MKDIR COMMAND**== 

**Mkdir** (**make a new directory**)-  Mkdir Hello- make a folder or directory call Hello . Directory are mostly highlighted due to our customization of myzsh. also when you click on **ls -l**  directory will have the following **drwx**

==**to name folders or directory with space name run the following**== 
mkdir "folder name "  example mkdir "my dev folder" 
or mkdir my\ dev\ folder and then enter 
to view directory content with space name : **cat "my dev folder"**

==**mkdir -p**== (parent flag) i**s used to create nested directory eg ***mkdir -p Directory/ subdirectory/sub-subdirectory***
**==ls -R Directory==** - list directory recursively 
**Rmdir** – remove empty directory a. Eg rmdir Hello – remove directory called “Hello” 

**==rmdir -r==** is used to remove directory that contain folders or files or that have content in them 
**Touch**- is used to create an empty file. EG touch hello.txt   - a file name hello.txt has been created . it can also be used to update the time stamp of the existing file  :

**==CP== ==COMMAND==** 

**Cp** **(copy)** - is used to copy files from the current directory to a different directory  or copy a file 
CP option source destination 
example cp test1.txt test1_copy.txt

**To copy a directory that contains folders to another directory, run the below command 
cp -r (directory name ) (new directory_copy)**

If a file already exist in a directory and you try to copy the same directory, run 
cp -I (Flag I stands for interactive)
this will ask for confirmation before overwriting 

==**MV COMMAND IN LINUX**== 

**mv (move)** command is used to **move or** **rename files in the directory**. eg mv test1.txt mydirectory
this moves the txt files to the required directory
move a file to a different directory: $ mv file2 /home/pete/Documents or 
more than one file :
$ mv file_1 file_2 /somedirectory
==mv -r== : is used to move directory .(**-r is a recursive**)

==**TO REMOVE DIRECTORY**== 
rm -f (force)- remove all files
**rm -r** (directory name)
if access denied run. **sudo rm -r (directory name)vim**
 rm -i (interactive)

rm (remove) is used to remove files from the directory 
**Locate**: this cmd is used to locate a file, just like the search command  in windows 
**Ctrl l** – clears your command line interface
**echo "Godfather of Harlem" > welcome.txt**
echo "welcome1999 >> welcome.txt "
the symbol **>>** Adds a content on the file 
a single **>** overwrites the content 

**==CAT COMMAND==** 

**cat command- it has 3 functions 
echoing eg cat enter. test. this will echo test. to come of the txt press ctrl d 
2) cat command can be used to display content of two files . eg cat text1.txt text2.txt
3) **cat command can also be used to combine content of two files . eg cat text1.txt text2.txt > combined.txt 
to read a directory call -
enter cat ./-

standard in in command (stdin:
$ cat <oeanut.txt > banan.txt
**==Vim==**- use vim command to insert text. once completed press esc  **: wq (write and quit)** to save text and exit 
 whilst in command mode in vim. to move to the **beginning** of a line, **press zero (0)**
 to move to the **end** of a line press *
 to move **forward** by word, press **w**
 to move **backwards** by word press **b**
 to move to specific line press : followed by specific number **eg :5 enter** 
 to search for a specific word in a log i vim 
 in vim to delete a whole line press **dd
 to delete from a specific word to the end of the line, move cursor to the word and press D 
 TO COPY LINE - press yy
 to paste press p
 *to undo last change press u 
 ctrl r -redo the change 
 

==head== command - gives you the 10 lines by default 
==tail== command- shows the last 10 lines by default. tail text1.txt 
to view first 5 line use the following command: ~head -n 5 text1.txt
you can use head and tail command : head -n10 text1.txt  | tail -n 5

**head and tail command is used to view the beginning and end of a file** 
**PIPING (|)** piping is use to sending data from one program to another. what this does is it feeds the output from the program on the left as an input to nthe program on the right. 

You may combine pipes and redirection too.
example: head -n10 text1.txt  | tail -n 5 > output.txt 
**env (Environment)**
run env to vie environment variable 
One particularly important variable is the PATH Variable. 

**cut command**
cur command extracts portions of text from a file.
example 
$ echo 'The quick brown; fox jumps over the lazy  dog' > sample.txt
$ cut -c 5 sample.txt
This outputs the 5th character in each line of the file. In this case it is "q", note that the space also counts as a character.


**sudo !!** - means you are trying to run a previous command 

==**SETTING ZSH TO BE DEFAULT SHELL== 
**Developers uses ZSH to customise the shell they are using. 
CMD 
~% sudo  chsh -s /bin/zsh
==sudo== 
password:
:~$ zsh
echo $SHELL
/bin/zsh
restart or update sessions once zsh os installed 

==INSTALL OHMYZSH== 

RUN 
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"



==**THE SUDO COMMAND== 

Sudo (super user do)- it  allows permitted user to execute command as a super user or administrative privilege 
sudo command can only be run by a root user or a user with an elevated permission
==sudo command is required when creating users and groups== 
**
**ROOT USER PLUS A DANGEROUS COMMAND** 
to run as root user, enter 
sudo su
followed by whoami
root username conatins# at the end
eg root@ebrima:/home/ebojang#
this gives you an unrestricted access to the entire system.

rm -rf / - this removes everything in the root file system.
rm is remove -r (recursive) f (force) / (root directory)
**rm -rf /** 
when you run the this command this can break the actual root system 

==**TO CREATE NEW USER?**==
sudo useradd (new username)
sudo passwd (new username)
New Password: (enter the password for the new user)

**SWITCH NEW USER ON THE TERMINAL, ENTER BELOW COMMAND**
~**su (substitute user)** eg su - (new username)
this will prompt you to enter the new user password 
enter whoami to verify you are now the new user

NOTE: That the new user/account will not have SUDO privileges 

**TO GRANT NEW USER A SUDO PRIVILEGE OR ACCESS:**
exit and on the root user profile enter the following 
*~sudo usermod -aG sudo (new username)*

**TO REMOVE SUDO ACCESS FROM A USER , RUN THE FOLLOWING** 
exit from new user and run
**sudo deluser (newusername) sudo**

TO CREATE NEW GROUP 
First check list of group names by entering 
cat /etc/group

**to add new group run** 
sudo groupadd (groupname)
to verify group name has been created run
cat /etc/group

**TO ADD USER TO GROUP** 
~sudo usermod -aG (groupname) (username)

to confirm user has been added to the group, login as the new user 
su - (username)
~groups
the username will appear alongside the group they are a member of 

**TO REMOVE USER FROM A GROUP :**
sudo gpasswd -d (username) (groupname)

**TO DELETE GROUP** 
sudo groupdel (groupname)
to confirm group has been deleted run:
grep (groupname) /etc/group
or etc/group 

**==INTRODUCTION TO FILE PERMISSIONS==**
r- read w- write x- you can run the file as a programme
![[Pasted image 20250531172850.png]]
![[Pasted image 20250531171227.png]]

**==HOW TO MODIFY PERMISSION==** 
**TO GRANT USER EXECUTE PERMISSION ON A FILE :**
~chmod u+x (user+execute), group+r (group+read), o-w (remove w permission from others) filename 
example chmod u+x,g+r,o-w welcome.txt

**numerical representation**
read=4, write=2, execute=1(7)
group read= 4
other no perm=0
if user have rwe permission, this will be, group have read permission+ execute and other have no permission
**run the below command** 
~chmod 750 test.txt

**Grouping permissions using symbolic operators:**
~ chmod users and groups=rw others=r 
~ chmid ug+rw,o=r test.txt

**Changing file/Dir ownership for user/Group:**
~chown = is to change owner of file or directory 
run: sudo chown (accountname) (filename)
~chgrp= is to change group owner 
sudo chgrp (groupname) (filename)

**Alternatively, you can change both user and group owner in one command** 
~ sudo chown (user):(group) (filename)
~ sudo chown testaccount:admin2 test.txt

**HOW TO CHANGE OWNERSHIP OF A DIRECTORY?**
sudo chown (username):(groupname) "directory name)"
ls - l to check the owner and group 


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









