##Overthewire bandit 0-1

###Objective
Locate the password stored in a file named readme in the home directory and use it to log into bandit1 via SSH
###Aproach
-Listed files in the home directory using ls
-Identified a file named readme
-Read its content to obtain the password
-Used the password to authenticate the next level


###Commands used 
-ls 
-cat readme 
-exit 
-ssh bandit1@bandit.labs.overthewire.org -p 2220 

###Key concepts learned
-Basic file enumeration in linux (ls)
-Reading file contents (cat)
-Managing SSH sessions(exiting current session before switching users)
-
-
