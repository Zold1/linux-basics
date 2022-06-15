# Linux Paths

## What is a path?

A path is a unique location to a file or a folder in a file system of an OS. A path to a file is a combination of / and alpha-numeric characters.

## What is an absolute path?

An absolute path is defined as the specifying the location of a file or directory from the root directory(/). In other words we can say absolute path is a complete path from start of actual filesystem from / directory.

Some examples of absolute path:

* /home/imran/linux-practices/
* /var/ftp/pub
* /etc/samba.smb.conf
* /boot/grub/grub.conf

> If you see all these paths started from / directory which is a root directory for every Linux/Unix machines.

## What is the relative path?

Relative path is defined as path related to the present working directory(pwd). Suppose I am located in /home/zold and I want to change directory to /home/zold/linux-basics. I can use relative path concept to change directory to linux-basics and also devopsdir directory.

``` console
zold@Zold:~$ pwd
/home/zold
zold@Zold:~$ cd linux-basics
zold@Zold:~/linux-basics$ ls
 Archive.md                 'Linux File System.md'     README.md            'Vim Editor.md'
'Best Practices.md'         'Linux Introduction.md'    Redirections.md       linux_architecture.jpg
'File Permissions.md'       'Linux Paths.md'           SSH.md
'Files and Directories.md'  'Networking Commands.md'  'Terminal Basics.md'
 Filters.md                 'Package Management.md'   'User and Groups.md'
zold@Zold:~/linux-basics$ pwd
/home/zold/linux-basics
zold@Zold:~/linux-basics$ cd devopsdir
zold@Zold:~/linux-basics/devopsdir$ pwd
/home/zold/linux-basics/devopsdir
```

> If you see all these paths did not start with / directory.
