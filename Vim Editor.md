# Vim Editor

This is command mode editor for files. Other editors in Linux are emacs, gedit
vi editor is most popular

* install vim `sudo apt install vim` or `sudo yum install vim -y`
* `vim script.sh` open file in vim

``` console
~
~
~
"script.sh" [New File]                                                         0,0-1         All 
```

There's **2 modes** in vim editor:

* **INSERT mode** you can write text in file
* **COMMAND mode** you can make actions in file (delete lines, replace, ... etc)

Key | Mode
--- | ----
i   | for switching to insert mode
ESC | for switching to command mode

* **Note:** When you open the vim editor, it will be in the command mode by default.

***

## Command mode commands

### Saving and Quitting

Command           | Explain
----------------- | -------
`:w myprogram.c`  | save the current changes to a file. If you don't specify a name, changes will be saved to the current file.
`:q`              | quits Vim. If you have unsaved changes, you will be asked whether or not you'd like to save your changes before quitting.
`:q!`             | quit without saving unsaved changes.
`:wq`             | save and quit.

## Navigating A File

Command           | Explain
----------------- | -------
`gg`              | jump to the first line in file.
`G`               | jump to last line in file
`12G`             | Go to line 12 (change number to anything)

### Searching/Replacing

Command           | Explain
----------------- | -------
`/foo`            | search the file for "foo". This will highlight all matches in the editor for you to see.
`n`               | move the cursor to the next search match
`N`               | move the cursor to the previous search match
`:noh`            | to turn off highlighting until the next search. Alternatively, search for a bogus string, like /thiswordwontexist
`:%s/old/new/`    | replace "old" word with "new" word
`:%s/old/new/gi`  | replace "old" word with "new" word even capital words!

### Editing Text

Command             | Explain
------------------- | -------
`dd` or `:d`        | deletes the current line
`d10`               | deletes 10 lines (change number to anything)
`yy` or `:y` or `Y` | (cut) the current line
`p`                 | Paste the text you yanked or deleted
`x`                 | delete the character underneath the cursor

### Entering INSERT Mode

Command           | Explain
----------------- | -------
`i`               | enter INSERT mode before the cursor
`I`               | enter INSERT mode at the start of the current line
`a`               | enter INSERT mode appending after the cursor
`A`               | enter INSERT mode appending to the end of the current line
`0`               | enter INSERT mode starting from the beginning of the file

### Undo/Redo

Command           | Explain
----------------- | -------
`u`               | undo the last action
`U`               | undo all recent changes made to the current line
ctrl-r            | redo

### Others

Command           | Explain
----------------- | -------
`:se nu`          | to number the lines
`:e <Other File>` | to edit a different file

**Note:** For learn every thing about vim write `vimtutor` in console and read the documation

[Next: Filters](./Filters.md)

[Prev: Package Management](./Package%20Management.md)