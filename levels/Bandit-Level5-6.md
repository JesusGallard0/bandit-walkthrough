##Bandit level 5-6


###Objective 
Retrieve the password stored somewhere under the inhere directory.The file must meet the following conditions:
-human readable
-1033 bytes in size 
-not executable 
Use it to log into bandit6

###Approach
-List everything with ls
-Navigated into the inhere directory
-listed all the files
-Used find . -type f -size 1033c filtering by file type and size 
-Located the matching file stored in maybehere07/.file2 
-Read its content to obtain the password
-Used the password to authenticate into the next level

###Commands used

-ls
-cd inhere
-ls 
-find . -type f -size 1033c
-cd maybehere07
- cat .file2
-ssh bandit6@bandit.labs.overthewire.org -p 2220

###Key concepts learned
-find enables recursive search with multiple constraints
-Combing filters improves efficiency and accuracy during enumeration

