# Filters

## Reading File

* `cat <File>` concatenate files and print on the standard output

``` console
root@Zold:~# cat myfile.script
Hello World!
This is text in file.
For testing.
```

* `less` read large file page by page or line by line
* `b` go back one page
* **SPACE** go to the next page in accordance with the terminal’s size

***

## Search in File

* `grep <word> <file>` search for a word in a file
* `grep -i <word> <file>` search for a capital word in a file
* `grep -i <word> *` Search in all files in working path
* `grep -iR <word> *` Search in all files in working path and all directories with their files
* `grep -v 'word'` Invert the sense of matching, to select non-matching lines.
* `free -m | grep Mem` Search for a word from another command output

``` console
root@Zold:~# free -m
              total        used        free      shared  buff/cache   available
Mem:           1626         223        1279           2         123        1268
Swap:          1024           0        1024

root@Zold:~# free -m | grep Mem
Mem:           1626         223        1279           2         123        1268

root@Zold:~# free -m | grep -v Mem
              total        used        free      shared  buff/cache   available
Swap:          1024           0        1024
```

***

## Head & Tail of File

* `head <file>` Print first 10 lines of each FILE
  * `head -3 <file>` Print 3 lines only **change number to anything**
* `tail <file>` Print last 10 lines of each FILE
  * `tail -4 <file>` Print 4 lines only **change number to anything**
  * `tail -f <file>` output appended data as the file grows

***

## Split

* `cut -d <Delimiter> -f <Index> <File>` remove sections from each line of file

``` console
root@Zold:~# cut -d : -f1 /etc/passwd
root
daemon
bin
sys
sync
games
man
lp
mail
news
uucp
proxy
```

***

## Replace

* `sed 's/old/new/gi' <file>` replace "old" word with "new" word in a file
* `sed -i 's/old/new/gi' <file>` replace "old" word with "new" word and edit file in place
* `sed -i 's/root/boot/gi' testdir/*` replace word in all files in directory

[Next: Redirections](./Redirections.md)

[Prev: Vim Editor](./Vim%20Editor.md)
