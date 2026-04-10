## Bandit level 29-30



### Objective
-Clone a repository  via SSH and locate the password stored within it 


### Approach
-Created a local directory to store the repository
-Cloned the repository using the provided endpoint 
-Inspected the repository contents and found a README.md file that said stating: "no passwords in production" so,maybe in another branch
-Listed all branches using git branch -a  
-Checked out the dev branch (remotes/origin/dev
-Located a README.md file containing the password and i retrieved it
-Used the retrieved password to authenticate as bandit30 in the next level

### Commands used 
    mkdir ban29git
    cd ban29git
    git clone ssh://bandit29-git@bandit.labs.overthewire.org:2220/home/bandit29-git/repo
    cd repo
    ls
    cat README.md
    git branch -a
    git checkout remotes/origin/dev
    ls 
    cat README.md


    ssh bandit30@bandit.labs.overthewire.org -p 2220



### Key concepts learned

- Remote branches can contain different versions of files,including sensitive information not present in main branch
- Storing sensitive data in any branch is insecure,all branches are accessible once the repository is cloned
-git branch -a lists all local and remote branches
-git checkout switches to a specified branch



