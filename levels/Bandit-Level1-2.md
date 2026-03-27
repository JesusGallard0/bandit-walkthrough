##Bandit Level 2

###Objective
Retrieve stored in  the file named - in the home directory and use it to log into bandit2 via SSH

###Approach
1.Listed files in the home directory using ls
2.identified a file named -
3.Accessed the file using ./- to avoid ambiguity with standart input
4.Read the file contents to obtain the password 
5.used the password to log into bandit2 via SSH

###Commands used
-ls
-cat ./-
-ssh bandit2@bandit.labs.overthewire.org -p 2220


###key concepts learned
-Files named - can conflict with standart input/output conventions in Linux
-Using ./ explicity defines the file path and avoids misinterpretation
-Trying to open - directly will cause the command to wait for input instead of reading the file

