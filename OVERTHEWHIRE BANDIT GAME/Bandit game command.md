

OVER THE WIRE BANDIT GAME 
bandit.labs.overthewire.org,

Bandit Level0 -> 1
login: SSH bandit0@bandit.labs.overthewire.org -p2220
Password: bandit0
The password for the next level is stored in a file called readme located in the home directory.
ls 
run: cat readme
Password: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If

Bandit Level1 -> 2
SSH bandit1@bandit.labs.overthewire.org -p2220
The password for the next level is stored in a file called - located in the home directory
run: cat <- or cat ./-
password:263JGJPfgU6LtdEvgfWU1XP5yac29mFx

Bandit Level2 -> 3
The password for the next level is stored in a file called --spaces in this filename-- located in the home directory
cat ./"--spaces in this filename--" or run cat -- --spaces\ in\ this\ filename--
password:MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx

Bandit Level3 -> 4
Bandit level 3 -> 4
The password for the next level is stored in a hidden file in the inhere directory.
cat ./...Hiding-From-You
password: 2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ

Bandit 4 -> 5
The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.
file inhere/*
cat inhere/-file07
Password: 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw

Bandit 5 -> 6
he password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:
human-readable
1033 bytes in size
not executable
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG

Bandit Level 6 -> 7

The password for the next level is stored **somewhere on the server** and has all of the following properties:

- owned by user bandit7
- owned by group bandit6
- 33 bytes in size
 find / -user bandit7 -group bandit6 -size 33c
























stage 5-6
to find a file using size 
find . -type f -size 1033c

(find .) looks for all the files and directories with the dot meaning starting from the current dir
stage 6-7
to find password on the server and owner name is bandit 7 group name bandit 6 size 33
run the below command 
find / -type f -user (usernsme) -group (groupname) -size33 (c represents bytes) **`2>/dev/null`**

-Note:  `2>/dev/null` → Suppresses permission errors from directories you can't access
run cat command filename to access content 

The password for the next level is stored in the file **data.txt** next to the word **millionth**
run command: grep millionth data.txt

when you use grep -l "word" filename - it searches for the name word in the file. it becomes case insensitive .

LEVEL 8-9 
The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once

## Commands you may need to solve this level

grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd



