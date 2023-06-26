# Managing file ownership 2.8a

## Why is managing file ownership important?

Managing file ownership is crucial for security and access control. It ensures that sensitive files are only accessible to authorized users. Additionally, file ownership allows for accountability by identifying who made changes to a file.

## What is the command to view file ownership?

The command to view file ownership is `ls -l`. This command provides a long format listing that includes ownership information.

## What permissions are set when a user creates a file or directory? Who does the file or directory belong to?

When a user creates a file or directory, the permissions are set based on the default umask value. The file or directory belongs to the user who created it. By default, the owner is granted read and write permissions, while other users do not have any permissions.

## Why does the owner, by default, not receive X permissions when they create a file?

The owner does not receive execute (X) permissions by default when creating a file to prevent accidental execution of potentially harmful files. Execute permissions are typically given explicitly when necessary.

## What command is used to change the owner of a file or directory?

The command used to change the owner of a file or directory is `chown`. This command allows you to change the ownership to a specified user or group.

# Managing file permissions Task 2.8b

## Does being the owner of a file mean you have full permissions on that file?

Being the owner of a file does not necessarily mean having full permissions. The owner may have read, write, and execute permissions, but it depends on the specific permissions assigned to the file.

## If you give permissions to the User entity, what does this mean?

Giving permissions to the User entity means granting those permissions to the user who owns the file or directory. The User entity represents the owner of the file or directory.

## If you give permissions to the Group entity, what does this mean?

Giving permissions to the Group entity means granting those permissions to the group associated with the file or directory. Multiple users can belong to a group, and by assigning group permissions, these users gain the specified access rights.

## If you give permissions to the Other entity, what does this mean?

Giving permissions to the Other entity means granting those permissions to all other users who are neither the owner nor part of the group. The Other entity represents users who do not fall into the User or Group categories.

## You give the following permissions to a file: User permissions are read-only, Group permissions are read and write, Other permissions are read, write, and execute. You are logged in as the user which is the owner of the file. What permissions will you have on this file? Explain.

As the owner of the file, your permissions will be read-only. This is because the User permissions, which pertain to the file owner, are set to read-only. The permissions granted to the Group and Other entities, which allow for reading, writing, and executing, do not apply to you as the file owner.

## Here is one line from the ls -l. Work everything you can about permissions on this file or directory.

The line `-rwxr-xr-- 1 tcboony staff` details the permissions for the file or directory:

- The first character `-` indicates that it is a regular file.
- The subsequent characters `rwx` indicate that the owner (User entity) has read, write, and execute permissions.
- The characters `r-x` represent the read and execute permissions for the Group entity.
- The characters `r--` represent read-only permission for the Other entity.
- The number `1` indicates the number of hard links to the file or directory.
- `tcboony` is the owner (user) of the file or directory.
- `staff` is the group associated with the file or directory.

# Managing file permissions using numeric values 2.8c

## What numeric values are assigned to each permission?

The numeric values assigned to each permission are as follows: Read (r) is `4`, Write (w) is `2`, and Execute (x) is `1`.

## What can you do with the values assigned read + write permissions?

When the numeric values for read (`4`) and write (`2`) are added together, you get a total of `6`. This means you can both read the file's contents and modify (write to) the file.

## What value would assign read, write, and execute permissions?

The numeric value that would assign read, write, and execute permissions is `7` (4+2+1).

## What value would assign read and execute permissions?

The numeric value that would assign read and execute permissions is `5` (4+1).

## Often, a file or directory's mode/permissions are represented by 3 numbers. What do you think 644 would mean?

The value `644` represents the file or directory's permissions:

- The leftmost digit `6` represents the owner's permissions (read and write).
- The middle digit `4` represents the group's permissions (read-only).
- The rightmost digit `4` also represents read-only permissions for others.

# Changing file permissions 2.8d

## What command changes file permissions?

The command to change file permissions is `chmod` (Change Mode).

## To change permissions on a file, what must the end user be? (2 answers)

To change permissions on a file, the end user must be either the owner of the file or an administrator with the appropriate privileges.

## Give examples of some different ways/syntaxes to set permissions on a new file (named test.txt) to: Set User to read, Group to read + write + execute, and Other to read and write only

The following commands can be used to set permissions on a new file named `test.txt`:

- Using symbolic notation: `chmod u=r,g=rwx,o=rw test.txt`
- Using numeric notation: `chmod 764 test.txt`

## Add execute permissions (to all entities)

To add execute permissions to all entities, use the command: `chmod +x test.txt`

## Take write permissions away from Group

To remove write permissions from the Group entity, use the command: `chmod g-w test.txt`

## Use numeric values to give read + write access to User, read access to Group, and no access to Other

To use numeric values to give read + write access to User, read access to Group, and no access to Other, use the command: `chmod 640 test.txt`

# Linux Commands

- `cat chicken-joke.txt | grep chicken`

  - This command reads the contents of the file "chicken-joke.txt" and passes it to the `grep` command, which searches for the word "chicken" in the input and displays the matching lines.

- `apt install tree`

  - This command installs the "tree" package using the package manager "apt". Tree is a utility that displays the directory structure in a tree-like format.

- `sudo apt install tree`

  - Same as the previous command, but it runs with administrative privileges (sudo).

- `sudo apt-get update -y`

  - This command updates the package lists and upgrades the installed packages on the system. The "-y" flag automatically confirms any prompts during the update process.

- `cd /`

  - Changes the current directory to the root directory ("/").

- `mkdir del_temp`

  - Creates a new directory named "del_temp" in the current directory.

- `cd del_temp/`

  - Changes the current directory to the "del_temp" directory.

- `cd ..`

  - Moves up one directory level (to the parent directory).

- `rm -r del_temp/`

  - Deletes the "del_temp" directory and its contents recursively ("-r" flag).

- `mkdir funny-jokes`

  - Creates a new directory named "funny-jokes" in the current directory.

- `pwd`

  - Prints the current working directory (full path).

- `cd ../..`

  - Moves up two directory levels (to the grandparent directory).

- `mv chicken-joke.txt funny-stuff/funny-jokes/`

  - Moves the file "chicken-joke.txt" to the "funny-jokes" directory inside the "funny-stuff" directory.

- `mv chicken-joke.txt test-del.txt`

  - Renames the file "chicken-joke.txt" to "test-del.txt" in the current directory.

- `mv test-del.txt ../../`

  - Moves the file "test-del.txt" to the parent directory.

- `mv chicken-joke.txt funny-stuff/funny-jokes/`

  - Moves the file "chicken-joke.txt" to the "funny-jokes" directory inside the "funny-stuff" directory.

- `mv chicken-joke.txt ~/funny-stuff/`

  - Moves the file "chicken-joke.txt" to the "funny-stuff" directory in the user's home directory.

- `cp chicken-joke.txt bad-joke.txt`

  - Copies the file "chicken-joke.txt" and creates a new file named "bad-joke.txt" in the current directory.

- `mv bad-joke.txt ~/`

  - Moves the file "bad-joke.txt" to the user's home directory.

- `rm -r funny-stuff/`
  - Deletes the "funny-stuff" directory and its contents recursively ("-r" flag).

### Linux Commands

#### System Update and Package Management

- `sudo apt upgrade`

  - This command is used to upgrade all upgradable packages on the system.

- `sudo apt install nginx`
  - This command is used to install the 'nginx' package.

#### Nginx Service Management

- `sudo systemctl start nginx`

  - Starts the 'nginx' service.

- `sudo systemctl restart nginx`

  - Restarts the 'nginx' service.

- `sudo systemctl enable nginx`

  - Enables the 'nginx' service to start on boot.

- `sudo systemctl is-enabled nginx`

  - Checks whether the 'nginx' service is enabled to start on boot.

- `sudo systemctl status nginx`
  - Checks the status of the 'nginx' service.

#### Shell Scripts

- `./provision.sh`

  - Executes the 'provision.sh' shell script in the current directory.

- `nano provision.sh`

  - Opens the 'provision.sh' file in the nano text editor.

- `cat provision.sh`
  - Displays the content of 'provision.sh' file in the terminal.

#### Environment Variables

- `printenv`

  - Prints all environment variables.

- `printenv USER`

  - Prints the 'USER' environment variable.

- `MYNAME=zain`

  - Sets the 'MYNAME' environment variable to 'zain'.

- `echo "hello"`

  - Prints "hello" to the console.

- `echo $MYNAME`

  - Prints the value of 'MYNAME' environment variable.

- `export MYNAME=zain`

  - Exports the 'MYNAME' environment variable so it is available to child processes.

- `export MYCATSNAME=Silkie`

  - Exports the 'MYCATSNAME' environment variable so it is available to child processes.

- `printenv MYCATSNAME`
  - Prints the 'MYCATSNAME' environment variable.

#### Process Management

- `ps`

  - Displays the current running processes.

- `exit`
  - Exits the current shell.

#### User's Bash Environment

- `nano .bashrc`

  - Opens the '.bashrc' file in the nano text editor.

- `tail -5 .bashrc`

  - Shows the last 5 lines of the '.bashrc' file.

- `source .bashrc`
  - Loads the '.bashrc' file, applying any changes made.

#### Terminal History

- `history`
  - Shows the history of commands that have been entered in the terminal.

kill - 9 command:

- brute force method.

## Copy file to VM

`scp -i ~/.ssh/tech241-zain-az-key app.zip adminuser@51.11.137.173:~/`
`<Path to private key><Path to file you want to transfer><username and public ip of machine>:<path you want to store file>`

## provision.sh

#!/bin/bash

# update source list

sudo apt update -y

# upgrade all the packages and installs them in the kernal

sudo apt upgrade -y

# install nginx

sudo apt install nginx -y

# start nginx

sudo systemctl start nginx

# status nginx

# sudo systemctl status nginx

# Linux Commands Explanation

## NSG rules

- Added port 3000 to the NSG rules on azure website.
- Inbound port rule

## Process Management

- **ps aux**: Display detailed information about all the current running processes in the system. The 'aux' option shows processes for all users, in a user-oriented format.

- **sleep**: Pause for an amount of time. The number following the command is the number of seconds to pause. For example, `sleep 3` pauses for 3 seconds.

- **jobs**: Display the status of jobs in the current session.

- **jobs -l**: List the current jobs along with their process IDs.

- **kill**: Terminate processes. The number following the command is the process ID to terminate. The `-1` and `-9` are signals specifying how to terminate the process. `-1` is a hangup signal, and `-9` is a kill signal.

- **ps -ef**: Display a full listing of all current processes.

- **kill -1 4528**: Sends a HUP (hang up) signal to the process with ID 4528.

- **kill -15 4528**: Sends a TERM (terminate) signal to the process with ID 4528.

- **kill -9 4528**: Sends a KILL signal to the process with ID 4528.

## File Management

- **nano**: Open the file in the nano text editor. For example, `nano provision.sh` opens the file `provision.sh` in the nano text editor.

- **ls**: List the files and directories in the current directory.

- **rm**: Remove files or directories. The `-r` option is used to remove directories and their contents recursively.

- **cd**: Change the current directory. `cd` without any arguments changes to the home directory.

- **mv**: Move or rename files or directories. For example, `mv app app-scp` renames the directory `app` to `app-scp`.

- **rm -rf app-github/**: Recursively removes the `app-github` directory and its contents.

## Git Commands

- **git --version**: Display the installed version of Git.

- **git clone**: Clone the Git repository at the provided URL into a new directory in the current location. For example, `git clone https://github.com/Zain-Ashfaq/tech241-sparta-app` clones the specified Git repository.

## Node.js and npm Commands

- **curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -**: Downloads and runs the NodeSource setup script for Node.js 12.x.

- **sudo apt install nodejs -y**: Installs Node.js using the apt package manager.

- **sudo npm install pm2 -g**: Installs the pm2 process manager globally using npm.

- **npm install**: Installs the dependencies listed in the `package.json` file in the current directory.

- **npm start**: Runs the script named "start" defined in the `package.json` file in the current directory.

## Other Commands

- **history**: Display the command line history.

- **clear**: Clears the terminal screen.
