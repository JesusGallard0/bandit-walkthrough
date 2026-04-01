##Bandit level 19-20


###Objective
Retrieve the password for the next level using a setuid binary provided in thehome directory.The password is stored in /etc/bandit_pass/bandit20,but is only accesible via elevated execution privilages


###Approach
-Inspected the home directory and identified the exectable bandit20-do

-Checked file permissions using ls -l to confirm it was a setuid binary 
-Executed the binary to run commands with the privileges of the bandit20 user
-Used it to read the restricted  file and extracted the password 
-Used the password to authenticate as bandit20


###Commands used
-ls -l 
- ./bandit20-do  cat  /etc/bandit_pass/bandit20
-ssh bandit20@bandit.labs.overthewire.org -p 2220


###Key concepts learned
-SetUID allows a binary to execute with the permissions of its owner
-Misconfigured setuid binaries can lead to privilege escalation


