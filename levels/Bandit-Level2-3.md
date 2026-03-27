##Bandit Level 3


###Objective

-Retrieve the password stored in a file named --spaces in this filename-- located in the home directory and use it to log into bandit3

###Approach
-Listed the files using ls 
-Identified the file
-I read the file usign cat "./--spaces in this filename--" using quotes to treat the filename as a single argument
-Read the file content to obtain the password
-Used the password to authenticate into the next level

###Commands used
-ls
-cat "./--spaces in this filename--"
-exit
-ssh bandit3@bandit.labs.overthewire.org -p 2220

###Key concepts learned
-The linux shell splits arguments by spaces by default
-Filenames with spaces must be handled explicitly
-Quotes(" ") allow the shell to interpret the full filename as a single argument
-Alternatively,spaces can be scaped using\
