# Package Management

In few words, package management is a method of installing and maintaining (which includes updating and probably removing as well) software on the system.

## High and low-level package tools

In order to perform the task of package management effectively, you need to be aware that you will have two types of available utilities: low-level tools (which handle in the backend the actual installation, upgrade, and removal of package files), and high-level tools (which are in charge of ensuring that the tasks of dependency resolution and metadata searching -”data about the data”- are performed).

DISTRIBUTION           | LOW-LEVEL TOOL | HIGH-LEVEL TOOL
---------------------- | -------------- | ----------------
Debian and derivatives | dpkg           | apt-get / aptitude
CentOS                 | rpm            | yum

***

## YUM Command [CentOS]

* `yum update && yum upgrade` two commands you can use to keep all of your packages up to date in CentOS Linux distribution.
* `yum install <Package>` download & install package
  * `yum install <Package> -y` Automatically answer yes for all questions.
* `yum remove <Package>` Remove package from system
* `yum search <Package>` Search in yum repositoy
* `yum clean all` clean local cache

## RPM Command [CentOS]

* `curl <Url of Package RPM> -o <File Name on System>` Download Package
  * `curl https://rpmfind.net/linux/centos-stream/9-stream/BaseOS/x86_64/os/Packages/tree-1.8.0-6.el9.x86_64.rpm -o tree-1.8.0-6.el9.x86_64.rpm`
* `rpm -ivh tree-1.8.0-6.el9.x86_64.rpm` Install Package
* `rpm -e tree-1.8.0-6.el9.x86_64.rpm` Delete rpm package
* `rpm -qa` → All rpms
* `rpm -qa | grep tree` Get package from all packages

**Example** install nginx:

* `ls /etc/yum.repos.d/` → Files info of repo
* `yum install epel-release -y`
* `yum install nginx`

***

## APT Command [Debian]

* `apt update && apt upgrade` two commands you can use to keep all of your packages up to date in Debian or a Debian-based Linux distribution.
* `apt search <Package>` search package in all repository
* `apt install <Package>` install package
  * `apt install <Package1> <Package2>` install multi packages
* `apt remove <Package>` delete package
  * `apt purge <Package>` delete package with all files

## DPKG Command [Debian]

First download the package via `wget` or `curl`

Then `dpkg` commands:

* `dpkg -i <Package Name>` install package
* `dpkg -r <Package Name>` delete package

[Next: Vim Editor](./Vim%20Editor.md)

[Prev: File Permissions](./File%20Permissions.md)
