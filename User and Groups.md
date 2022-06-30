# User and Groups

## Important Points

* Users and groups are used to control access to files and resources
* Users login to the system by supplying their username and password
* Every file on the system is owned by a user and associated with a group
* Every process has an owner and group affilition, and can only access the resources it's owner or group can access
* Every user of the system is assigned a unique user ID number (the UID)
* Users name and UID are stored in **/etc/passwd**
* User's password is stored in **/etc/shadow**
* Users are assigned a **home directory** and a program that is run when they login (**Usually a shell**)
* Users cannot read, write or execute each other's files without permission.

linux there are 3 types of users

* Super user or root user
  The most powerful user - It's the administrator user
* System user
  Created by the software or applications
* Normal user
  Created by root user
  Only root user has the permission to create or remove a user

Type    | Example          | User ID       | Group ID      | Home Dir         | Shell
------- | ---------------- | ------------- | ------------- | ---------------- | -----------
Root    | root             | 0             | 0             | /root            | /bin/bash
Regular | zold, vagrant    | 1000 to 60000 | 1000 to 60000 | /home/{username} | /bin/bash
Service | ftp, ssh, apache | 1 to 999      | 1 to 999      | /var/ftp etc     | /sbin/nologin

## Show All Users

`cat /etc/passwd` → show all users

``` console
root@Zold:~# cat /etc/passwd
root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
sys:x:3:3:sys:/dev:/usr/sbin/nologin
sync:x:4:65534:sync:/bin:/bin/sync
games:x:5:60:games:/usr/games:/usr/sbin/nologin
man:x:6:12:man:/var/cache/man:/usr/sbin/nologin
lp:x:7:7:lp:/var/spool/lpd:/usr/sbin/nologin
mail:x:8:8:mail:/var/mail:/usr/sbin/nologin
news:x:9:9:news:/var/spool/news:/usr/sbin/nologin
```

Explaining syntax, will use the first account to explain

* `root` username
* `x` encrypted password stored in /etc/shadow file
* `0` user id
* `0` group id
* `root` comment
* `/root` home directory
* `/bin/bash` shell

***

## User Control Commands

* `whoami` print effective userid
* `w` show who is logged on and what they are doing.

``` console
root@Zold:~# whoami
root

root@Zold:~# w
 13:38:04 up 56 min,  0 users,  load average: 0.00, 0.11, 0.07
USER     TTY      FROM             LOGIN@   IDLE   JCPU   PCPU WHAT
```

* `id` print real and effective user and group IDs
* `id <Username>` Select a specific account username

``` console
root@Zold:~# id
uid=0(root) gid=0(root) groups=0(root)

root@Zold:~# id zold
uid=1000(zold) gid=1000(zold) groups=1000(zold),27(sudo),29(audio),30(dip),44(video),46(plugdev),117(netdev),1001(docker)
```

* `useradd <Username>` and `adduser <Username>` add a new user to your current Linux machine

`useradd` vs `adduser` ? `useradd` is native binary compiled with the system. But, `adduser` is a perl script which uses `useradd` binary in back-end. also `adduser` is more user friendly and interactive than its back-end `useradd`. There's no difference in features provided.

``` console
root@Zold:~# adduser ashraf
Adding user `ashraf' ...
Adding new group `ashraf' (1004) ...
Adding new user `ashraf' (1003) with group `ashraf' ...
Creating home directory `/home/ashraf' ...
Copying files from `/etc/skel' ...
New password:
Retype new password:
passwd: password updated successfully
Changing the user information for ashraf
Enter the new value, or press ENTER for the default
        Full Name []: Ashraf Osaama
        Room Number []: 10
        Work Phone []: 01039382745
        Home Phone []: 01139827388
        Other []:
Is the information correct? [Y/n] y
root@Zold:~# su - ashraf
ashraf@Zold:~$
```

* `userdel <Username>` delete a user account and related files
* `userdel -r <Username>` Files in the user's home directory will be removed along with the home directory itself and the user's mail spool

``` console
zold@Zold:~$ sudo userdel -r amira
zold@Zold:~$ su - amira
su: user amira does not exist
```

* `passwd` Change password of effective user
* `passwd <Username>` Change password of specific user

``` console
zold@Zold:~$ sudo passwd salah
New password:
Retype new password:
passwd: password updated successfully
```

* `su - <username>` switch user which login to machine
* `su -` or `sudo -i` login to root user
* `exit` logout

``` console
zold@Zold:~$ su - ahmed
Password:
ahmed@Zold:~$ exit
logout
zold@Zold:~$
```

***

## Group Control Commands

* `cat /etc/group` get all groups
* `groups` Groups of effective user
* `groups <Username>` Groups of specific user

``` console
zold@Zold:~$ cat /etc/group
root:x:0:
daemon:x:1:
bin:x:2:
sys:x:3:
adm:x:4:syslog,zold
tty:x:5:syslog
disk:x:6:
lp:x:7:
mail:x:8:
news:x:9:

zold@Zold:~$ groups
zold adm dialout cdrom floppy sudo audio dip video plugdev netdev docker
```

* `groupadd <Username>` and `addgroup <Username>` create a new group

On most distribution `adduser` and `addgroup` are interactive 'convenience' wrappers around the commands `useradd` and `groupadd`.

* `groupdel <Username>` or `delgroup <Username>` delete a group

``` console
zold@Zold:~$ sudo addgroup devops
[sudo] password for zold:
Adding group `devops' (GID 1004) ...
Done.

zold@Zold:~$ sudo delgroup devops
Removing group `devops' ...
Done.
```

***

## User with Group Commands

* `usermod [OPTIONS] <group> <username>` modify a user account
  * `usermod -g devops tom` Make 'devops' primary group of user 'tom'
  * `usermod -aG admins aws` Add 'aws' user to 'admin' group
* `gpasswd -d <username> <group>` Remove user from group

``` console
zold@Zold:~$ sudo usermod -aG devops zold
zold@Zold:~$ sudo gpasswd -d zold devops
Removing user zold from group devops
```

***

## Sudo

allows a permitted user to execute a command as the superuser or another user, as specified by the security policy

``` console
zold@Zold:~$ adduser salah
adduser: Only root may add a user or group to the system.

zold@Zold:~$ sudo adduser salah
[sudo] password for zold:
Adding user `salah' ...
Adding new group `salah' (1002) ...
Adding new user `salah' (1001) with group `salah' ...
Creating home directory `/home/salah' ...
Copying files from `/etc/skel' ...
New password:
Retype new password:
passwd: password updated successfully
Changing the user information for salah
Enter the new value, or press ENTER for the default
        Full Name []:
        Room Number []:
        Work Phone []:
        Home Phone []:
        Other []:
Is the information correct? [Y/n]
```

[Next: File Permissions](./File%20Permissions.md)

[Prev: Files and Directories](./Files%20and%20Directories.md)
