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
