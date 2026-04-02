##Bandit level 20-21



###Objective
Use the setuid binary in the homedirectory.
This binary connects to localhost on a port you specify,reads a line of input, and compares it to the password of the current level.
if the input matches,it returns the password for bandit21
###Approach
-Listed files to locate the setuid binary
-Started a listener with netcat opening a port that is not n use (nc -lvp 30003)
-Trigger binary from another terminal in a second session as bandit20 and executed ./succonect 30003
-Sent the password through the listener
-Recieved the password as an output 
-Used the password to authenticate as bandit21 in the next level


###Commands used
-ls
-#first terminal
    -nc -lvp 30003
-#second terminal
    -./succonect 30003
-#first terminal
    -#paste bandit20 password

-ssh bandit21@bandit.labs.overthewire.org -p 2220



###Key concepts learned
-Setuid binaries can be programmed to do anything the developer wants
-Netcat is a versatile tool for:
    -Opening listening ports (-l)
    -Debugging network interactions
    -Sending/receiving raw plaintext over TCP

