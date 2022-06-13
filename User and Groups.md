# User and Groups

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

* ``
