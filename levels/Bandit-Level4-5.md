##Bandit level 4


###Objecetive
-Find the only human-readable file among multiple files in the inhere directory  ,retrieve the password and use it to log into bandit5

###Approach
-Listed all files using ls
-Navigated into the inhere directory
-Used file ./* to determinate the type of each file
-Identified the file containing ASCII text 
-Read the contents of that file to obtain the password cat ./-File07
-I used the password to gain acces to the next level

###Commands used
-ls
-cd inhere
-file ./*
-cat ./-File07
-ssh bandit5@bandit.labs.overthewire.org -p 2220


###Key concepts learned
-The file command is used to determinate the type of a file 
-Attempting to open every file manually instead of using file leads to inefficient enumeration and poor methodology
-File allows to attackers to quickly identify valuable data (credentials,configs)
