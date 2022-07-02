# Package Management

In few words, package management is a method of installing and maintaining (which includes updating and probably removing as well) software on the system.

## High and low-level package tools

In order to perform the task of package management effectively, you need to be aware that you will have two types of available utilities: low-level tools (which handle in the backend the actual installation, upgrade, and removal of package files), and high-level tools (which are in charge of ensuring that the tasks of dependency resolution and metadata searching -”data about the data”- are performed).

DISTRIBUTION           | LOW-LEVEL TOOL | HIGH-LEVEL TOOL
---------------------- | -------------- | ----------------
Debian and derivatives | dpkg           | apt-get / aptitude
CentOS                 | rpm            | yum

***

## CentOS Distribution

### yum command

* `yum update && yum upgrade` two commands you can use to keep all of your packages up to date in CentOS Linux distribution.
* `yum install <Package>` download & install package
  * `yum install <Package> -y` automatically answer yes for all questions.
* `yum remove <Package>` remove installed package from system
* `yum search <Package>` search in yum repositoy
* `yum clean all` clean local cache

**Example** install nginx:

* `ls /etc/yum.repos.d/` → Files info of repo
* `yum install epel-release -y`
* `yum install nginx`

### rpm command

First download the package via `wget` or `curl`

Then `rpm` commands:

* `rpm -ivh <Package Name>` install package
* `rpm -e <Package Name>` remove installed package
* `rpm -qa` all rpm packages

***

## Debian Distribution

### apt command

* `apt update && apt upgrade` two commands you can use to keep all of your packages up to date in Debian or a Debian-based Linux distribution.
* `apt search <Package>` search package in all repository
* `apt install <Package>` install package
  * `apt install <Package1> <Package2>` install multi packages
* `apt remove <Package>` remove installed package
  * `apt purge <Package>` remove installed package with all files

### dpkg command

First download the package via `wget` or `curl`

Then `dpkg` commands:

* `dpkg -i <Package Name>` install package
* `dpkg -r <Package Name>` remove installed package

[Next: Vim Editor](./Vim%20Editor.md)

[Prev: File Permissions](./File%20Permissions.md)
