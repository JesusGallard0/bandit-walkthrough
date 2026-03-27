##Bandit level 6-7


###Objective
Retrieve the password stored somewhere in the server.The password must meet the following conditions:

-owned by user bandit7
-owned by group bandit6
-33 bytes in size
Gain access to the next level with the password

###Approach
-Used find to search the entire filesystem (/) since the file location is unknown
-Applied filters for:
    -file type(-type f)
    -owner(-user bandit7)
    -group(-group bandit6)
    -size(-size 33c)
-Suppressed permision errors using 2>/dev/null

-Located the matching file 
-Read its contents to obtain the password
-Used the password to log into the next bandit via SSH


###Commands used
-find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
-cat /var/lib/dpkg/info/bandit7.password
-ssh bandit7@bandit.labs.overthewire.org -p 2220


###Key concepts learned
-2>/dev/null suppresses error output (like permission denied) for cleaner results
-Find can be used to search the entire filesystem when the file location is unknown-File filtering can include ownership(-user,-group) and size constraints
