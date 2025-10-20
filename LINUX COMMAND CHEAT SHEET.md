FILE OPERATIONS 
**Ls  (list directory) - view the content of a directory 
ls -l shows a detailed list of files in a long format
ls -a list all files + hidden files 
ls -R list directories recursively. eg devops/cloud/support
devops:
cloud
./cloud:
support

**note**:
- `-` one dash informs the system that we will pass one letter argument, like 'l'
- `--` two dashes means that argument will contain more than one letter. Most commonly it will be an English word.

**lso**f : lists on its standard output file information about files opened  by  processes

SORTING FILES 
sort files by time
ls -lt   sorts files with the last modification time, newest files come first.
ls -ltc  sorts files with c-time metadata change i.e content altered  

sort content by size
ls -s - short list of files and allocated space.
`ls -lS` it sorts files by size, largest are going first.

HUMAN READABLE FILE
 This argument is `--human-readable` or -h
 ls -lh  list directory contents with human-readable file sizes.
ls -lSh list directory contents with himan-readable file sizes, largest one on top.

file format
`ls --format=commas` will print the files separated by commas.
