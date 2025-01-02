### What is Shell Scripting in DevOps?

Shell scripting is a way to automate repetitive tasks by writing scripts that execute commands in a Linux shell. These scripts are used for:

- File manipulation: Automating backups, log rotations, etc.

- Task scheduling: Setting up cron jobs.

- Custom workflows: Automating deployments, server provisioning, etc.

Example: Let’s say you need to create daily logs. Instead of doing it manually, you can write a shell script to automate it:

```
rajas_pawar@APAC-IND-LAP181:~/DevOps/Learning/Day4$ #!/bin/bash
DATE=$(date +%F)
echo "Log created on $DATE" > daily.log
rajas_pawar@APAC-IND-LAP181:~/DevOps/Learning/Day4$ ls
daily.log
rajas_pawar@APAC-IND-LAP181:~/DevOps/Learning/Day4$
```


### What is #!/bin/bash?

The line #!/bin/bash is called a shebang. It specifies the shell interpreter to use for executing the script.

- #!/bin/bash: Specifies the Bash shell.

- #!/bin/sh: Uses the default shell, which may be Bourne Shell or a compatible shell, depending on the system.

And yes we can write #!/bin/sh instead of #!/bin/bash, but note that some Bash-specific features may not work in sh.


### Tasks for the Day -

1. Print a Message

Here’s a simple shell script that prints a message:

- First create a blank file

```rajas_pawar@APAC-IND-LAP181:~/DevOps/Learning/Day4$ touch day4.sh```

- Using Vim put the code as below

```#!/bin/bash  
echo "I will complete #90DaysOfDevOps challenge!"
```
- Assign it permissions using chmod and Run it
```
$ chmod +x day4.sh  
$ ./day4.sh
```
- Output :
```
rajas_pawar@APAC-IND-LAP181:~/DevOps/Learning/Day4$ ./day4.sh
I will complete #90DaysOfDevOps challenge
```
2. Take User Input and Command-Line Arguments

- Again create another file day4-1.sh and put below code in that , A script to take input from the user and command-line arguments:
```
rajas_pawar@APAC-IND-LAP181:~/DevOps/Learning/Day4$ touch day4-1.sh
rajas_pawar@APAC-IND-LAP181:~/DevOps/Learning/Day4$ vim day4-1.sh

#!/bin/bash
echo "Enter your name:"            # It will ask for Name Promt
read NAME 
echo "Hello, $NAME!"

# Using command-line arguments
echo "First argument: $1"
echo "Second argument: $2"
```
- Save this file and hit script after giving permissions and hit command as below ,
```
$ chmod +x day4-1.sh
$ ./day4-1.sh DevOps Journey
```
- Output :
```
rajas_pawar@APAC-IND-LAP181:~/DevOps/Learning/Day4$ ./day4-1.sh DevOps Journey
Enter your name:
Rajas Pawar
Hello, Rajas Pawar!
First argument: DevOps
Second argument: Journey
```
3. If-Else Example: Comparing Two Numbers

- First create a blank file
```
rajas_pawar@APAC-IND-LAP181:~/DevOps/Learning/Day4$ touch day4-2.sh
```
- Using Vim put the code as below
```
#!/bin/bash
NUM1=10
NUM2=20

if [ $NUM1 -gt $NUM2 ]; then
    echo "$NUM1 is greater than $NUM2"
else
    echo "$NUM1 is not greater than $NUM2"
fi
```
- Assign it permissions using chmod and Run it
```
$ chmod +x day4-2.sh  
$ ./day4.sh
```
- Output :
```
rajas_pawar@APAC-IND-LAP181:~/DevOps/Learning/Day4$ ./day4-2.sh
10 is not greater than 20
```

### Points To remember :

- Always Check file should not be empty (view with cat cmd)

- File must have permission to execute (+x)
