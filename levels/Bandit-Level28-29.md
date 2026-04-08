## Bandit level28-29




### Objective
-Clone a git repository and retrieve the password for bandit29 inside the repository


### Approach
-Created a directory to store the repository for this level
-Cloned the repository inside the directory
-Navigating in the repository,located a README.md file containing credentials ,a placeholder instead of a real password 
-Revealed old commits using git log
-And looked on each one using git show and the hashes to find the password before it was censored
-Found the commit containing the password in plain text 
-Used the password to authenticate as bandit29



### Commands used
    mkdir gitbandit
    cd gitbandit
    git clone  ssh://bandit28-git@bandit.labs.overthewire.org:2220/home/bandit28-git/repo
    cd repo
    ls
    cat README.md
    git log
    git show adc7f885a129baee883058b8a870739489f80194:README.md
    git show a3437bddd447f2d496731658e86b98cbea9d3c98:README.md
    

    ssh bandit29@bandit.labs.overthewire.org -p 2220


### Key concepts learned 

-Git history is persistent ,even if a file is modified previous versions remain accessible in commit hisory 
-Avoid sensitive data exposure in repositories
-Git inspection techniques
    -git log (view commit history)
    -git show (inspect specific commits)
    -git diff(compare changes)

