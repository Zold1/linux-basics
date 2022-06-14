# Best Practices

## Security Best Practices for Linux Servers

* Use SSH instead of password for logging into servers
* If somehow that’s not possible, use strong and unique passwords:
  * Same password should never be used for multiple users or software systems
  * Configure expiration, to update the passwords regularly
  * Use password manager for two-factor authentication, password generation, cloud password storage etc.
* Update your software regularly or enable automatic updates
* Avoid unnecessary software, as each new software can expose the server to potential problems
* Regularly backup your data. The application “rsync” is a popular option in Linux

***

## Users & Permissions

* Only use the root account for systems administration. Login with normal user and su to root
* Remove or lock user accounts that are no longer needed
* Make sure that passwords on active accounts are changed regularly
* Lock User Accounts after a number of unsuccessful login attempts

***

## Networking

* Always have a Firewall
* Restrict network access as much as possible
  * Ports, which you don’t need should be closed

***

## SSH

* SSH, like all network services, should be disabled if not needed
* Disable root logins via SSH
  * Can be configured here: `/etc/ssh/sshd_config`
  * Login with a normal user and su to root