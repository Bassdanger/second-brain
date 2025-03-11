1. Docker hub
2. Search Ubuntu
3. in the bash `docker run ubuntu`
4. `docker ps -a`
5. `docker run -it ubuntu`
6. Shell prompt shows up
7. `/` = root directory
8. `#` = highest privileges
9. `whoami` = shows which user
10. Linux is case sensitive
11. Up and down arrows recycle commands 
12. `history` = sees latest commands
13. `!2` = shows second command used

**Managing Packages
1. `apt` - package manger for ubuntu
2. `apt-get` - the old one
3. `nano` - basic text editor for Linux
4. `apt update` - gets latest packages
5. `apt list` - gets all packages
6. `apt install nano` - installs nano
7. `apt update` - always run this first before using packages
8. `Control + X` - exit out of nano
9. `Control + L` - clears window
10. `apt remove nano` - removes nano
11. use apt to install python

**Navigating in Linux
1. `pwd` - present working directory
2. `ls` - list
3. `ls -1` - lists one item per line
4. `ls -l` - see long listing, permissions, user ownership, size, ownership
5. `cd` - change directory
6. `cd ..` - goes one level up
7. `ls /bin` - see items in bin directory
8. `cd `squiggly line my keyboard does have it lol - goes to root directory

**Manipulating Files and Directories
1. `cd root` 
2. `mkdir test`
3. `ls`
4. `mv test docker` - renames test to docker
5. `ls
6. `cd docker
7. `touch hello.txt` - creates hello.txt
8. `ls`
9. `touch file1.txt file2.txt file3.txt` - makes three files
10. `ls
11. `ls -1
12. `mv hello.txt /etc` - moves it to etc directory (don't do this)
13. `Control + W` - removes entire word
14. `mv hello.txt hello-docker.txt`
15. `rm file*` - removes all files that start with "file"
16. `ls
17. `cd ..
18. `rm -r docker/` - removes the directory and all it's content

**Editing and Viewing Files
1. `apt install nano`
2. `nano file1.txt`
3. type hello world
4. `Control + X
5. Yes
6. Enter
7. `ls
8. `cat file1.txt` - sees content of a file (short content usually)
9. `more /etc/adduser.conf` - see more details of longer files
10. Press space to go to the next page, enter to go line by line
11. press q to exit
12. `apt install less` - newer command to replace more
13. `less /etc/adduser.conf` - now you can scroll down in up with arrow key
14. `head -n 5 /etc/adduser.conf` - see first 5 lines of file
15. `tail -n 5 /etc/adduser.conf` - see last 5 lines of file

**Redirection
1. `cat file1.txt`
2. `cat file1.txt > file2.txt` - writes file1 data to file2
3. `cat file1.txt file2.txt > combined.txt` - combines both files
4. `echo hello
5. `echo hello > hello.txt` - writes hello to hello.txt
6. `ls -l /etc > files.txt` - writes the long list of /etc to files.txt
7. `cat files.txt`

**Searching for Text
1. `grep hello file1.txt` -finds hello in file (case sensitive)
2. `grep -i hello file1.txt` - find hello in file (case insensitive)
3. `grep -i root /etc/password`
4. `grep -i hello file*` - search all files for "hello"
5. `grep -i -r hello .` - search current directory for "hello"
6. `grep -ir hello .` - same exact command

**Finding Files and Directories
1. `ls`
2. `find` - shows all files in the directory, even hidden files
3. `ls -a` - sees all files including hidden files
4. `find /etc` - all files in etc
5. `find -type d` - shows only the directories in the search
6. `find -type f` - shows only the files in the search 
7. `find -type f -name "F*"` - finds all files that start with F (case sensitive)
8. `find -type f -iname "F*"` - finds all files that start with F (case insensitive)
9. `find / -type f -name "*.py"` - finds all python files in the image
10. `find / -type f -name "*.py" > python-files.txt` - output all the python files found in a text file 

**Chaining Commands
1. `mkdir test;cd test;echo done` - use a semicolon to chain commands
2. `mkdir test && cd test && echo done` - if first command fails the other will fail
3. `mkdir test || echo "directory exist"` - makes directory or directory exists
4. `ls /bin`
5. `ls /bin | less` - piping, less doesn't need the file name it uses the input from the ls command 
6. `ls /bin | head`
7. `ls /bin | head -n 5` 
8. `mkdir hello;\` - let's you continue writing the command on a new line for breaking commands up 

**Environment Variables
1. `printenv` - see all environment variables
2. `printenv PATH` - see PATH variable (case sensitive)
3. `echo $PATH` - $ references a environment variable, see PATH variable
4. `export DB_USER=mosh` - creates environment variable only for the current session
5. `exit` - terminates session
6. `docker ps`
7. `docker ps - a`
8. `docker start -i 2f7` - starts container with first 2 letters of id
9. environment data will be good
10. `cd root
11. `.bashrc` - the user personal startup file
12. `echo DB_USER=mosh >> .bashrc` - appends DB_USER to .bashrc
13. `cat .bashrc` 
14. Never store sensitive information in environment variables, it is just plain text 
15. `exit`
16. `docker start -i 2f7`
17. `echo $DB_USER`
18. The .bashrc file has to be reloaded to see any updates
19. `source .bashrc` - reloads file

**Managing Processes
1. `ps` - see all running processes
2. `sleep 3` - prompt sleeps for 3 seconds
3. `sleep 3 &` - sleep runs in the background so you can run other commands
4. `kill 38` - kills process with process id (PID)

**Managing Users
1. `useradd -m john` - adds a user called "john"
2. `cat /etc/passwd` - to see user info
3. `usermod -s /bin/bash john` -changes the shell program
4. `cat /etc/shadow` - passwords stored here in encrypted format
5. new window
6. `docker ps` 
7. `docker exec -it <container_id> bash`
8. `exit`
9. `docker exec -it -u john <container_id> bash` - logs in as john
10. `$` - means you are not a root user like `#`
11. `cat /etc/shadow` - can't access because you don't have permissions
12. `userdel johh` - deletes user (don't do this)
13. `adduser bob` - cooler useradd basically that tells you more and interactive
	1. Don't use this in Docker

**Managing Groups
1. `groupadd developers`
2. `cat /etc/group` - to see groups
3. `usermod -G developers john`
4. `cat /etc/passwd | grep john` or `grep john /etc/passwd`
5. `groups john` - to see a users groups

**File Permissions
1. `cd /home`
2. `echo echo hello > deploy.sh`
3. `cat deploy.sh`
4. `ls -l`
5. If first letter is `d`, that means it is a directory, `-` means it is a file
6. `r` - read, `w` - write, `x` - execute
7. first group is permissions for who owns the file,  second group is permissions for the group who owns the file, the third group is for everyone else 
8. `./deploy.sh` - executes the file
9. `chmod u+x deploy.sh` - adds execute permission (`chmod u-x` to remove permission)
10. `ls -l`
11. `./deploy.sh`
12. switch to john terminal
13. `cd ..`
14. `ls -l` 
15. `./deploy.sh`
16. switch to root
17. `chmod o+x deploy.sh` - allows execute permission to others
18. switch to john
19. `./deploy.sh`
20. switch to root
21. `chmod og+x+w-r deploy.sh` - gives others and groups permissions execute, write, removes read permission