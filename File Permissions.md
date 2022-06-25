# File Permissions

## Linux File Ownership

Every file and directory on your Unix/Linux system is assigned 3 types of owner, given below.

* **User:** a user is the owner of the file. By default, the person who created a file becomes its owner. Hence, a user is also sometimes called an owner.
* **Group:** a user- group can contain multiple users. All users belonging to a group will have the same Linux group permissions access to the file.
* **Other:** any other user who has access to a file. This person has neither created the file, nor he belongs to a usergroup who could own the file. Practically, it means everybody else.

***

## Linux File Permissions

Every file and directory in your UNIX/Linux system has following 3 permissions defined for all the 3 owners discussed above.

* **Read:** This permission give you the authority to open and read a file. Read permission on a directory gives you the ability to lists its content.
* **Write:** The write permission gives you the authority to modify the contents of a file. The write permission on a directory gives you the authority to add, remove and rename files stored in the directory. Consider a scenario where you have to write permission on file but do not have write permission on the directory where the file is stored. You will be able to modify the file contents. But you will not be able to rename, move or remove the file from the directory.
* **Execute:** In Windows, an executable program usually has an extension “.exe” and which you can easily run. In Unix/Linux, you cannot run a program unless the execute permission is set. If the execute permission is not set, you might still be able to see/modify the program code(provided read & write permissions are set), but not run it.

Let’s see file permissions in Linux with examples by `ls -l` command:

``` console
zold@Zold:~/linux-admin1$ ls -l
total 92
-rw-rw-r-- 1 zold zold  1377 Jun 14 16:10 'File Permissions.md'
```

Here, we have highlighted '-rw-rw-r--' and this weird looking code is the one that tells us about the Unix permissions given to the owner, user group and the world.

Here, the first '–' indicates the file type

| key | Type
| --- | ----
| -   | File
| d   | Directory
| l   | Link [Shortcut]
| c   | Special File [Such as files in /dev/]
| s   | Socket
| p   | Pipe

The characters are pretty easy to remember.

* `r` read = 4
* `w` write = 2
* `x` execute = 1
* `-` No Permission = 0
* `u` user → first 3 letters
* `g` group → second 3 letters
* `o` others → last 3 letters

Let us look at it this way.

The first part of the code is ‘rw-‘. This suggests that the owner ‘Home’ can:

* Read the file
* Write or edit the file
* He cannot execute the file since the execute bit is set to ‘-‘.

By design, many Linux distributions like Fedora, CentOS, Ubuntu, etc. will add users to a group of the same group name as the user name. Thus, a user ‘tom’ is added to a group named ‘tom’.

The second part is ‘rw-‘. It for the user group ‘Home’ and group-members can:

* Read the file
* Write or edit the file

The third part is for the world which means any user. It says ‘r–‘. This means the user can only:

* Read the file

***

## Change Owners

* `chown <user>.<group> <file>` change user and group owners of file
* `chown -R <user>.<group> <directory>` change user and group owners of directory
* `chown <user> <file>` change user owner only
* `chgrp <group> <file>` Change group owner only

**Note:** For debian use : instead of .

**Example:** `chown zold:devops script.sh`

## Change Permissions

We can use the ‘chmod’ command which stands for ‘change mode’. Using the command, we can set permissions (read, write, execute) on a file/directory for the owner, group and the world.

For change permissions

* `+` Add
* `-` Minus
* `=` Set

Examples:

* `chmod g+w <file>` add write permession for group
* `chmod -rx <file>` remove read & execute for all [user, group, others]
* `chmod 750 <file>` add permessions by numbers

[Next: Package Management](./Package%20Management.md)

[Prev: User and Groups](./User%20and%20Groups.md)