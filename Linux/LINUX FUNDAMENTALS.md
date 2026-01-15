Linux benefits 
* **open source nature** - this aids users to modify, distribute and even sell modifications to the OS under their own term 
* **cost effectiveness** - most Linux distributions are free download and use 
* **security** - permission and user features alongside regular updates help keep system secure from malware and vulnerabilities. 
* customizability 
* reliability 

Working with the linux shell
symbol to represent home directory? tilda (~)
user home directory by default is represented as : /home

Command types 
* internal or Built-in commands -echo, cd pwd, set e.t.c
* External commands : are binary programmes or scripts which are usually located in a distinct file in a system.mv, date, uptime, cp, uptime e.t.c 

To determine if a command is internal or external use ==type== command :
example: type echo, type mv, type date 

Basic Linux Commands:

==**POPULAR LINUX COMMANDS== 
Linux file system directories 
**
devops:
cloud
./cloud:
support

**lso**f : lists on its standard output file information about files opened  by  processes

**note**:
- `-` one dash informs the system that we will pass one letter argument, like 'l'
- `--` two dashes means that argument will contain more than one letter. Most commonly it will be an english word.

**FILE TYPES IN LINUX** 
1) Regular files : images, scripts, configurstoion /data files
2) Directory: type of file that store other files within . eg home directory
3) special files: hav e sub file types
* character files: 
* block files: represent block devices .these are located under /dev 
* links 
* socket: enables communication between two processes 
* named pipes

HOW TO IDENTIFY FILE TYPE IN LINUX
$ file /home/ebrima or $ file (filename)


==Filesystem Hierarchy in Linux;==
* /opt : is the path where all 3rd programmes are installed
* /mnt : is used to mount filesystem temporarily 
* /tmp ; is used to store temporary data
* /media : all external media is mounted on /media . example usb disk
* /etc : stores most of configuration files in linux 
* /var : is where logs can be found 

==LINUX BOOT PROCESS== 
1) BIOS POST
2) Boot Loader 
3) kernel initialisation
4) Init process (systemd): brings linux host to a usable state.


 **what is the init process used by this system?**
 $ sudo ls -l /sbin/init 
result: lrwxrwxrwx 1 root root 22 Jun  4  2025 /sbin/init -> ../lib/systemd/systemd

**Viewing file sizes in Linux**
run du command. disk usage is a command used to inspect size of a file. 
1) $ du -sk (filename) : shows the size of the directory in kilo bytes
2) $ du  -sh test.txt : prints the size in human readable format
3) $ ls -lh test.txt 


**ARCHIVING FILES** 
tar -cf is the command use to archive data 
tar is abbreviation for tape archive 

$tar -c is used to create and archive 
$ tar -cf : is used to specify the name of the tar file  to be created (test.tar) followed by the name of the file or directories to be created.

==TO VIEW CONTENT OF ARCHIVE FILES:==
$ tar -tf (followed by the archive file or tar file) test.tar

 ==to EXTRACT ARCHIVE FILE:==
 **$tar -xf** (archive file name) test.tar
 
 **to compress file: to reduce size** 
 $ tar -zcf
run following commands to compress 
$ bzip2 test.img
$ gzip test.img
xz test.img 

TO UNCOMPRESS or extract 
$bunzip2 test.img
$gunzip test.img
$ unxz test.img 
$ du -sh test.img.bz2

**SEARCHING FOR FILES AND DIRECTORIES** 
==$ locate== (filename) example $ locate test.txt 
This will return all paths matching the pattern 

Alternatively, use the find command to search for a file
$ find (followed by the file path ) -name (filename) example 
$ find /home/ebrim -name test.txt 
use grep command 
grep (word ) (filename)
$ grep genius test.txt 
grep command is case sensitive 
use grep -i 
to search for a word or pattern recursively:
grep-r "genius" file path 

**redirect output** 
cat missing_file 2> /dev/null
error won't be printed out  
 




==**SORTING FILES== 
Ls  (list directory) - view the content of a directory 
ls -l shows a detailed list of files in a long format
ls -a: list all files including hidden
ls -R list directories recursively. eg devops/cloud/support
sorting files by time. Run ls -ltu or ltc
sort files by size:
ls -s or ls -lS
ls -lS - sort files by size , largest are going first
ls -lt : long list files in order created 
ls -ltr : long list files in the reverse order created
==**Argument human readable or better -h**== 
 This argument is `--human-readable` or -h
 ls -lh  list directory contents with human-readable file sizes.
ls -lSh list directory contents with human-readable file sizes, largest one on top.
ls -lSh or ls -lh

**
 **==CD COMMAND==** 
 
**Cd (change directory)**-  navigate through the Linux files and directories 
- . (current directory). This is the directory you are currently in.
- .. (parent directory). Takes you to the directory above your current.
- ~ (home directory). This directory defaults to your “home directory”. Such as /home/pete.
- - (previous directory). This will take you to the previous directory you were just at.
**Cd ..** -  takes you one directory up  
`cd parentdir/childdir023` .
- `cd ../../../var/log/nginx`
- `cd /var/log/nginx`
Protip:
Pushd /popd command : this command remembers current working directory before changing directory to the to the command specified in thecommand argument .
**Pwd (print/ present working directory)** – shows your current working directory 
touch -  allows you to create new empty files.

**file** -filenames aren’t required to represent the contents of the file . to find out what kind of a file a file is . run 
$ file (filename)
==**less.**==  if you are viewing text files larger than a simple output, less is more.
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

**create 10 directories, starting with `testdir1` to `testdir10`. How to do it in one command?**
*==mkdir tesdir{1..10}==*


==**mkdir -p**== (parent flag) i**s used to create nested directory eg ***mkdir -p Directory/ subdirectory/sub-subdirectory***
**==ls -R Directory==** - list directory recursively 
**Rmdir** – remove empty directory a. Eg rmdir Hello – remove directory called “Hello” 

**==rmdir -r==** is used to remove directory that contain folders or files or that have content in them 
**Touch**- is used to create an empty file. EG touch hello.txt   - a file name hello.txt has been created . it can also be used to update the time stamp of the existing file  :


**Absolute and Relative Path**
Absolute path: is a location of a file or directory starting from the root directory ~$ cd /home/ebrima/downloads


**tree command** 
It recursively shows the content of the directory. Recursively means if there is a subdirectory, its content will be shown as well.

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
**PIPING (|)** piping is use to sending data from one program to another. what this does is it feeds the output from the program on the left as an input to the program on the right. 

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
**==files involved in users configuration==**
**passwd **
located in most config files /etc/passwd
the structure 
'username:password:UID:GID:description:homedir:shell'
x in the password field means that password is encrypted and stored in another file


**ROOT USER PLUS A DANGEROUS COMMAND** 
to run as root user, enter 
sudo su
followed by whoami
root username conatins# at the end
eg root@ebrima:/home/ebojang#
this gives you an unrestricted access to the entire system.

run the command **id
this shows you UID, GID and other groups to which user belongs 

rm -rf / - this removes everything in the root file system.
rm is remove -r (recursive) f (force) / (root directory)
**rm -rf /** 
when you run the this command this can break the actual root system 

==**TO CREATE NEW USER?**==
sudo useradd (new username)
sudo passwd (new username)
New Password: (enter the password for the new user)

the command:
which useradd or which adduser shows you where the executable is located.
file 

**to change user password 
passwd (username)**

**SWITCH NEW USER ON THE TERMINAL, ENTER BELOW COMMAND**
~**su (substitute user)** eg su - (new username)
this will prompt you to enter the new user password 
enter whoami to verify you are now the new user

NOTE:
when su is executed without user: `su -` root is assumed and you need to give root password.
to quit the password prompt, press CTRL +c or try 3 times to login.



NOTE: That the new user/account will not have SUDO privileges 

**TO GRANT NEW USER A SUDO PRIVILEGE OR ACCESS:**
exit and on the root user profile enter the following 
*~sudo usermod -aG sudo (new username)*

**TO REMOVE SUDO ACCESS FROM A USER , RUN THE FOLLOWING** 
exit from new user and run
**sudo deluser (newusername) sudo**

**TO CREATE NEW GROUP** 
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
~ chmod ug+rw,o=r test.txt

**owner**: *- the owner of the object. It doesn't mean who created it, but who owns it at this moment.
- Group. Owner belongs to the group (of users). This inforation is here too. This means that our 'groupmates' have specific access to the file*
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


**some common commands** 


`grep`. This command search for given pattern in the output. Output may be the file or output from other command.

`grep 'case' .bashrc` This command will search for pattern `case` in a file `.bashrc`.

`wc` is a utility for counting words, newlines, bytes. Commonly we use it for counting lines.

When we execute

`wc -l .bashrc`

it will count how many lines (`-l` argument) are in our `.bashrc` file.

`sort` will sort the output in alphabetical order

****
==**note the command uniq always work best with sort**==
example 
cat numbers.txt | sort | uniq |wc -l

**to know what file type a file is. run** 
file (filename)


to kill process 


THE PS COMMAND 
Process status (ps)- with ps we can  only see these processes which are related to this session only.ps a
ps -a

ps aux shows the most important info, like PIC, status and resource usage

**==ALIAS==**
in order to create an alias we need to use the alis command. 
Example:
alias lh='ls alh'
ll is an alias as well 

**just typing the command alias , shows all defined aliases in the session.**

**to remove alias, run the following** 
unalias (followed by alias name or shortcut)
example: unalias lh

Make alias permanent
grep "alias" .bashrc
echo "alias lh='ls -alh'" >> .bashrc



UNDERSTANDING LOGS IN LINUX 

 By default, all logs are stored in `/var/log` directory (or filesystem), however, every system has different approach to files structure
cd /var/log

sys log- Contains all important information about the system and applications.
auth.log - Contains information about authorizations. All user login attempts (with information if successful or not), logout, password changes, remote logins and use of `sudo`.
kern.log - stores kernel messages 
last.log - contains information about last login




==LINUX PACKAGE MANAGEMENT INTRODUCTION==

**What is a package?**
A package is a compressed archive that contains all the file that are required by a particular software to run. 

==What are package managers?==
package managers are tools that automate the process of installing, updating , configuring and removing software packages.

==#RPM PACKAGE MANAGER==
is a package manger used in Red Hat Enterprise linux as well as other linux distributions.
The file extension for packages managed by RPM is .rpm

**RPM has 5 basic modes of operations:**
1) installing:  run the following command; rpm -ivh (package name) example rpm -ivh telnet.rpm
2) uninstalling: $ rpm -e telnet.rpm
3) upgrade: $ rmp -Uvh telnet.rpm
4) query; $ rpm -q telnet.rpm
5) veryfying: rpm -Vf <path to file>

to confirm how many software repositories are configures for yum package manger?
$ sudo yum repolist

DEBIAN-BASED PACKAGE MANAGERS 
1)  debian package (dpkg):
* install /upgrade: $ dpkg -i (package name) eg telnet.deb
* uinstalling $ dpkg -r telnet.deb
* list: $ dpkg -l telnet
* status: $dpkg -s telnet
* verifying: $dpkg -p <file path>*

2) Advanced Package Tool (apt)


SECURITY AND FILE PERMISSIONS IN LINUX 


