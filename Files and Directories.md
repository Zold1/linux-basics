# Files and Directories Commands

## Directory Path Commands

* `ls` get list directory contents
  * `ls -a` don't ignore hidden contents which starting with .
  * `ls -R` get list subdirectories recursively
  * `ls -l` get list directory contents with a long listing format
  * `ls <Directory>` specify directory which command execute on it
  ![ls](./images/ls-1.png)
* `cd <Directory Path>` change the
* `pwd` print name of current/working directory
 working directory
![pwd](./images/pwd-1.png)

***

## Directories Commands

The first thing you need to know is that: Directories in Linux = Folders in Windows

### New Directories

* `mkdir <Directory>` make directories
![mkdir](./images/mkdir-1.png)
![mkdir](./images/mkdir-2.png)
* `mkdir -p <Directory1>/<Directory2>` make nested directories, if they don't exist already.
![mkdir](./images/mkdir-3.png)

### Copy Directories

* `cp -r <Directory> <Path>` copy directories recursively
![cp](./images/cp-1.png)

### Remove Directories

* `rmdir <Directory>` or `rm -d <Directory>` remove empty directories
![rm](./images/rm-1.png)
* `rm -r <Directory>` remove directories and their contents recursively
![rm](./images/rm-2.png)
* `rm -rf **` remove all [directories, files, ...]
![rm](./images/rm-3.png)

***

## Files Commands

### New Files

* `touch <File>` make files
![touch](./images/touch-1.png)

### Copy Files

* `cp <File> <Path>` copy file
![cp](./images/cp-2.png)

### Remove Files

* `rm <File>` remove files
![rm](./images/rm-4.png)

### Show Data of Files

* `cat <File>` concatenate files and print on the standard output
![cat](./images/cat-1.png)
* `file <File>` determine file type
![file](./images/file-1.png)

***

## Links

* `ln -s <File Path> <Link Name>` make links between files
![ln](./images/ln-1.png)
* `unlink <Link>` remove link
![unlink](./images/unlink-1.png)

***

## Move/Rename

* `mv <Old File> <New File>` move (rename) [files, directories, ...]
![mv](./images/mv-1.png)