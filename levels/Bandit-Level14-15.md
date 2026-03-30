##Bandit Level 14-15



###Objective
Retrieve the password for the next level by submitting the password of the current level to port 30000 on localhost.

###Approach
-Verified that port 30000 was open on localhost
-Established a TCP connection to the port using nc(Netcat)
-Sent the current level password through the connection
-Recieved the password for the next level as a response from the service
-Used the retrieved password to authenticate into bandit15


###Commands used
nmap 127.0.0.1
nc localhost 30000
#(manually pasted the current level password)
ssh bandit15@bandit.labs.overthewire.org -p 2220

###Key concepts learned
-nmap is used to identify open ports and infer running services via fingerprinting techniques.Results are heuristec and may not always be exact
-Tools like nc allow direct interaction with TCP services:
    -You connect as a client
    -Send input
    -Recieve output from the server
-Some services are designed to return specific outputs when given correct input




