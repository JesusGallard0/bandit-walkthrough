## Bandit level 30-31



### Objective
From your local machine, clone the repository and find the password for the next level. 


### Approach
-Created a local directory in my machine to store the repository
-Cloned the repository via SSH
-Inspected the repository and found an empty README.md file
-Checked commit history and branches but found no useful information
-Considered other git objects that may store data,such as tags.Checked out tags using git tag
-Discovered a tag named secret  
-Used git show secret to inspect the tag which revealed the password
-Retrieved the password and used it to authenticate as bandit31 in the next level



### Commands used
    mkdir bandit30git
    cd bandit30git
    git clone  ssh://bandit30-git@bandit.labs.overthewire.org:2220/home/bandit30-git/repo
    cd repo
    ls
    cat README
    git branch -a
    git log --all --oneline
    git tag
    git show secret


    ssh bandit31@bandit.labs.overthewire.org -p 2220



### Key concepts learned

-Tags are references to specific commits,often used for marking releases
-Tags can contain metadata or annotated messages.Dont use them to store sensitive data
-Tags can be accessible to anyone who clones the repository

