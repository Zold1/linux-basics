# Linux File System

``` console
zold@Zold:~$ cd /
zold@Zold:/$ ls
bin   dev  home  lib    lib64   lost+found  mnt  proc  run   snap  sys  usr
boot  etc  init  lib32  libx32  media       opt  root  sbin  srv   tmp  var
```

* `/` root directory
* `/home` home directory for all non-root users
* `/root` home directory for all root users
* `/bin` user executable files ex: [cp, cat, ...]
* `/sbin` system binary files. These are executables used for system administration, only root users can use this
* `/lib` Contains shared library files that are required to boot the system from `/bin` and `/sbin`.
* `/usr` These are shareable, read-only files, including executable binaries and libraries, man files, and other types of documentation.  
  * `/usr/local` libraries and packages that you will download will be here ex: docker, java, ...etc
    * `/usr/local/bin` packages commands will be here
    * `/usr/local/lib` packages will be here
* `/opt` libraries and packages that you will download will be here too
  * what is the diffrent between `/opt` and `/usr/local`? `/opt` it be here packages that do not divide their components unlike `/usr/local`
* `/boot` contains the static bootloader and kernel executable and configuration files required to boot a Linux computer.
* `/etc` contains the local system configuration files for the host computer.
* `/dev` contains the device files for every hardware device attached to the system, ex: keyboard, mouse, camera ...etc
* `/var` Variable data files are stored here. This can include things like log files, MySQL, web server data files, email inboxes .... etc
  * for example `/var/cache` contains cache data from packages
* `/tmp` temporary directory. used by the operating system and many programs to store temporary files.
* `/media` and `/mnt` a temporary mountpoint for regular filesystems (as in not removable media) that can be used while the administrator is repairing or working on a filesystem.

[Next: Files and Directories](./Files%20and%20Directories.md)
[Prev: Linux Paths](./Linux%20Paths.md)
