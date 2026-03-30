##Bandit Level 13-14


###Objective
Retrieve the password for the next level, stored in /etc/bandit_pass/bandit14. Can only be read by user bandit14.

###Approach
-Listed files using ls
-Located the ssh private key
-Reviewed the HINT using cat to confirm that the key should be used for authentication
-Copied the private ssh key to the local machine using scp
-Adjusted file permissions to the ssh private key as required by SSH 
-Used the private key to authenticate as bandit14 via SSH
-Once authenticated,accessed the password file 
-Used the password to authenticate in the next level

###Commands used
ls
cat HINT
exit
scp -P 2220 bandit13@bandit.labs.overthewire.org:sshkey.private .
chmod 600 sshkey.private
 ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220
 cat /etc/bandit_pass/bandit14
 ssh bandit15@bandit.labs.overthewire.org -p 2220

###Key concepts learned
-A private key can be used instead of a password to authenticate to an SSH server
-SSH requires strict permissions on private keys
-scp is used to copy files between remote and local systems over SSH

