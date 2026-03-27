##Bandit Level 0


###Objective
Acces the bandit server via ssh

###Given
-Host: bandit.labs.overthewire.org
-Port: 2220
-Username: bandit0

###Solution
Used ssh to establish a remote shell:

ssh bandit0@bandit.labs.overthewire.org -p 2220

###Key concepts
-SSH allows secure remote login over a network
-Default port is 22 but here it is 2220 
-Syntax this time ssh user@host -p port

###What i learned
-How to construct an SSH command from given parameters
-How remote authentication works



