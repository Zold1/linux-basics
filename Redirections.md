# Redirections

Redirection is a process where we can copy the output of any command(s), file(s) into a new file. There are two ways of redirecting the output into a file.

## Overwrite using `>`

* `echo ‘Welcome to linux.’ > /tmp/sysinfo.log`

## Append using `>>`

* `free -m >> /tmp/sysinfo.log`
* `df -h >> /tmp/sysinfo.log`
* `uptime >> /tmp/sysinfo.log`
* `uptimer 2>> /tmp/sysinfo.log` → To append error only if found “2>>”
* `free -m &>> /tmp/sysinfo.log` → To append error or real output “&>>”

## Command | Command [pipe]

* `grep -R boot * | tail -2`
* `grep -R boot * | tail -2 | grep fun`
* `grep -R boot * | tail -2 | grep fun >> /tmp/sysinfo.log`
