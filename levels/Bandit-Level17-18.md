##Bandit level 17-18


###Objective
Retrieve the password which can be in one of the 2 files in the homedirectory: passwords.old and passwords.new. The password for the next level is in passwords.new and is the only line that has been changed between passwords.old and passwords.new

###Approach
-Listed the files in the home directory using ls
-Compared both files using diff utility to identify differences
-Filtered the output to extract only the present in passwords.new
-Used the extracted password to authenticate in the next level

###Commands used
-ls
-diff passwords.old passwords.new|grep ">" | cut -c3-
-ssh bandit18@bandit.labs.overthewire.org -p 2220

###Key concepts learned
-diff command compares two files line by line and highlights differences

