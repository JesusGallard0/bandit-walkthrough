## Bandit level 26-27


### Objecetive 
-Retrieve the password for bandit27 using the privileges available to bandit26


### Approach
-Listed files in the home directory to identify useful binaries
-Used the binary to read the password file in /etc/bandit_pass/bandit27
-Retrieved the password and used it to authenticate in bandit27



### Commands used
    
    ls
    ./bandit27-do cat /etc/bandit_pass/bandit27


    ssh bandit27@bandit.labs.overthewire.org -p 2220


### Key concepts learned


-Custom binaries can be configured to 
    -run with elevated privileges
    -Allow execution of commands as another user
