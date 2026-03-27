##bandit level 9-10

###Objective
Retrieve the password for the next level which is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.


###Approach
-Listed the files using ls
-Used strings to extract human-readable sequences from data.txt 
-Filtered the output using grep to locate lines containing multiple = characters
-Identified the line containing the password
-Used the password to gain access to the next level

###Commands used
-ls
-strings data.txt | grep "==="
-ssh bandit10@bandit.labs.overthewire.org -p 2220

###Key concepts learned
-strings extracts printable text from binary or noisy files
-grep filters output based on patterns

