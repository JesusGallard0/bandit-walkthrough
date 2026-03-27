##Bandit level 3


###Objective
Retrieve the password stored in a hidden file inside a directory named inhere and use it to log into bandit4


###Approach
-Listed the elements with ls
-i got into the inhere directory
-i used ls -a to reveal hidden files(dotfiles)
-Located a file named ...Hiding-From-You
-I read the file using cat ...Hiding-From-You
-I used the password to gain acces to the next bandit via SSH

###Commands used
-ls
-cd inhere
-ls -a
-cat ...Hiding-From-You
-exit
-ssh bandit4@bandit.labs.overthewire.org -p 2220

###Concepts learned

-Files can be hidden in Linux if they start with "."
-Standart ls does not display hidden files
-ls -a can list files even if there are hidden


