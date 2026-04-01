##Bandit level 18-19


###Objective
Retrieve the password for the next level stored in a file readme in the homedirectory. Unfortunately, someone has modified .bashrc to log you out when you log in with SSH.


###Approach
-Attempted to SSH into the account normally,which triggered an automatic logout due to a malicious or modified .bashrc
-Bypassed the shell initialization by forcing a non-interactive shell at login
-Gained acces to a stable shell environment without executing .bashrc
-Located the readme file in the homedirectory
-Read the file using cat
-Used the extracted password to authenticate as bandit19




###Commands used
-ssh -p 2220 bandit18@bandit.labs.overthewire.org -t /bin/sh
-#(manually input the password)
-ls
-cat readme
-ssh bandit19@bandit.labs.overthewire.org -p 2220




###Key concepts learned
-.bashrc is executed during interactive shell sessions
    -it can be abused to disrupt login sessions
-Using ssh -t /bin/sh forces a minimal shell environment
    -This avoids execution of user-specific startup scripts

