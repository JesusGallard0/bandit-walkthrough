##Bandit Level 15-16


###Objective
Retrieve the password for the next level which can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL/TLS encryption


###Approach
-Verified that port 30001 was open on localhost using nmap 
-Established a secure connection using openssl s_client
-Submitted the current level's password through the encrypted channel
-Received the password for the next level as a response from the service
-Used the password to authenticate as bandit16

###Commands used
-nmap -p 30001 127.0.0.1
-openssl s_client -connect localhost:30001 
-# (manually pasted the current level password)
-ssh bandit16@bandit.labs.overthewire.org -p 2220

###Key concepts learned

-SSL/TLS encrypts data in transit,preventing it from being read in plaintext

-openssl s_client allows direct interaction with SSL/TLS services,similar to how nc interacts with plain TCP services
-By default,nmap scans the 1000 most common ports.Using -p allows targeting a specific port directly

