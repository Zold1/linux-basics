# Linux Introduction

## Linux Origins

* 1984: The GNU Project and the Free Software Foundation
  * Creates open source version of Unix utilities
  * Creates the General Public License (GPL)
* 1991: Linus Torvalds
  * Creates open source, Unix-like kernel, released under the GPL
  * Ports some GNU utilities, solicits assistance online
* Today:
  * Linux kernel + GNU utilities = complete, open source, Unix-like operating system

***

## Linux Principles

* Everything is a file (including hardware)
* Small, single-purpose programs
* Ability to chain programs together to perform complex tasks
* Avoid captive user interfaces
* Configuration data stored in text

***

## Why Linux?

* OpenSource.
* Community support.
* Heavily customizable.
* Most Servers runs on Linux.
* DevOps most of the tools implements on Linux only.
* Automation
* Secure.

***

## Architecture of Linux

![Architecture](./linux_architecture.jpg)

***

## Diffrent Linux distros

### Popular Desktop Linux OS

* Ubuntu Linux
* Linux Mint
* Arch Linux
* Fedora
* Debian
* OpenSuse

### Popular Server Linux OS

* Red Hat Enterprise Linux
* Ubuntu Server
* Centos
* SUSE Enterprise Linux

### Most used Linux distros currently in IT industry

* RPM based:- RHEL & Centos
* Debian based :- Ubuntu Server

***

## Diffrence between RPM based and Debian based

From user’s point of view, there isn’t much difference in these tools. The RPM and DEB formats are both just archive files, with some metadata attached to them. They are both equally arcane, have hardcoded install paths and only differ in subtle details. DEB files are installation files for Debian based distributions. RPM files are installation files for Red Hat based distributions. Ubuntu is based on Debian’s package manage based on APT and DPKG. Red Hat, CentOS and Fedora are based on the old Red Hat Linux package management system, RPM.

### DEB or .deb (Debian based softwares)

DEB is the extension of the Debian software package format and the most often used name for such binary packages. DEB was developed by Bedian.
**Example:** Google chrome software
**Package name:** google-chrome-stable_current_amd64.deb
**Installation:** dpkg -i google-chrome-stable_current_amd64.deb

### RPM or .rpm (Red Hat based softwares.)

It is a package management system. The name RPM variously refers to the .rpm file format, files in this format, software packaged in such files, and the package manager itself. RPM was intended primarily for Linux distributions; the file format is the baseline package format of the Linux Standard Base. RPM was developed by Community & **Red Hat**.
**Example:** Google chrome software
**Package Name:** google-chrome-stable-57.0.2987.133-1.x86_64.rpm
**Installation:** rpm -ivh google-chrome-stable-57.0.2987.133-1.x86_64.rpm

**Note:** You will also encounter diffrent commands, packages and service names while using both kinds of distros
