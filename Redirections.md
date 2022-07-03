# Redirections

Redirection is a process where we can copy the output of any command(s), file(s) into a new file. There are two ways of redirecting the output into a file.

## Overwrite using `>`

* `<Command> > <File>`

``` console
zold@Zold:~$ echo 'Welcome to linux.' > /tmp/sysinfo.log
zold@Zold:~$ cat /tmp/sysinfo.log
Welcome to linux.
```

***

## Append using `>>`

* `<Command> >> <File>`

``` console
zold@Zold:~$ free -m >> /tmp/sysinfo.log
zold@Zold:~$ cat /tmp/sysinfo.log
              total        used        free      shared  buff/cache   available
Mem:           1626         222        1260           2         143        1263
Swap:          1024           0        1024

zold@Zold:~$ df -h >> /tmp/sysinfo.log
zold@Zold:~$ cat /tmp/sysinfo.log
              total        used        free      shared  buff/cache   available
Mem:           1626         222        1260           2         143        1263
Swap:          1024           0        1024
Filesystem      Size  Used Avail Use% Mounted on
none            814M  4.0K  814M   1% /mnt/wsl
drivers         119G   63G   56G  53% /usr/lib/wsl/drivers
none            814M     0  814M   0% /usr/lib/wsl/lib
/dev/sdc       1007G  7.7G  949G   1% /
none            814M   44K  814M   1% /mnt/wslg
rootfs          811M  1.8M  809M   1% /init
none            811M     0  811M   0% /dev
none            814M     0  814M   0% /run
```

* `<Command> 2>> <File>` append error only if found
* `<Command> &>> <File>` append error or real output

``` console
zold@Zold:~$ uptime 2>> /tmp/sysinfo.log
 03:33:07 up 2 min,  0 users,  load average: 0.10, 0.05, 0.01

zold@Zold:~$ uptimer 2>> /tmp/sysinfo.log
zold@Zold:~$ cat /tmp/sysinfo.log

Command 'uptimer' not found, did you mean:

  command 'uptimed' from deb uptimed (1:0.4.2-1)
  command 'uptime' from deb procps (2:3.3.16-1ubuntu2.3)

Try: sudo apt install <deb name>
```

***

## Pipes

* `<Command 1> | <Command 2> | <Command 3> | .... | <Command N>`

``` console
zold@Zold:~$ grep -R apt linux-basics/* | grep install | tail -2 >> /tmp/sysinfo.log
zold@Zold:~$ cat /tmp/sysinfo.log
linux-basics/Redirections.md:Try: sudo apt install <deb name>
linux-basics/Vim Editor.md:* install vim `sudo apt install vim` or `sudo yum install vim -y`
```

[Next: Archive](./Archive.md)

[Prev: Filters](./Filters.md)
