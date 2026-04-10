## Bandit level 32-33


### Objective 
Escape the restricted shell environment and retrieve the password



### Approach
-Logged into the server and encountered with a restircted UPPERCASE SHELL
-Attempted multiple standard commands but all were rejected with "permission denied"
-Recognized that the shell was restricting input rather than execution entirely
-Used the special variable $0 to invoke the current shell binary directly
-This bypassed the input restriction and spawned a normal interactive shell
-Navigated to the directory containing the password /etc/bandit_pass/bandit33
-Retrieved the password for bandit33



### Commands used
-$0
-cat /ect/bandit_pass/bandit33



### Key concepts learned
-$0 is a special variable that represents the current shell or script name.Executing $0 can spawn a new shell instance,potentially bypassing restrictions
-The restriction railed on filtering user input rather than properly sandboxing execution,making it bypassable
