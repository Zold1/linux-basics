# Processes

## Show process

* `top` display Linux processes

``` console
top - 15:27:17 up 4 min,  0 users,  load average: 0.00, 0.00, 0.00
Tasks:   5 total,   1 running,   4 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.0 us,  0.0 sy,  0.0 ni,100.0 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
MiB Mem :   1626.9 total,   1279.0 free,    223.1 used,    124.8 buff/cache
MiB Swap:   1024.0 total,   1024.0 free,      0.0 used.   1268.0 avail Mem

  PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND
    1 root      20   0    2940   1732   1392 S   0.7   0.1   0:02.45 init
   96 root      20   0    2940    416      0 S   0.0   0.0   0:00.00 init
   97 root      20   0    2956    416      0 S   0.0   0.0   0:00.02 init
   98 zold      20   0   10172   5292   3436 S   0.0   0.3   0:00.10 bash
  145 zold      20   0   10872   3664   3148 R   0.0   0.2   0:00.02 top
```

* `ps aux` report a snapshot of the current processes.

``` console
zold@Zold:~$ ps aux
USER       PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root         1  0.2  0.0   2464  1652 ?        Sl   10:21   0:04 /init
root        68  0.0  0.0   2464   452 ?        Ss   10:22   0:00 /init
root        69  0.0  0.0   2464   452 ?        S    10:22   0:00 /init
zold        70  0.0  0.2  10040  4984 pts/0    Ss   10:22   0:00 -bash
zold       566  0.0  0.1  10616  3300 pts/0    R+   10:47   0:00 ps aux
```

* `ps` report a snapshot of the current processes.

To see every process on the system using standard syntax:

* `ps -e`
* `ps -ef`
* `ps -eF`

To see every process on the system using BSD syntax:

* `ps ax`
* `ps aux`

``` console
zold@Zold:~$ ps aux
USER       PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root         1  0.7  0.0   2400  1436 ?        Sl   15:22   0:04 /init
root        96  0.0  0.0   2940   416 ?        Ss   15:24   0:00 /init
root        97  0.0  0.0   2956   416 ?        R    15:24   0:00 /init
zold        98  0.0  0.3  10172  5292 pts/0    Ss   15:24   0:00 -bash
zold       434  0.0  0.2  10616  3348 pts/0    R+   15:32   0:00 ps aux
```

***

## kill process

First we need to get process id

``` console
zold@Zold:~$ ps -ef | grep httpd
zold        47     9  0 15:39 pts/0    00:00:00 grep --color=auto httpd
```

Process ID: **47**

Now killing it

* `kill 47` kill process 47
* `kill -9 47` kill process 47 with child processes

``` console
zold@Zold:~$ kill 47
zold@Zold:~$ ps -ef | grep httpd
zold@Zold:~$
```

***

## kill multi processes

* `kill 3021 3022 3023` kill multi
* `ps -ef | grep httpd | grep -v ‘auto’ | aws ‘{print $2}’`
* `ps -ef | grep httpd | grep -v ‘auto’ | aws ‘{print $2}’ | xargs kill -9`

[Next: Networking Commands](./Networking%20Commands.md)

[Prev: Services](./Services.md)
