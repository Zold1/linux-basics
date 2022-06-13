# Files and Directories Commands

## Make Directories

The first thing you need to know is that: Directories in Linux = Folders in Windows

* `mkdir <Directory>` make directory
![images/mkdir-1.png]()
* `mkdir <Directory1> <Directory2> <Directory3>` make multi directories
* `mkdir -p /<Directory1>/<Directory2>/<Directory3>` will create nested directories, if they don't exist already.

***

## Make Files

* `touch <File>` make file
* `touch <File1> <File2> <File3>` make multi files

***

## Copy

* `cp <File> <Path>` copy file
* `cp -r <Directory> <Path>` copy directory recursively

***

## Remove

* `rm <File>` remove file
* `rmdir <Directory>` or `rm -d <Directory>` delete empty directory
* `rm -r <Directory>` remove directory and their contents recursively
* `unlink <Link>` remove link

***

## List Directory Contents

* `ls` get list directory contents
* `ls -a` don't ignore hidden contents which starting with .
* `ls -R` get list subdirectories recursively
* `ls -l` get list directory contents with a long listing format
* `ls <Directory>` specify directory which command execute on it

***

## Other Commands

* `cat <File>` print file on the standard output
* `cat <File1> <File2>` concatenate files and print on the standard output
* `file <File>` determine file type
* `pwd` print name of current/working directory
* `cd <Directory Path>` change the working directory
