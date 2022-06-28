# Files and Directories

## Directory Path Commands

The first thing you need to know is that: Directories in Linux = Folders in Windows

* `ls` get list directory contents
  * `ls -a` don't ignore hidden contents which starting with .
  * `ls -R` get list subdirectories recursively
  * `ls -l` get list directory contents with a long listing format
  * `ls <Directory>` specify directory which command execute on it

``` console
root@Zold:~# ls
devops  file1.txt

root@Zold:~# ls -a
.  ..  .bash_history  .bashrc  .config  .docker  .motd_shown  .npm  .profile  .viminfo  devops

root@Zold:~# ls -l
total 8
drwxr-xr-x 2 root root 4096 Jun 13 10:52 devops
-rw-r--r-- 1 root root   13 Jun 13 10:54 file.txt

root@Zold:~# ls -R
.:
devops  file.txt

./devops:
file2.txt

root@Zold:~# ls -al devops
total 8
drwxr-xr-x 2 root root 4096 Jun 13 10:52 .
drwx------ 6 root root 4096 Jun 13 10:54 ..
-rw-r--r-- 1 root root    0 Jun 13 10:51 file2
```

* `cd <Directory Path>` change the working directory
* `pwd` print name of current/working directory

``` console
root@Zold:~# cd /home/zold
root@Zold:/home/zold# pwd
/home/zold
```

***

## Directories Commands

### New Directories

* `mkdir <Directory>` make directories

``` console
root@Zold:~# mkdir devops-folder
root@Zold:~# ls
devops-folder

root@Zold:~# mkdir kubernetes terraform jenkins
root@Zold:~# ls
jenkins kubernetes terraform
```

* `mkdir -p <Directory1>/<Directory2>` make nested directories, if they don't exist already.

``` console
root@Zold:~# mkdir -p aws/eks/kubernetes
root@Zold:~# ls -R
.:
aws

./aws:
eks

./aws/eks:
kubernetes

./aws/eks/kubernetes:
```

### Copy Directories

* `cp -r <Directory> <Path>` copy directories recursively

``` console
root@Zold:~# ls
aws  devops
root@Zold:~# cp -r aws devops
root@Zold:~# ls devops
aws
```

### Remove Directories

* `rmdir <Directory>` or `rm -d <Directory>` remove empty directories

``` console
root@Zold:~# ls
aws  devops
root@Zold:~# rmdir aws
root@Zold:~# ls
devops
```

* `rm -r <Directory>` remove directories and their contents recursively

``` console
root@Zold:~# ls devops
ansible  aws  cloud  kubectl
root@Zold:~# rm -r devops
root@Zold:~# ls
root@Zold:~#
```

* `rm -rf **` remove all [directories, files, ...]

``` console
root@Zold:~# ls
aws  azure  devops  terraform  cloud  eks  prometheus
root@Zold:~# rm -rf **
root@Zold:~#
```

***

## Files Commands

### New Files

* `touch <File>` make files

``` console
root@Zold:~# touch devops{1..5}.txt
root@Zold:~# ls
devops1.txt  devops2.txt  devops3.txt  devops4.txt  devops5.txt
```

### Copy Files

* `cp <File> <Path>` copy file

``` console
root@Zold:~# ls
file.txt
root@Zold:~# cp file.txt terraform.tfvars
root@Zold:~# ls
file.txt  terraform.tfvars
```

### Remove Files

* `rm <File>` remove files

``` console
root@Zold:~# ls
file.txt  terraform.tfvars
root@Zold:~# rm file.txt terraform.tfvars
root@Zold:~# ls
root@Zold:~#
```

### File Type

* `file <File>` determine file type

``` console
root@Zold:~# ls
aws.txt
root@Zold:~# file aws.txt
aws.txt:  ASCII text
```

***

## Links

Links in Linux = Shortcuts in Windows

* `ln -s <File Path> <Link Name>` make links between files

``` console
root@Zold:~# ln -s /home/zold/script.sh script-link
root@Zold:~# ls
script-link
```

* `unlink <Link>` remove link

``` console
root@Zold:~# ls
script-link
root@Zold:~# unlink script-link
root@Zold:~# ls
root@Zold:~#
```

***

## Move/Rename

* `mv <Old File> <New File>` move (rename) [files, directories, ...]

``` console
root@Zold:~# ls
devops-folder  file1.txt
root@Zold:~# mv file1.txt file2.txt
root@Zold:~# ls
devops-folder  file2.txt

root@Zold:~# mv file2.txt devops-folder
root@Zold:~# ls devops-folder
file2.txt
```

[Next: User and Groups](./User%20and%20Groups.md)

[Prev: Linux File System](./Linux%20File%20System.md)
