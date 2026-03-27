##Bandit level 7-8


###Objective 
Retrieve the password stored in the file data.txt next to the word millionth and use it to log into the next level 


###Approach
-Listed the files in the home directory using ls
-identified the file data.txt
-used grep to search for the keyword millionth within the file
-Extracted the password from the matching line
-Used the pasword to gain acces to the next level 

###Commands used
-ls
-grep "millionth" data.txt
-ssh bandit8@bandit.labs.overthewire.org -p 2220


###key concepts learned
-grep is used to search for specific patterns within files
-Command-line tools are more efficient than manual inspection for large files 
