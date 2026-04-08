##bandit level 25-26



###objective
log into bandit26 using a privatekey found in bandit25.
The shell for bandit26 is not /bin/bash, but something else. find out what it is, how it works and how to break out of it.

###approach
-Listed files in bandit25's home directory and ideftified the SSH key

-Used scp to copy the key to the local machine and set chmod 600 to the SSHkey

-Checked /etc/passwd to determine which shell is being used by bandit26

-Found /usr/bin/showtext.This indicates a custom shell,likely a wrapper around a text viewer

-Upon login: a large text is displayed and the connection immediately closes 

-The shell runs a program that displays text and exits,likely uses a pager such as "more"

-Pagers like "more" become interactive only if the output exceeds terminal size,so,i reduced the terminal height to prevent full rendering and forcer a TTY allocation with SSH

-Inside "More" i used v to open vim 

-used vim's shell escape :set shell =/bin/bash and initiated the shell :shell 

-Once there retrieve the password from the file with the bandit26 password

-used the password to authenticate in the next level


###commands used 
-ls
-another terminal:
    -scp -p 2220 bandit25@bandit.labs.overthewire,org:bandit26.sshkey .
    -chmod 600 bandit26.sshkey
    -#used a shorter terminal
    -ssh -t -i bandit26.sshkey bandit26@bandit.labs.overthewire.org -p 2220
    
    -#inside more 
        -v
        -#Inside vim

            -:set shell =/bin/bash
            -:shell
            -#once in the /bin/bash shell
        -#Get password
            -cat /etc/bandit_pass/bandit26

        -#inside a new terminal
            -ssh bandit26@bandit.labs.overthewire.org -p 2220

        



###key concepts learned
-Restricted shells are not secure by default
-Pager behavior depends on terminal size
-vim allows shell execution

