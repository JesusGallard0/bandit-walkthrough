##Bandit level 22-23


###Objecetive
Identify the program executed by cron,analyze its behavior, and retrieve the password for the next level

###Approach
-Navigated to the cron  configuration directory /etc/cron.d
-Listed files to locate the relevant cron job
-Identified the file cronjob_bandit23
-Read its contents to determine which script is being executed 
-Located and analyzed the referenced script:

    #!/bin/bash

myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)

echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"

-The script determines the current user using whoami
-It generates a file name by hashing the string 
    "I am user <username>"
    using md5sum
    The password file for that user is copied to /tmp/<hash>

-Since the filename in /tmp is predictable,i reproduced the same hash locally
-It produced a generated file name which i read using cat /tmp/filename
-This file contained the password for bandit23

-Used the retrieved password to log into the next level

###Commands used

cd /etc/tmp
ls
cat cronjob_bandit23
cat  /usr/bin/cronjob_bandit23.sh

 echo "I am user bandit23" | md5sum
 cat /tmp/8ca319486bfbbc3663ea0fbe81326349
 
ssh bandit23@bandit.labs.overthewire.org -p 2220



###Key concepts learned

-Cron jobs can expose sensitive operations if their logic is predictable
-A hash function like MD5 converts input into a fixed-lenght,deterministic output
    -The same input will always produce the same hash
-Hashing does not provide security if the input is known or easily guessable
-Reading and understanding shell scripts is a fundamental cybersecurity skill

