# Terminal Basics

## Terminal line explain

``` console
zold@ubuntu-os: ~$
```

* `zold` Username who is logged in to console
* `ubuntu-os` name of computer or remote server
* `~` home directory and it will, and it will change according to the directory it is in

``` console
zold@ubuntu-os:~$ pwd
/home/zold
zold@ubuntu-os:/usr/local$ pwd
/usr/local
```

* `$` indicates that the user is a normal user, if the user is root it will be `#`

``` console
zold@ubuntu-os:~$ su -
root@ubuntu-os:~#
```

***

## Basic Commands

* `echo Welcome to linux.` for print something

``` console
root@Zold:~# echo Welcome to linux.
Welcome to linux.
```

* `clear` clear terminal

* `history` all commands you executed it in terminal
* `history 10` last 10 commands you executed it in terminal, you can **change the number** as you like

***

## System Commands

* `uname` get kernel name
* `uname -a` get name and information about current kernel

``` console
root@Zold:~# uname
Linux
root@Zold:~# uname -a
Linux Zold 5.10.102.1-microsoft-standard-WSL2 #1 SMP Wed Mar 2 00:30:59 UTC 2022 x86_64 x86_64 x86_64 GNU/Linux
```

* `cat /etc/os-release` Operating system identification
* `lscpu` 
* `lsmem`
* `free -m`
* `df -h`
* `uptime`