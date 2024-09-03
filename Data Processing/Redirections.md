# Redirections

Redirection in Linux allows you to control where the output of a command goes and where the input for a command comes from. This is a fundamental aspect of shell scripting and command-line operations, enabling users to connect and manipulate data streams efficiently.

This page will cover the basics of standard input/output (I/O), redirection operators, and how to combine them with pipes to perform powerful data manipulations.

## Standard Input, Output, and Error

In Linux, commands use three standard data streams:

1. **Standard Input (`stdin`)**: The data stream that provides input to commands, usually from the keyboard. By default, it is file descriptor `0`.
   
2. **Standard Output (`stdout`)**: The data stream where a command sends its output, usually to the terminal screen. By default, it is file descriptor `1`.
   
3. **Standard Error (`stderr`)**: The data stream where a command sends its error messages, also usually to the terminal screen. By default, it is file descriptor `2`.

## Redirecting Standard Output (`>` and `>>`)

Redirecting output is one of the most common forms of redirection.

### Basic Redirection (`>`)

- **Redirect Output to a File**:

    ```bash
    command > file.txt
    ```

    This command sends the output to `file.txt`, overwriting it if the file exists.

### Append Output (`>>`)

- **Append Output to a File**:

    ```bash
    command >> file.txt
    ```

    This command appends the output to `file.txt` without overwriting the existing content.

## Redirecting Standard Input (`<`)

Redirecting input allows a command to take input from a file instead of the keyboard.

- **Use a File as Input**:

    ```bash
    command < file.txt
    ```

    This feeds the contents of `file.txt` as input to the command.

## Redirecting Standard Error (`2>`)

Sometimes you may want to separate error messages from normal output.

- **Redirect Errors to a File**:

    ```bash
    command 2> error.log
    ```

    This sends error messages to `error.log` instead of the terminal.

## Combining Standard Output and Error (`>&` and `2>&1`)

You can combine standard output and standard error into a single stream.

- **Redirect Both Output and Errors to the Same File**:

    ```bash
    command > file.txt 2>&1
    ```

    This sends both the standard output and standard error to `file.txt`.

- **Redirect Output and Error Separately**:

    ```bash
    command > output.txt 2> error.log
    ```

    This sends standard output to `output.txt` and errors to `error.log`.

## Using Pipes (`|`)

Pipes allow you to use the output of one command as the input for another.

- **Basic Pipe Usage**:

    ```bash
    command1 | command2
    ```

    This takes the output of `command1` and uses it as the input for `command2`.

### Example: Using Pipes with Redirection

- **Search for a Word in a File and Count Occurrences**:

    ```bash
    grep "word" file.txt | wc -l
    ```

    This command finds all occurrences of "word" in `file.txt` and then counts the number of matching lines.

## Here Documents (`<<`)

A here document is a type of redirection that allows you to pass a block of text as input to a command.

- **Using a Here Document**:

    ```bash
    command << EOF
    Line 1
    Line 2
    EOF
    ```

    Everything between the two `EOF` markers is treated as input to `command`.

## Here Strings (`<<<`)

A here string is similar to a here document but allows you to pass a single string as input.

- **Using a Here String**:

    ```bash
    command <<< "This is a single input string"
    ```

    This passes the string "This is a single input string" as input to `command`.

## Conclusion

Understanding redirections in Linux is key to mastering the command-line interface. By controlling where your commands take input from and where they send output, you can automate tasks, create complex workflows, and handle errors more effectively. Pipes, combined with redirections, provide even more powerful ways to manipulate data streams and command outputs.
