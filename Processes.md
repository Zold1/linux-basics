# Processes

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
