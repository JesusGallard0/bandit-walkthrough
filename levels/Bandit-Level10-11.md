##Bandit level 10-11


###Objective
Retrieve password for the next level, stored in the file data.txt, which contains base64 encoded data

###Approach
-Listed files to identify the file
-Observed that the file content contains base64-encoded data
-Decoded the content using
   -base64 -d data.txt
-Extracted the password from the decoded output
-Used the password to gain acces in the next level

###Commands used
-ls
-base64 -d data.txt
-ssh bandit11@bandit.labs.overthewire.org -p 2220


###Key concepts learned
-Base64 is an ecoding scheme,not encryption
-Use base64 -d to decode encoded data into readable plaintext
-Encoded data is often used to safely transmit or store binary/text data
