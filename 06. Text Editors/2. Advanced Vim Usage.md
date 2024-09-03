# Advanced Vim Usage

Once you're comfortable with the basics of Vim, it's time to explore its more advanced features. These capabilities can help you maximize productivity, automate repetitive tasks, and manage large projects more efficiently.

## Custom Key Mappings

Vim allows you to create custom key mappings, which can be added to your `.vimrc` file. This helps streamline your workflow by assigning shortcuts to frequently used commands.

### Creating Key Mappings

- **Normal Mode Mapping**: Use `nnoremap` for custom mappings in Normal Mode.
  
    ```vim
    nnoremap <leader>w :w<CR>
    ```
  
    This maps `<leader>w` (commonly `\w`) to save the file.

- **Insert Mode Mapping**: Use `inoremap` for Insert Mode mappings.
  
    ```vim
    inoremap jj <Esc>
    ```
  
    This maps `jj` to exit Insert Mode, which can be quicker than reaching for the `Esc` key.

- **Visual Mode Mapping**: Use `vnoremap` for Visual Mode mappings.
  
    ```vim
    vnoremap <leader>y "+y
    ```
  
    This maps `<leader>y` to yank (copy) text to the system clipboard.

### Leader Key

The `<leader>` key is a customizable prefix key that you can set in your `.vimrc`. It's commonly used to create shortcuts.

```vim
let mapleader = ","
```

In this example, the leader key is set to `,`, allowing for custom mappings like `,w` to save the file.

## Using Registers for Advanced Copy and Paste

Registers in Vim allow you to store and access multiple pieces of text. By default, Vim uses the unnamed register (`"`), but you can specify others.

### Accessing Registers

- **Yanking into a Register**: To yank text into a specific register, use `"` followed by the register name and the yank command.
  
    ```vim
    "ayw
    ```
  
    This yanks a word into register `a`.

- **Pasting from a Register**: To paste from a specific register, use `"` followed by the register name and the paste command.
  
    ```vim
    "ap
    ```
  
    This pastes the contents of register `a`.

### Useful Registers

- **System Clipboard Register (`+`)**: Use the `+` register to copy to and paste from the system clipboard.
  
    ```vim
    "+y
    ```

- **Small Delete Register (`-`)**: Stores small deletions, like a single word, without overwriting the unnamed register.

## Recording and Using Macros

Macros in Vim allow you to record a series of commands and play them back, which is useful for repetitive tasks.

### Recording a Macro

1. Press `q` followed by a letter (e.g., `a`) to start recording.
2. Execute the commands you want to record.
3. Press `q` again to stop recording.

### Playing Back a Macro

- To play back a macro stored in register `a`, press `@a`.
- To repeat the last macro, press `@@`.

### Advanced Macro Usage

- **Execute a Macro Multiple Times**: Prefix the macro command with a number to repeat it.
  
    ```vim
    5@a
    ```
  
    This repeats the macro in register `a` five times.

- **Edit a Macro**: Macros are stored in registers, so you can yank, edit, and paste them just like any other text.

## Working with Tabs, Buffers, and Windows

Vim's powerful handling of tabs, buffers, and split windows makes it an excellent tool for multitasking and managing complex projects.

### Managing Buffers

- **Open a New Buffer**: Use `:e filename` to open a new buffer.
- **Switch Between Buffers**: Use `:bnext` (or `:bn`) and `:bprev` (or `:bp`) to navigate through buffers.
- **List All Buffers**: Use `:ls` or `:buffers` to see a list of open buffers.

### Using Tabs

- **Open a File in a New Tab**: Use `:tabnew filename`.
- **Switch Between Tabs**: Use `gt` to move to the next tab and `gT` to move to the previous tab.
- **Close a Tab**: Use `:tabclose`.

### Split Windows

- **Horizontal Split**: Use `:split filename` or `:sp filename`.
- **Vertical Split**: Use `:vsplit filename` or `:vsp filename`.
- **Switch Between Windows**: Use `Ctrl+w` followed by a direction (`h`, `j`, `k`, `l`) to move between split windows.
- **Resize Windows**: Use `Ctrl+w` followed by `+` or `-` to increase or decrease the window height, or `>` and `<` to adjust width.

## Advanced Search and Replace

Vim's search and replace capabilities are powerful, particularly when combined with regular expressions.

### Basic Replace

To replace all instances of `foo` with `bar` in the current file:

```vim
:%s/foo/bar/g
```

### Conditional Replace

To replace only if `foo` is found at the start of a line:

```vim
:%s/^foo/bar/g
```

### Interactive Replace

To confirm each replacement interactively:

```vim
:%s/foo/bar/gc
```

- `c`: Confirm each substitution.

## Scripting and Automation

Vim supports scripting using Vimscript, its built-in scripting language, which allows for automation of complex tasks.

### Writing Simple Vimscript

Here’s a basic example of a Vimscript function:

```vim
function! ToggleNumber()
    if &number
        set nonumber
    else
        set number
    endif
endfunction
```

- **Call the Function**: You can call this function by adding a custom key mapping:

    ```vim
    nnoremap <leader>n :call ToggleNumber()<CR>
    ```

### Automating Tasks with Autocommands

Autocommands automatically execute commands in response to events, like opening a file or changing a buffer.

Example: Automatically set the file type for `.txt` files:

```vim
autocmd BufNewFile,BufRead *.txt set filetype=markdown
```

- **Events**: `BufNewFile` and `BufRead` trigger the command when a new file is created or an existing one is read.
- **Action**: The file type is set to markdown.

## Plugins and Extending Vim

Vim can be extended with plugins, enabling features like code completion, file management, and syntax highlighting.

### Popular Plugin Managers

- **Vundle**: Easy to use and well-documented.
- **Pathogen**: Simplifies the process of installing plugins.
- **vim-plug**: A fast and minimalist plugin manager.

### Must-Have Plugins

- **NERDTree**: A file explorer tree for navigating the filesystem.
- **CtrlP**: A fuzzy file finder that makes navigating large projects easier.
- **Surround**: Provides mappings to easily delete, change, and add surroundings like parentheses, quotes, etc.
- **Fugitive**: A Git wrapper that integrates Git commands into Vim.

### Installing Plugins with vim-plug

Add this to your `.vimrc`:

```vim
call plug#begin('~/.vim/plugged')

Plug 'scrooloose/nerdtree'
Plug 'tpope/vim-fugitive'
Plug 'ctrlpvim/ctrlp.vim'

call plug#end()
```

Install the plugins:

```bash
vim +PlugInstall +qall
```

## Conclusion

Mastering advanced Vim features transforms it from a simple text editor into a powerful, customizable tool that can adapt to virtually any workflow. With these advanced techniques, you can harness the full potential of Vim, making your editing process more efficient and enjoyable.
