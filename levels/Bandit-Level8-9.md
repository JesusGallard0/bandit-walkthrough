##Bandit level 8-9

###Objective
Retrieve the password stored in the file data.txt which is the only line of text that occurs only once,and using it to gain acces to the next level

###Approach
-Listed files using ls
-Identified the file data.txt
-Sorted the file contents to group identical lines together
-Used uniq -u to extract the line that appears only once
-Used the resulting line as the password to authenticate into the next level

###Commands used
-ls
-sort data.txt | uniq -u
-ssh bandit9@bandit.labs.overthewire.org -p 2220

###Key concepts learned
-sort organizes lines so identical entries become adjacent
-uniq operates on consecutive duplicate lines
-uniq -u outputs only lines that appear exactly once
-pipelines (|) allow combining tools to perform complex operations efficiently 

