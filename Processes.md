# Processes

## Show process

* `top`
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

* `ps -ef`

## kill process

* `ps -ef | grep httpd | grep -v ‘auto’`
* `kill 2995` to kill process
* `kill -9 3020` child process still working

## kill multi processes

* `kill 3021 3022 3023` kill multi
* `ps -ef | grep httpd | grep -v ‘auto’ | aws ‘{print $2}’`
* `ps -ef | grep httpd | grep -v ‘auto’ | aws ‘{print $2}’ | xargs kill -9`

[Next: Networking Commands](./Networking%20Commands.md)

[Prev: Services](./Services.md)