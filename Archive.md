# Archive

we will use an archiving utility `tar` and `zip`

`tar` in itself just bundles files together (the result is called a tarball), while `zip` applies compression as well.

## Tar

* `tar -czvf <Tar Name> <Directory>` compressed file/directory

``` console
root@Zold:~# ls devops
ansible  aws  kubernetes  prometheus  terraform
root@Zold:~# tar -czvf devops-tools.tar.gz devops
devops/
devops/prometheus
devops/kubernetes
devops/terraform
devops/aws
devops/ansible
```

* `tar -xzvf <Tar File>`
* `tar -xzvf <Tar File> -C <Path>`

``` console
root@Zold:~# ls
devops-tools.tar.gz  tools
root@Zold:~# tar -xzvf devops-tools.tar.gz -C tools
devops/
devops/prometheus
devops/kubernetes
devops/terraform
devops/aws
devops/ansible
root@Zold:~# ls tools
devops
root@Zold:~# ls tools/devops
ansible  aws  kubernetes  prometheus  terraform
```

***

## Zip

First we need to install package `sudo apt install zip`

* `zip <Zip Name>` compressed file/empty directory
* `zip -r <Zip Name> <Directory>` compressed directory

``` console
root@Zold:~# ls devops
ansible  aws  kubernetes  prometheus  terraform
root@Zold:~# zip -r devops-package.zip devops
  adding: devops/ (stored 0%)
  adding: devops/prometheus (stored 0%)
  adding: devops/kubernetes (stored 0%)
  adding: devops/terraform (stored 0%)
  adding: devops/aws (stored 0%)
  adding: devops/ansible (stored 0%)
```

* `unzip <Zip File>` uncompressed zip file

``` console
root@Zold:~# rm -rf devops
root@Zold:~# ls
devops-package.zip
root@Zold:~# unzip devops-package.zip
Archive:  devops-package.zip
   creating: devops/
 extracting: devops/prometheus
 extracting: devops/kubernetes
 extracting: devops/terraform
 extracting: devops/aws
 extracting: devops/ansible
root@Zold:~# ls devops
ansible  aws  kubernetes  prometheus  terraform
```
