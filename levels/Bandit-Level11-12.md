##Bandit level 11-12


###Objective
Retrieve the password for the next level which is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

###Approach
-Listed files to locate the file data.txt
-Identified the data transformation as ROT13 cipher
-Applied the character substitution using "tr":
    --tr 'A-Za-z' 'N-ZA-Mn-za-m' < data.txt
-Extracted the password in the encoded output
-Used the password to gain acces in the next level

###Commands used
-ls
-tr 'A-Za-z' 'N-ZA-Mn-za-m' < data.txt
-ssh bandit12@bandit.labs.overthewire.org -p 2220

###Key Concepts learned
-ROT13 cipher is a simple letter substitution cipher that shifts characters by 13 positions
-tr performs character-by-character substitution based on defined mappings

