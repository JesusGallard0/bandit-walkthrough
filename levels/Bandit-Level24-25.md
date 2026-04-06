##Bandit level 24-25



###Objective
Retrieve the password for the next level by authenticating against a service running on port 30002 using

    -Bandit24 password

    -Brute-force attack against a 4-digit PIN


###Approach
-Navigated to the /tmp directory 

-Discovered an existing directory (bruteforce) containing a file with PIN combinations

-Used netcat to send all combinations to the target service

-Upon successful authentication,the service returned the password for bandit25

-Used the extracted password to authenticate in the next level 



###Commands used 

cd /tmp

cd bruteforce

cat combinations.txt

cat combinations.txt | nc localhost 30002

ssh bandit25@bandit.labs.overthewire.org -p 2220



###Key concepts learned
 
-Bruteforce is effective here due to: 

    -Small search space (10000 combinations)

    -No rate limiting or lockout

    -its feasibility depends on the size of the keyspace


