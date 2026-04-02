##Bandit level 21-22


###Objective
Identify a program that runs automatically via cron (the time-based job scheduler) inspect /etc/cron.d/ to determinate what command is executed and how can it be leveraged to retrieve the password for the next level

###Approach
-Navigated to cron configuration directoy usig cd /etc/cron.d
-listed files ls -l 
-Located a file named cronjob_bandit22 which is likely associated with the next level 
-Using cat to inspect the file output:
    * * * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
        -Runs every minute (* * * * *)
        -Executes as a user bandit22 
        -Calls the script /usr/bin/cronjob_bandit22.sh
        -Suppresses output (&> /dev/null)

-Inspecting the script:
    #!/bin/bash
     chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
     cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
        -The script reads the password for bandit22
        -Writes it into a file in /tmp
        -Sets permissions to 644

-Retrieve the password for the next level reading the file in the script

-Used the password to authenticate in the next level


###Commands used
-cd /etc/cron.d
-ls -l 

-cat cronjob_bandit22
-cat  cat /usr/bin/cronjob_bandit22.sh

- cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
-ssh bandit22@bandit.labs.overthewire.org -p 2220


###Key concepts learned
-/tmp directory is globally writable ,commonly used for temporary files,no sensitive data recommended

-chmod 644 makes a file world-readable ,which creates a vulnerability

-Cron is a scheduler that executes commands at fixed intervals

* * * * * command
│ │ │ │ │
│ │ │ │ └── day of week
│ │ │ └──── month
│ │ └────── day of month
│ └──────── hour
└────────── minute
