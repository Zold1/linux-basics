# Filters

## Reading File

* `cat <File>` concatenate files and print on the standard output

``` console
root@Zold:~# cat myfile.script
Hello World!
This is text in file.
For testing.
```

* `more` read large file page by page
* `b` go back one page
* **SPACE** go to the next page in accordance with the terminal’s size

``` console
root@Zold:~# more index.html
```

* `less` read file line by line

``` console
root@Zold:~# less script.sh
```

## Search in File

* `grep <word> <file>` Search for a word in a file
* `grep -i <word> <file>` Search for a capital word in a file
* `grep -i <word> *` Search in all files in working path
* `grep -iR <word> *` Search in all files in working path and all directories with their files
* `free -m | grep Mem` Search for a word from another command output
* `grep "sudo chmod"` search for a sentence
* `grep -v 'word'`

## Head & Tail

* `head <file>` Print first 10 lines of each FILE
* `head -3 <file>` Print 3 lines only
* `tail <file>` Print last 10 lines of each FILE
* `tail -4 <file>` Print 4 lines only
* `tail -f <file>` watch file

## Cut

* `cut -d <word> -f<index> <file>` → هيمسك التكست سطر سطر كل سطر هيعمله split بالكلمه اللى تحددها بعد كدا هيطبع الاندكس اللى انت محدده برضو
  * `cut -d :x: -f2 /etc/passwd`

## Replace

* `sed ‘s/<old>/<new>/gi’ <file>` replace word in a file
* `sed -i ‘s/<old>/<new>/gi’ <file>` replace word without printing in console
* `sed -i ‘s/root/boot/gi’ testdir/*` replace word in all files in directory

[Next: Redirections](./Redirections.md)

[Prev: Vim Editor](./Vim%20Editor.md)
