## Bandit level 27-28


### Objective
-Cone a git repository over SSH and retrieve the password for bandit28

### Approach
-Created a local directory to store the repository
-Cloned the repository via SSH using the correct port
-Navigated into the repo directory and found a README file containing the password 
-Retrieve the password reading the file
-Used the password to authenticate as bandit28 in the next level

### Commands used

    mkdir banditgit
    cd banditgit
    git clone ssh://bandit27-git@bandit.labs.overthewire.org:2220/home/bandit27-git/repo 
    cd repo 
    ls
    cat README

    
    ssh bandit28@bandit.labs.overthewire.org -p 2220


### Key concepts learned 

-Git repositories can be hosted on remote servers and accessed via SSH
    -No need for plataforms like GitHub
    -Direct cloning from a server is possible

