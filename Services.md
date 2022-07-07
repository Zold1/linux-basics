# Services

## Systemd vs Init

* **Systemd** is the new init system, starting with Fedora and now adopted in many distributions like RedHat, Suse and Centos. Historically, most of us have been using traditional SysV init scripts normally residing in /etc/rc.d/init.d/. These scripts invoke a daemon binary which will then fork a background process. Even though shell scripts are very flexible, tasks like supervising processes and parallelized execution ordering are difficult to implement. With the introduction of systemd’s new-style daemons it is easier to supervise and control them at runtime and it simplifies their implementation.

* The **systemctl** command is a very good initiative by the systemd team. It shows more detailed error messages and also runtime errors of services including start-up errors. systemd have introduced a new term called **cgroups** (control groups) which is basically groups of process that can be arranged in a hierarchy. With the original init system, determining which process does what and who it belongs to becomes increasingly difficult. With systemd, when processes spawn other processes these children are automatically made members of the parents cgroup thus avoiding confusions about inheritance.

![Systemd vs Init](./systemd-vs-sysVinit-cheatsheet-A4.jpg)

* **Note:** `sudo reboot` system reboot
  after this action the package will be inactive and you need to active it.

[Next: Processes](./Processes.md)

[Prev: Archive](./Archive.md)
