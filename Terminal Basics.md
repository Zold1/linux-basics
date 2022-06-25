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

``` console
zold@Zold:~$ cat /etc/os-release
NAME="Ubuntu"
VERSION="20.04.4 LTS (Focal Fossa)"
ID=ubuntu
ID_LIKE=debian
PRETTY_NAME="Ubuntu 20.04.4 LTS"
VERSION_ID="20.04"
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
VERSION_CODENAME=focal
UBUNTU_CODENAME=focal
```

* `lscpu` display information about the CPU architecture

``` console
zold@Zold:~$ lscpu
Architecture:                    x86_64
CPU op-mode(s):                  32-bit, 64-bit
Byte Order:                      Little Endian
Address sizes:                   48 bits physical, 48 bits virtual
CPU(s):                          4
On-line CPU(s) list:             0-3
Thread(s) per core:              2
Core(s) per socket:              2
Socket(s):                       1
Vendor ID:                       AuthenticAMD
CPU family:                      23
Model:                           24
Model name:                      AMD Ryzen 3 3200U with Radeon Vega Mobile Gfx
Stepping:                        1
CPU MHz:                         2595.043
BogoMIPS:                        5190.08
Virtualization:                  AMD-V
```

* `lsmem` list the ranges of available memory with their online status

``` console
zold@Zold:~$ lsmem
RANGE                                  SIZE  STATE REMOVABLE BLOCK
0x0000000000000000-0x000000006fffffff  1.8G online       yes  0-13

Memory block size:       128M
Total online memory:     1.8G
Total offline memory:      0B
```

* `free` Display amount of free and used memory in the system
* `free -m` Display the amount of memory in mebibytes.

``` console
zold@Zold:~$ free -m
              total        used        free      shared  buff/cache   available
Mem:           1626         222        1299           0         105        1279
Swap:          1024           0        1024
```

* `df` report file system disk space usage
* `df -h` print sizes in powers of 1024 (e.g., 1023M)

``` console
zold@Zold:~$ df -h
Filesystem      Size  Used Avail Use% Mounted on
none            814M  4.0K  814M   1% /mnt/wsl
drivers         119G   69G   50G  58% /usr/lib/wsl/drivers
none            814M     0  814M   0% /usr/lib/wsl/lib
/dev/sdc       1007G  7.5G  949G   1% /
none            814M   44K  814M   1% /mnt/wslg
tools           119G   69G   50G  58% /init
none            811M     0  811M   0% /dev
none            814M     0  814M   0% /run
none            814M     0  814M   0% /run/lock
none            814M     0  814M   0% /run/shm
none            814M     0  814M   0% /run/user
tmpfs           814M     0  814M   0% /sys/fs/cgroup
none            814M   80K  814M   1% /mnt/wslg/versions.txt
none            814M   80K  814M   1% /mnt/wslg/doc
drvfs           119G   69G   50G  58% /mnt/c
drvfs           1.9T  612G  1.3T  33% /mnt/d
```

* `uptime` tell how long the system has been running.

``` console
zold@Zold:~$ uptime
 10:00:15 up 10 min,  0 users,  load average: 0.00, 0.00, 0.00
```

* `sudo reboot` reboot system

***

## New command?

by `<Command> --help` or `<Command> -h` you can learn how to use any command you will see

**Example:** `chown` command, if you don't know how to use it, simply we will ask the terminal

``` console
zold@Zold:~$ chown --help
Usage: chown [OPTION]... [OWNER][:[GROUP]] FILE...
  or:  chown [OPTION]... --reference=RFILE FILE...
Change the owner and/or group of each FILE to OWNER and/or GROUP.
With --reference, change the owner and group of each FILE to those of RFILE.

  -c, --changes          like verbose but report only when a change is made
  -f, --silent, --quiet  suppress most error messages
  -v, --verbose          output a diagnostic for every file processed
      --dereference      affect the referent of each symbolic link (this is
                         the default), rather than the symbolic link itself
  -h, --no-dereference   affect symbolic links instead of any referenced file
                         (useful only on systems that can change the
                         ownership of a symlink)
      --from=CURRENT_OWNER:CURRENT_GROUP
                         change the owner and/or group of each file only if
                         its current owner and/or group match those specified
                         here.  Either may be omitted, in which case a match
                         is not required for the omitted attribute
      --no-preserve-root  do not treat '/' specially (the default)
      --preserve-root    fail to operate recursively on '/'
      --reference=RFILE  use RFILE's owner and group rather than
                         specifying OWNER:GROUP values
  -R, --recursive        operate on files and directories recursively
```

***

## Shortcuts

* **Ctrl + C** or **Ctrl + Z**: stop running task in terminal
* **Ctrl + R**: search terminal history
* **Ctrl + Shift + C**: copy text
* **Ctrl + Shift + V**: paste text

[Next: Linux Paths](./Linux%20Paths.md)

[Prev: Linux Introduction](./Linux%20Introduction.md)