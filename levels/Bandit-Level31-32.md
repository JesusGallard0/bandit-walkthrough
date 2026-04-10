### Bandit level 31-32



### Objective
From your local machine, clone the repository and find the password for the next level.


### Approach
-Created a local directory to store the repository
-Cloned the repository via SSh inside my directory
-Navigated into the repository and located a README.md file that contained instructions:
    -Create a file:
    -name:key.txt
    -content:'May I come in?'
    -Branch:master
-Created the file following the required content
-Added and commited the file locally
-Attempted to push to the remote master branch
-The push was rejected by the server but the rejection message contained the password in plain text
-Used the retrieved password to authenticate as bandit32 in the next level


### Commands used
    mkdir bandit30git
    cd bandit30git
    git clone  ssh://bandit31-git@bandit.labs.overthewire.org:2220/home/bandit31-git/repo
    cd repo
    ls
    cat README.md
    nvim key.txt
        -#Write in the file
        -May I come in?
    git add key.txt
    git commit -m "May I come in?"
    git push origin master
         
         #Password retrieved from server response

         ssh bandit32@bandit.labs.overthewire.org -p 2220

### Key concepts learned
-A git push sends commits to a remote repository but the server can validate or reject them before accepting
-Git servers can use hooks to inspect incoming changes,in this level a hook intercepted the push and returned the password in the response
-Even when an action is rejected server responses may leak sensitive information 
