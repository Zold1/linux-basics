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

* `yum install httpd [-y]` Download  & Install Package
* `yum remove httpd` Remove package
* `yum search jdk` Search in yum
* `yum update` update all packages
* `yum clean all` clean local cache

## RPM Command [CentOS]

* `curl <url_of_package_rpm> -o <file_name>` Download Package
  * `curl https://rpmfind.net/linux/centos-stream/9-stream/BaseOS/x86_64/os/Packages/tree-1.8.0-6.el9.x86_64.rpm -o tree-1.8.0-6.el9.x86_64.rpm`
* `rpm -ivh tree-1.8.0-6.el9.x86_64.rpm` Install Package
* `tree /var/log` Try to use package
* `rpm -e tree-1.8.0-6.el9.x86_64.rpm` Delete rpm package
* `rpm -qa` → All rpms
* `rpm -qa | grep tree` Get package from all packages

**Example** install nginx:

* `ls /etc/yum.repos.d/` → Files info of repo
* `yum install epel-release -y`
* `yum install nginx`

***

## APT Command [Debian]

* `apt update` update packages
* `apt upgrade` upgrade packages
* `apt search tree` search package in all repository
* `apt install tree` install package
  * `apt install tree python` install multi packages
* `apt remove apache2` delete package
* `apt purge apache2` delete package with all files

## DPKG Command [Debian]

* `wget <lint_url>` download package via `wget`
* `dpkg -i <name_of_package>` install package
* `dpkg -r <name_of_package>` delete package

[Next: Vim Editor](./Vim%20Editor.md)

[Prev: File Permissions](./File%20Permissions.md)
