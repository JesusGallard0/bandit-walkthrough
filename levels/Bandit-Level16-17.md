##Bandit level 16-17


###Objective
Retrieve the credentials for the next level by submitting the password of the current level to a port on localhost in the range 31000 to 32000.

###Approach
-Scanned the port range 31000-32000 on localhost using nmap and used the ssl-cert script to detect which ports were runing SSL/TLS enabled
-Identified two candidate ports that supported encrypted communication
-Determined the correct service based on its response,which returned an SSH private key
-Saved the private key locally and restricted its permissions using chmod 600
-Used the file as a private key to authenticate in bandit17


###Commands used
-nmap -p 31000-32000 --script ssl-cert  127.0.0.1
- openssl s_client -connect localhost:31518 
- # (manually submitted the password)
-  openssl s_client -connect localhost:31790
- # (manually submitted the password)
-#On local machine
    -nvim key.txt
    -# (pasted and saved the private key)
    -chmod 600 key.txt
    -ssh -i key.txt bandit17@bandit.labs.overthewire.org -p 2220



###Key concepts learned
-the ssl-cert script helps identify services that support SSL/TLS
-A BEGIN RSA PRIVATE KEY block represents a private key used for SSH authentication
-nmap ability to scan a specific range of ports 


