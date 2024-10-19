- [Linux basics](#linux-basics)
- [Week 2](#week-2)
- [File System](#file-system)
- [`cloud-init`](#cloud-init)
- [signals](#signals)
- [exit codes](#exit-codes)
- [processes](#processes)
- [Searching](#searching)
- [Scripting basics](#scripting-basics)


# Linux basics
What is Linux?  
Explain the following terms:
- kernel
- shell
- terminal

What are the responsibilities of the kernel?  
Where does the shell look for commands?  
What is REPL and what is it's relevance to Linux?  

# Week 2
how to update packages with pacman?  
how to install packages with pacman?  
What is SSH?  
Explain how to generate ssh keys and connect to a remote host using them.  

# File System
What is a file system?  
Name two ways to find your home directory  
Where are programs stored?  
Where can I find every user's home directory?  
Where are device files located?  
What is pseudo filesystem?  
explain the what "root" means  
Where can i find information about users and their passwords?  
How can i give a new user permission to use sudo?  
What is special about /bin?  
What are the two types of links and their differences?  
How do you make both of them?  
Where can i find system config files?  
What is special about /proc?  
Where are the files that the operating system uses before the kernel executes user mode programs?  

# `cloud-init`
What is the purpose of cloud-init?  
Create a cloud-init script to configure:
- Adding a User with
  - username, primary group, and supplementary groups
  - shell 
  - can use sudo with no password
  - ssh-key that can be used to remotely connect as this user
- Install packages
  - neovim, less, man-db, github, bash-completion
- disable logging as the root user directly 

# signals
What is a signal?  
List the common signals for ending programs.  
What commands can i use to send signals to programs?  
What signal does CTRL-C send?  
Write a command that interrupts processes that the pattern 'chrome' executed by the user 'Mavis'.  

# exit codes
How can I view the exit code of the last program?  
What do exit codes 0 and 1 mean?  
How can i provide and exit code in my script?  

# processes
How are processed identified?  
What is process 1? What launches it?  
Explain the headings:
- `PID`
- `TTY`
- `CMD`
- `TIME`
- `RSS`
What does it mean when a process has ? as it's value for TTY?  
How can i see only the PID and RSS of each process?  
Why are there so few processes when i use ps?  

# Searching
What is the difference between find and grep?  
Write a command to find files based on  
- when their metadata and content was last modified
- their name
- who owns the file
- their size (larger and smaller? what is the unit?)
- file permissions
- type of file
What does `-exec` do?  
Write a command that finds every file larger than 10 MB and deletes them.  


users and groups
Write a command that adds a new user, gives them a home directory, and sets their login shell to /usr/bin/bash  
Create two groups 'silly-time' and 'souper-user'. Make 'silly-time' the primary group of the member you created, and add 'souper-user'   as an additional group  
List every member of that group.  
Give the user a new password  
Delete the group  

why is using adduser not advised?  
How do i find   
- who belongs to the group "souper-user" as an additional group
- who has the group "silly-time" as their primary group?
- all users?
- info about passwords?

What are the two types of users?  
What user is UID 0?  

This is the output from ls -l  
`drwxr-x-wx`
- What type of file is this?
- What users have reading permission?
- What permissions does the owner have
- What does 'x' mean in reference to the file?
- Set the permission for 'other users' to read and execute using symbolic
- Set the permission for the group to write only using octal.

how do you change the ownership of files?  

Why is it reocommended to not stay logged in as the root user?  
How do i give a user sudo permissions?  


# Scripting basics
Write a for loop.  
Write an if statement with else if and else.  
