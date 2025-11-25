
How to Check for a Human-Readable File in the Inhere Directory?
run: file inhere/*

**Find a human readable file, file size and file not executable?**
Answer: find . -type f -size 1033c ! -executable -exec file {} + | grep -w text
-type f : only match regular files 
-size 1033c - match files whose size is exactly 1033c. the c suffix means bytes.
! - executable - this excludes files that are executable