# SSH

## SSH Login

* Via Password
  * `ssh <username>@<ip>`
  
  ``` console
  zold@devops:~$ ssh root@150.89.14.90
  root@150.89.14.90's password: 
  root@ubuntu-s-1vcpu-1gb:~#
  ```

* Via Private Key
  * `ssh -i .ssh/id_rsa <username>@<ip>`
  
  ``` console
  zold@devops:~$ ssh -i .ssh/id_rsa root@159.89.14.94
  root@ubuntu-s-1vcpu-1gb:~#
  ```

***

## Generate SSH Key Pair

* `ssh-keygen -t rsa`

``` console
root@Zold:~# ssh-keygen -t rsa
Generating public/private rsa key pair.
Enter file in which to save the key (/root/.ssh/id_rsa):
Created directory '/root/.ssh'.
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /root/.ssh/id_rsa
Your public key has been saved in /root/.ssh/id_rsa.pub
The key fingerprint is:
SHA256:rf6GWQ3Tj0TRboUjsYF1NpEwbBnyQXIbe5dW56fpAkQ root@Zold
The key's randomart image is:
+---[RSA 3072]----+
|          E=&B=+o|
|         ..=*@=o=|
|          .+=o.=+|
|         oo o.++.|
|        S o= +o  |
|         ...o..  |
|        .+  . .  |
|       .o .  .   |
|        .o.      |
+----[SHA256]-----+
```

After that, two files will appear in the .ssh folder

* **id_rsa** This is private key
* **id_rsa.pub** This is public key

> .ssh folder is a hidden folder which has public, private key and known hosts

***

## Add public key to authorized keys of remote server

if you want to login to remote server without write ssh key pair every time, we need to add public key to remote server

* `cat .ssh/id_rsa.pub`
* Copy public key text

``` console
root@Zold:~# cat .ssh/id_rsa.pub
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQDA/PhoJnHM7G6Ulk2zn6UQ0IqZsWhpMl+sRXlvQ6SJvD0mxqq9H9JYuRir/a8r6BCX0PUz1t7XNzu9VpDgqfBLFNI+3cg63f9u19t83ib5PQtZ2BnDXRkBZkFE9oORT9gy4GUR6LscN+ioPBVV0WB00e9t4TglSVaCuFIDJNhIwoPefj8mtaUmSICQrC6TNXKqSdiSaQaHO91ee/qLWBZr4wLc+mJJS1SulswSSn48ZvoN9l9rC4JQdPFAdz5v7QRh9PZSsIQQX+3z2ZCOWUnFeiUdImWle9ucMfT+Ki6dWV43dJmqe3PkGg8KPDWqZwOrGx9vkayLDCu+Sh/gb9B5eVeAkvrkOKTQmpNsow3qI4XFwU1vqsRwCNcMcdI06Oym9vp4yDbMzU3+qcEHAaDtCFBp44DKDN4J6k9/1vuAUKQu9QZuev8CIB49fTRUiKqICoIj58TGkLOJjdQbsQ8w35eBvpHAIWaqJvwEDNuK6DIFe8M9+qOuyn+2p10U2qc= root@Zold
```

* Open .ssh/authorized_keys file in remote server

``` console
root@ubuntu-s-1vcpu-1gb:~# vim .ssh/authorized_keys
```

* then paste public key text in authorized_keys file

* try to login now without ssh private key

``` console
zold@devops:~$ ssh root@159.89.14.94
root@ubuntu-s-1vcpu-1gb:~# 
```

## Copy File to Remote Server

* `scp <file> <username>@<ip>:<path>`

``` console
zold@devops:~$ scp test.sh root@159.89.14.94:/root
```

* if you need to write ssh private key

``` console
zold@devops:~$ scp -i .ssh/id_rsa test.sh root@159.89.14.94:/root
```
