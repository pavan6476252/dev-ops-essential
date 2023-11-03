# Linux practice

# UNIT 1

## Unix: A Brief History

Unix is an operating system that was developed in the late 1960s and early 1970s at AT&T's Bell Labs. It is known for its stability, flexibility, and powerful command-line interface. Unix has significantly influenced the development of modern operating systems, including Linux.

## What is Unix?

Unix is an operating system that provides a multi-user, multitasking environment. It's designed to be portable, efficient, and flexible. Unix systems are known for their command-line interface and are used for various tasks, from file management to programming.

## Unix Components

1. **Kernel**: The core of the operating system that manages hardware resources.

2. **Shell**: The user interface for interacting with the system. Common shells include Bash, Zsh, and Csh.

3. **Filesystem**: The hierarchical structure for organizing files and directories.

4. **Utilities**: A set of commands and programs for performing various tasks.

## Using Unix: Basic Commands

### Basic Navigation:

- **`pwd`** (Print Working Directory): Shows the current directory.
  ```shell
  $ pwd
  /home/user
  ```

- **`ls`** (List): Lists files and directories in the current directory.
  ```shell
  $ ls
  file1.txt  directory1  file2.txt
  ```

- **`cd`** (Change Directory): Moves to a different directory.
  ```shell
  $ cd directory1
  ```

### File Operations:

- **`touch`**: Creates an empty file.
  ```shell
  $ touch newfile.txt
  ```

- **`cp`** (Copy): Copies files or directories.
  ```shell
  $ cp file1.txt file_copy.txt
  ```

- **`mv`** (Move): Renames or moves files.
  ```shell
  $ mv file2.txt new_location/
  ```

- **`rm`** (Remove): Deletes files or directories.
  ```shell
  $ rm file1.txt
  ```

### Viewing File Contents:

- **`cat`** (Concatenate): Displays file contents.
  ```shell
  $ cat file.txt
  ```

- **`less`**: View file contents page by page.
  ```shell
  $ less largefile.txt
  ```

### Command Substitution:

- You can use command substitution to embed the output of one command within another. It is done using backticks (\`) or `$()`.
  ```shell
  $ echo "Today is $(date)"
  ```

### Running Multiple Commands:

- Use semicolons to run multiple commands in a single line.
  ```shell
  $ command1 ; command2
  ```

- Use the `&&` operator to run the second command only if the first command succeeds.
  ```shell
  $ command1 && command2
  ```

- Use the `||` operator to run the second command only if the first command fails.
  ```shell
  $ command1 || command2
  ```


# UNIT 1 --- PART 2
 
 
### The File System - The Basics of Files

The file system is an integral part of an operating system, responsible for managing files and directories on storage devices like hard drives and SSDs. In Unix-like systems, it follows a hierarchical structure where files and directories are organized. Here are the key components and concepts:

#### What's in a File?

A file is a collection of data that can represent various types of information, such as text, programs, images, or configuration settings. In Unix, everything is considered a file, including hardware devices and directories.

#### Directories and File Names

Directories are special files that contain a list of other files and directories. They organize files into a structured hierarchy. File names are used to identify and access files within directories. These names can include letters, numbers, and symbols.

### Permissions

File and directory permissions control who can access, read, write, and execute files or directories. In Unix systems, there are three categories of users: owner, group, and others, each with its permissions.

- Read (r): Allows viewing the content of a file or listing the contents of a directory.
- Write (w): Grants the ability to modify the file or add/remove files in a directory.
- Execute (x): Permits running a file as a program or accessing files within a directory.

Permission combinations are expressed as a three-character string for each category (e.g., "rw-" for read and write, "--x" for execute). They can be modified using the `chmod` command.

### Inodes

An inode is a data structure that stores information about a file or directory, such as its location on the storage device, permissions, size, modification timestamps, and data block pointers. Inodes are used to manage files efficiently. Each file or directory is associated with an inode, and the file system keeps track of these inodes in an inode table.

### The Directory Hierarchy

The directory hierarchy is a tree-like structure that organizes files and directories into a logical order. It starts with the root directory ("/") and branches out into subdirectories. Directories can contain files and other subdirectories, creating a nested structure.

Here's a simple example of the directory hierarchy:
```
/
|-- home
|   |-- user1
|   |   |-- Documents
|   |   |-- Music
|   |-- user2
|   |-- ...
|-- var
|   |-- log
|   |-- ...
|-- bin
|-- usr
|-- ...
```

In this example, the root directory ("/") is at the top, and it contains subdirectories like "home," "var," "bin," and "usr." The "home" directory contains user-specific directories ("user1," "user2," etc.), and each user directory can have its files and subdirectories.

The directory hierarchy plays a crucial role in organizing and locating files and directories efficiently. Users can navigate through the hierarchy using commands like `cd` (change directory), `ls` (list files), and `pwd` (print working directory).
 

# GREP  Command
 
 
# `grep` Command

`grep` is a powerful and widely used command-line utility in Unix-like operating systems for searching and matching text patterns within files. It stands for "Global Regular Expression Print." This tool allows you to search for specific text patterns in one or more files and then print the lines that match those patterns. It's particularly useful for tasks like text processing, log file analysis, and data extraction.

## Basic Syntax

The basic syntax of the `grep` command is as follows:

```
grep [options] pattern [file...]
```

- `options`: Various command-line options that modify `grep`'s behavior.
- `pattern`: The regular expression pattern you want to search for.
- `file`: The file or files in which you want to search for the pattern. You can specify multiple files to search.

## Common Options

Here are some common options used with `grep`:

- `-i`: Perform a case-insensitive search.
- `-r` or `-R`: Recursively search directories.
- `-l`: Print only the names of files that contain the pattern.
- `-c`: Print a count of matching lines instead of the lines themselves.
- `-n`: Display line numbers along with matching lines.
- `-v`: Invert the match, i.e., print lines that do not contain the pattern.
- `-E` or `--extended-regexp`: Use extended regular expressions (allows more advanced pattern matching).
- `-F` or `--fixed-strings`: Treat the pattern as a fixed string (no regular expressions).
- `-w`: Match whole words only.

## Examples

### Basic Text Search

To search for the word "example" in a file named `file.txt`, you can use the following command:

```bash
grep "example" file.txt
```

### Case-Insensitive Search

To perform a case-insensitive search for "example" in the same file, use the `-i` option:

```bash
grep -i "example" file.txt
```

### Recursive Search

To search for a pattern in all files within a directory and its subdirectories, use the `-r` option:

```bash
grep -r "pattern" /path/to/directory
```

### Counting Matches

To count the number of lines that match a pattern, use the `-c` option:

```bash
grep -c "pattern" file.txt
```

### Display Line Numbers

To display line numbers along with matching lines, use the `-n` option:

```bash
grep -n "pattern" file.txt
```

### Invert Match

To find lines that do not contain a specific pattern, use the `-v` option:

```bash
grep -v "pattern" file.txt
```

### Using Regular Expressions

You can use regular expressions for more complex pattern matching. For example, to find lines that start with "error," you can use:

```bash
grep "^error" file.txt
```

 

### 1. Basic Text Search

Pattern: `"apple"`

Input File (`fruits.txt`):

```
apple
banana
cherry
apple pie
grape
```

Command:

```bash
grep "apple" fruits.txt
```

Output:

```
apple
apple pie
```

Explanation:
- The pattern `"apple"` is matched in lines that contain the word "apple."

### 2. Case-Insensitive Search

Pattern: `"Banana"`

Input File (`fruits.txt`):

```
apple
Banana
cherry
APPLE PIE
grape
```

Command:

```bash
grep -i "banana" fruits.txt
```

Output:

```
Banana
```

Explanation:
- The `-i` option makes the search case-insensitive, so it matches both `"Banana"` and `"banana"`.

### 3. Recursive Search

Pattern: `"error"`

Command:

```bash
grep -r "error" /path/to/directory
```

Output:

```
/path/to/directory/file1.txt: This line contains an error.
/path/to/directory/subdir/file2.txt: Another error occurred.
```

Explanation:
- The `-r` option searches for the pattern `"error"` in all files within the specified directory and its subdirectories.

### 4. Counting Matches

Pattern: `"apple"`

Input File (`fruits.txt`):

```
apple
banana
cherry
apple pie
grape
```

Command:

```bash
grep -c "apple" fruits.txt
```

Output:

```
2
```

Explanation:
- The `-c` option returns the count of lines that match the pattern `"apple"` in the file.

### 5. Display Line Numbers

Pattern: `"cherry"`

Input File (`fruits.txt`):

```
apple
banana
cherry
apple pie
grape
```

Command:

```bash
grep -n "cherry" fruits.txt
```

Output:

```
3: cherry
```

Explanation:
- The `-n` option displays line numbers along with the matching lines.

### 6. Invert Match

Pattern: `"apple"`

Input File (`fruits.txt`):

```
apple
banana
cherry
apple pie
grape
```

Command:

```bash
grep -v "apple" fruits.txt
```

Output:

```
banana
cherry
grape
```

Explanation:
- The `-v` option inverts the match and displays lines that do not contain the pattern `"apple"`.

### 7. Using Regular Expressions

Pattern: `"^error"`

Input File (`logs.txt`):

```
error: An error occurred
Warning: This is a warning
error: Another error
Debug: Debugging message
```

Command:

```bash
grep "^error" logs.txt
```

Output:

```
error: An error occurred
error: Another error
```

Explanation:
- The pattern `"^error"` matches lines that start with the word "error" using a regular expression.


# Vi editor
## some essential commands for using the `vi` text editor:

1. `vi filename`: Open a file in `vi` for editing.
2. `i`: Enter insert mode (for inserting text).
3. `Esc`: Exit insert mode and return to command mode.
4. `:w`: Save the file (write).
5. `:q`: Quit `vi` (if no changes were made).
6. `:wq` or `:x`: Save and quit `vi`.
7. `:q!`: Quit `vi` without saving changes.
8. `dd`: Delete the current line.
9. `yy`: Copy (yank) the current line.
10. `p`: Paste the copied text after the current line.
11. `u`: Undo the last change.
12. `Ctrl + r`: Redo the last undone change.
13. `:set number`: Show line numbers.
14. `:set nonumber`: Hide line numbers.
15. `:find pattern`: Search for a pattern in the file.
16. `n`: Move to the next occurrence of the search pattern.
17. `N`: Move to the previous occurrence of the search pattern.
18. `:s/old/new`: Replace the first occurrence of "old" with "new" in the current line.
19. `:s/old/new/g`: Replace all occurrences of "old" with "new" in the current line.
20. `:%s/old/new/g`: Replace all occurrences of "old" with "new" in the entire file.
21. `:set syntax=language`: Set syntax highlighting for a specific programming language.
22. `:help`: Access the `vi` help system. 


# creating script files 

**Step 1: Create a Script File**
- You can create a script file using a text editor, such as `nano`, `vim`, or `gedit`. Save the file with a `.sh` extension, which indicates that it's a shell script.

```bash
nano myscript.sh
```

**Step 2: Write Your Shell Commands**
- Inside the script file, write the series of shell commands that you want to include in your custom command. For example, let's create a simple script that displays a welcome message:

```bash
#!/bin/bash
# This is a simple shell script

echo "Welcome to my custom command!"
echo "Today is $(date)"
```

In the above script:
- `#!/bin/bash` specifies that the script should be interpreted using the Bash shell.
- `#` at the beginning of a line indicates a comment.
- `echo` is used to print text to the console.
- `$(date)` is a command substitution that inserts the current date and time.

**Step 3: Save and Exit**
- Save the script file and exit the text editor.

**Step 4: Make the Script Executable**
- To run the script as a command, you need to make it executable. Use the `chmod` command to add execute permissions to the script file.

```bash
chmod +x myscript.sh
```

**Step 5: Run Your Custom Command**
- Now, you can run your custom command like any other shell command.

```bash
./myscript.sh
```

The script will execute and display the welcome message along with the current date and time.


# Meta characters
 

1. **Wildcard `*`**:
   - The `*` metacharacter is used to match zero or more characters in filenames. It's often used in file globbing.
   - Example: `ls *.txt` lists all files with a `.txt` extension in the current directory.
   - Example: `rm *.bak` removes all files with a `.bak` extension in the current directory.

2. **Question Mark `?`**:
   - The `?` metacharacter is used to match a single character in filenames. It's often used in file globbing when you need to specify a single character.
   - Example: `ls file?.txt` lists files like `file1.txt`, `file2.txt`, but not `file10.txt`.
   - Example: `rm ?.txt` removes files with a single-character filename and a `.txt` extension.

3. **Pipe `|`**:
   - The `|` metacharacter is used to send the output of one command as input to another command. It's called "piping."
   - Example: `ls | grep "file"` lists files in the current directory and then searches for files containing the word "file."
   - Example: `cat file.txt | grep "pattern"` reads the content of `file.txt` and searches for the specified pattern.

4. **Redirect Output `>`**:
   - The `>` metacharacter is used to redirect the output of a command to a file, overwriting the file's content if it exists.
   - Example: `ls > filelist.txt` lists files in the current directory and saves the output in a file named `filelist.txt`.
   - Example: `echo "Hello" > greeting.txt` creates a file `greeting.txt` with the text "Hello."

5. **Run in the Background `&`**:
   - The `&` metacharacter is used to run a command in the background, allowing you to continue using the shell while the command runs.
   - Example: `long-running-command &` runs a command in the background, freeing up the shell for other tasks.
   - Example: `rsync -av /source /destination &` runs a file synchronization task in the background.

# Command Arguements and Parameters

**Arguments** are values or items that you provide to a command to specify what the command should act on or with. They are typically the non-option items you provide to a command.

**Parameters**, on the other hand, are settings or options that modify a command's behavior. They are preceded by a dash (`-`) or double dash (`--`) and provide additional instructions to the command.

Here are some examples:

1. **Copy Files (cp command)**:
   - Command: `cp`
   - Arguments: `file1.txt` and `file2.txt`
   - Parameters: None
   - Explanation: This command copies `file1.txt` to `file2.txt`. In this case, the filenames are the arguments, and there are no parameters.

   ```bash
   cp file1.txt file2.txt
   ```

2. **Copy Directory Recursively (cp command)**:
   - Command: `cp`
   - Arguments: `source_directory` and `destination_directory`
   - Parameters: `-r` (recursive)
   - Explanation: This command copies the contents of `source_directory` to `destination_directory`, including subdirectories. Here, the directories are arguments, and `-r` is a parameter.

   ```bash
   cp -r source_directory destination_directory
   ```

3. **List Files in a Long Format (ls command)**:
   - Command: `ls`
   - Arguments: None
   - Parameters: `-l` (long format)
   - Explanation: This command lists the files in the current directory in long format, showing detailed information about each file. There are no arguments; `-l` is a parameter.

   ```bash
   ls -l
   ```

4. **Search for a Pattern in Files (grep command)**:
   - Command: `grep`
   - Arguments: `pattern` and `file.txt`
   - Parameters: None
   - Explanation: This command searches for the specified `pattern` within the contents of `file.txt`. The pattern and the filename are arguments, and there are no parameters.

   ```bash
   grep "search_pattern" file.txt
   ```

5. **Display Disk Usage (du command)**:
   - Command: `du`
   - Arguments: `-h` (human-readable format)
   - Parameters: `/path/to/directory`
   - Explanation: This command displays disk usage information in a human-readable format for the specified directory. `-h` is a parameter, and the directory path is an argument.

   ```bash
   du -h /path/to/directory
   ```

# Program Output as  Arguement 

**Program Output as Arguments**:

In Unix-like operating systems, you can use the output of one command as input to another command using pipes (`|`). This allows you to chain commands together, passing data from one command's output to another command's input. It's a powerful feature for data processing and manipulation.

Here are some examples:

1. **List All .txt Files (ls and grep)**:
   - Command 1: `ls`
   - Command 2: `grep ".txt"`
   - Explanation: The first command (`ls`) lists all files in the current directory. The output, which is a list of filenames, is then passed to the second command (`grep`) using a pipe. The `grep` command searches for filenames that contain ".txt."

   ```bash
   ls | grep ".txt"
   ```

2. **Count Lines in a File (cat and wc)**:
   - Command 1: `cat file.txt`
   - Command 2: `wc -l`
   - Explanation: The first command (`cat`) displays the content of `file.txt`. The output (the lines in the file) is then passed to the second command (`wc -l`) using a pipe. The `wc` command with the `-l` parameter counts the number of lines.

   ```bash
   cat file.txt | wc -l
   ```

3. **Find and Replace (grep and sed)**:
   - Command 1: `grep "pattern" input.txt`
   - Command 2: `sed 's/pattern/replacement/'`
   - Explanation: The first command (`grep`) searches for lines containing "pattern" in `input.txt`. The matched lines are then passed to the second command (`sed`) using a pipe. The `sed` command replaces "pattern" with "replacement."

   ```bash
   grep "pattern" input.txt | sed 's/pattern/replacement/'
   ```

4. **Sort a List of Numbers (echo, sort, and uniq)**:
   - Command 1: `echo "5 2 8 2 5 1 7"`
   - Command 2: `tr ' ' '\n'`
   - Command 3: `sort`
   - Command 4: `uniq`
   - Explanation: The first command (`echo`) prints a list of numbers. The output is passed to the second command (`tr`) to split the numbers into separate lines. Then, the `sort` command arranges the numbers in ascending order, and `uniq` removes duplicates.

   ```bash
   echo "5 2 8 2 5 1 7" | tr ' ' '\n' | sort | uniq
   ```
 

 # Shell variables 
  
**Shell Variables**:

Shell variables are placeholders that store data, such as numbers, strings, file paths, and more. These variables are used within shell scripts and commands to hold and manipulate data. They can be predefined system variables or user-defined variables.

Here are some examples:

1. **Predefined Shell Variables**:

   - **`$HOME`**: This variable represents the user's home directory. It's often used to reference the user's home directory in various commands and scripts.

     Example:
     ```bash
     echo "Your home directory is: $HOME"
     ```

   - **`$USER`**: It contains the username of the currently logged-in user.

     Example:
     ```bash
     echo "You are logged in as: $USER"
     ```

   - **`$PATH`**: This variable defines the search path for executable commands. It's a colon-separated list of directories where the shell looks for commands to execute.

     Example:
     ```bash
     echo "The PATH variable is set to: $PATH"
     ```

2. **User-Defined Variables**:

   You can create your own variables to store custom data. Variables are assigned values using the `=` operator. Here are a couple of examples:

   - **`myVar`**: A user-defined variable storing a string.

     Example:
     ```bash
     myVar="Hello, World!"
     echo $myVar
     ```

   - **`num1` and `num2`**: User-defined variables holding numerical values.

     Example:
     ```bash
     num1=5
     num2=10
     sum=$((num1 + num2))
     echo "The sum of $num1 and $num2 is $sum"
     ```

   - **`filename`**: Storing a file path.

     Example:
     ```bash
     filename="/path/to/myfile.txt"
     echo "Working with the file: $filename"
     ```

# I/O redirection
 

**I/O Redirection**:

I/O (Input/Output) redirection is a powerful feature in Unix-like operating systems that allows you to control where the input and output of a command come from and go to. Redirection operators help you manage the flow of data in various ways.

Here are some common I/O redirection operators and their usage:

1. **Redirect Standard Output (`>`)**:
   - The `>` operator is used to redirect the standard output of a command to a file. If the file already exists, it will be overwritten; otherwise, a new file will be created.

   Example: Redirect the output of a command to a file.
   ```bash
   ls > filelist.txt
   ```

2. **Append to a File (`>>`)**:
   - The `>>` operator is used to append the standard output of a command to a file. If the file does not exist, it will be created.

   Example: Append the output of a command to an existing file.
   ```bash
   echo "New data" >> existingfile.txt
   ```

3. **Redirect Standard Input (`<`)**:
   - The `<` operator is used to provide input from a file to a command.

   Example: Use a file as input for a command.
   ```bash
   cat < inputfile.txt
   ```

4. **Redirect Standard Error (`2>`)**:
   - The `2>` operator is used to redirect error messages (standard error) to a file.

   Example: Redirect error messages to an error log file.
   ```bash
   command_that_might_fail 2> error.log
   ```

5. **Pipe (`|`)**:
   - The `|` operator is used to send the standard output of one command as the standard input to another command.

   Example: Chain commands by sending the output of one to the input of another.
   ```bash
   cat file.txt | grep "pattern"
   ```

6. **Combine Standard Output and Standard Error (`2>&1`)**:
   - The `2>&1` operator is used to combine the standard output and standard error streams. This is useful for capturing both output and error messages.

   Example: Redirect both standard output and standard error to a file.
   ```bash
   command 2>&1 > output_and_error.log
   ```

I/O redirection allows you to tailor the behavior of commands to your needs. You can capture, save, or manipulate the input and output of commands, making it an essential feature for scripting and data processing tasks.


# Unit 3 part 2

# Filters 

**Filters**:

Filters are commands or programs in Unix-like operating systems that take input from a data stream, process it in a specific way, and produce output. These filters are used to transform or analyze data and are a fundamental part of text processing in the command line. Here are some common filters and their usage:

1. **`grep` (Global Regular Expression Print)**:
   - `grep` is used to search and filter lines that match a specified pattern in a text file or data stream. It's an essential tool for pattern matching.

   **Example**: Search for lines containing the word "apple" in a text file.
   ```bash
   grep "apple" file.txt
   ```

2. **`sed` (Stream Editor)**:
   - `sed` is used for text manipulation and transformation. It allows you to perform tasks like search and replace, text substitution, and basic text processing.

   **Example**: Replace "old_word" with "new_word" in a text file.
   ```bash
   sed 's/old_word/new_word/g' input.txt
   ```

3. **`awk`**:
   - `awk` is a versatile text processing tool that's especially useful for handling structured data with fields and records. It allows for complex text processing tasks with custom scripts.

   **Example**: Print the second field of a CSV file.
   ```bash
   awk -F ',' '{print $2}' data.csv
   ```

4. **`sort`**:
   - `sort` is used to sort lines of text alphabetically or numerically, either in ascending or descending order.

   **Example**: Sort a list of names alphabetically.
   ```bash
   sort names.txt
   ```

5. **`cut`**:
   - `cut` is used to extract specific columns or fields from text data, typically when data is delimited.

   **Example**: Extract the first three characters of each line in a text file.
   ```bash
   cut -c 1-3 data.txt
   ```

6. **`tr` (Translate)**:
   - `tr` is used to translate or delete characters in a text stream.

   **Example**: Convert uppercase letters to lowercase.
   ```bash
   tr 'A-Z' 'a-z' < input.txt
   ```

# Other Filters 

**Other Filters**:

1. **`sort`**:
   - `sort` is used to sort lines of text, either alphabetically or numerically, and can arrange data in ascending or descending order.

   **Example**: Sort a list of numbers in ascending order.
   ```bash
   sort numbers.txt
   ```

2. **`cut`**:
   - `cut` is used to extract specific columns or fields from text data. It's often used when data is delimited.

   **Example**: Extract the second column (fields separated by a comma) from a CSV file.
   ```bash
   cut -d ',' -f 2 data.csv
   ```

3. **`tr` (Translate)**:
   - `tr` is used to translate or delete characters in a text stream, which can be useful for character conversions or substitutions.

   **Example**: Replace all spaces with underscores in a file.
   ```bash
   tr ' ' '_' < input.txt
   ```

4. **`wc`**:
   - `wc` (word count) is used to count lines, words, and characters in text data. It can provide various statistics about the input.

   **Example**: Count the number of lines in a file.
   ```bash
   wc -l file.txt
   ```

5. **`uniq`**:
   - `uniq` is used to remove duplicate lines from sorted data. It's often used in conjunction with the `sort` command.

   **Example**: Remove duplicate lines from a sorted list of names.
   ```bash
   sort names.txt | uniq
   ```

6. **`tee`**:
   - `tee` duplicates the input, allowing you to send it to multiple outputs. This can be useful for logging and parallel processing.

   **Example**: Display the content of a file on the terminal and save it to an output file.
   ```bash
   cat file.txt | tee output.txt
   ```

7. **`head` and `tail`**:
   - `head` is used to display the first lines of a file, while `tail` displays the last lines. You can control the number of lines to display.

   **Example**: Display the first 10 lines of a log file.
   ```bash
   head -n 10 logfile.txt
   ```
# Stream editor Sed
 
**The Stream Editor Sed**:

`sed` is a powerful command-line utility used for text manipulation and transformation. It's especially helpful for making basic text transformations on an input stream, such as a file or data from a pipeline. `sed` allows you to perform tasks like search and replace, text substitution, and text transformation.

Here are some common use cases with examples:

1. **Search and Replace**:
   - You can use `sed` to search for a specific pattern in the text and replace it with another pattern.

   **Example**: Replace all occurrences of "apple" with "orange" in a text file.
   ```bash
   sed 's/apple/orange/g' file.txt
   ```

2. **Delete Lines**:
   - `sed` can delete lines from the input text that match a particular pattern.

   **Example**: Delete all lines containing the word "error" from a log file.
   ```bash
   sed '/error/d' logfile.txt
   ```

3. **Text Transformation**:
   - You can use `sed` to transform text, such as converting text to uppercase or lowercase.

   **Example**: Convert all text to uppercase.
   ```bash
   sed 's/.*/\U&/' input.txt
   ```

4. **Print Specific Lines**:
   - `sed` can be used to print specific lines or ranges of lines from the input.

   **Example**: Print lines 5 to 10 from a text file.
   ```bash
   sed -n '5,10p' file.txt
   ```

5. **Appending and Inserting Text**:
   - `sed` allows you to append or insert text at specific lines in the input.

   **Example**: Insert a new line before every line containing "pattern."
   ```bash
   sed '/pattern/i New line of text' file.txt
   ```

6. **File Backup and In-Place Editing**:
   - With `sed`, you can create a backup of a file and perform in-place editing to update the file directly.

   **Example**: Replace text in a file and create a backup with a ".bak" extension.
   ```bash
   sed -i.bak 's/old_text/new_text/g' file.txt
   ```

# AWK patterns
 

**The AWK Pattern Scanning and Processing Language**:

`awk` is a versatile and powerful programming language used for text processing. It is particularly useful for handling structured data where records and fields are delimited. `awk` is known for its pattern scanning and text processing capabilities and is often used for data extraction, reporting, and manipulation. It operates on a line-by-line basis, making it well-suited for working with structured text data.

Here are some common use cases with examples:

1. **Basic Usage**:
   - `awk` can be used to process and print specific fields or columns from structured data.

   **Example**: Print the first and third columns from a space-separated file.
   ```bash
   awk '{print $1, $3}' data.txt
   ```

2. **Pattern Matching**:
   - `awk` is excellent for pattern matching. You can specify patterns and actions to be executed when patterns are matched.

   **Example**: Print lines containing the word "error" in a log file.
   ```bash
   awk '/error/ {print}' logfile.txt
   ```

3. **Calculations and Aggregations**:
   - `awk` can perform mathematical calculations and aggregations, making it useful for generating statistics.

   **Example**: Calculate the sum of values in the second column of a CSV file.
   ```bash
   awk -F ',' '{sum += $2} END {print "Sum:", sum}' data.csv
   ```

4. **Text Transformation**:
   - `awk` can transform text data, such as converting text to uppercase or lowercase.

   **Example**: Convert text to uppercase.
   ```bash
   awk '{print toupper($0)}' input.txt
   ```

5. **Custom Functions**:
   - You can define custom functions in `awk` for more complex text processing tasks.

   **Example**: Create an `awk` script to count and print unique words in a file.
   ```awk
   { for (i=1; i<=NF; i++) words[$i]++ }
   END { for (w in words) print w, words[w] }
   ```

6. **Working with Multiple Files**:
   - `awk` can process multiple files simultaneously.

   **Example**: Calculate the average of the second column in multiple data files.
   ```bash
   awk 'FNR == 1 {sum = 0} {sum += $2} END {print FILENAME, "Average:", sum/NR}' file1.txt file2.txt
   ```



# Good Files and Good Filters
 

**Good Files and Good Filters**:

In the Unix philosophy, it's common to adhere to the principle of creating small, single-purpose utilities or "good filters" that do one thing well. These filters are designed to perform a specific task efficiently and effectively. They can be combined to build complex data processing workflows, creating a modular and flexible approach to solving problems.

Here are some examples of "Good Filters" and how they can be used together:

**Good Filters**:
1. **`grep`**:
   - `grep` is a good filter for searching and filtering text based on patterns.

2. **`sed`**:
   - `sed` is a good filter for performing basic text transformations and substitutions.

3. **`cut`**:
   - `cut` is a good filter for extracting specific columns or fields from structured data.

4. **`sort`**:
   - `sort` is a good filter for sorting lines of text data.

**Examples of Combining Good Filters**:

1. **Counting Lines with `grep` and `wc`**:
   - You can use `grep` to filter lines and then count them using `wc`.

   ```bash
   cat data.txt | grep "pattern" | wc -l
   ```

2. **Extracting Specific Columns with `cut` and `grep`**:
   - Use `grep` to filter lines containing a specific pattern and then extract specific columns using `cut`.

   ```bash
   cat data.csv | grep "specific_pattern" | cut -d ',' -f 2,4
   ```

3. **Sorting and Filtering with `grep` and `sort`**:
   - Use `grep` to filter lines and then sort the results using `sort`.

   ```bash
   cat unsorted_data.txt | grep "pattern" | sort
   ```

4. **Text Transformation with `sed` and `grep`**:
   - Use `grep` to filter lines and then apply text transformation using `sed`.

   ```bash
   cat text_data.txt | grep "search_pattern" | sed 's/old_text/new_text/g'
   ```
 

 # UNIT 2

 # File Attributes and permissions 

**File Attributes and Permissions**:

In Unix-like operating systems, each file and directory has associated attributes and permissions that define how the file can be accessed and manipulated. These attributes include:

1. **File Type**: This attribute specifies the type of the file, such as regular file, directory, symbolic link, etc.

2. **Owner**: The owner of the file is the user who initially created the file. The owner has special privileges and can modify permissions.

3. **Group**: Files are associated with a group, and members of that group may have specific access rights to the file.

4. **Permissions**: File permissions determine who can read, write, and execute the file. Permissions are typically divided into three categories:
   - Owner (u): Permissions for the owner of the file.
   - Group (g): Permissions for members of the group associated with the file.
   - Others (o): Permissions for all other users who are not the owner or in the group.

Permissions are usually represented as a combination of symbols:

- `r` (read): Allows reading the file's content.
- `w` (write): Allows modifying the file.
- `x` (execute): Allows running the file as a program.

Here are some examples:

1. **Listing File Attributes**:

   You can use the `ls` command with the `-l` option to list the attributes and permissions of files in a directory. In the output, you can see the file type, owner, group, and permissions:

   ```bash
   ls -l
   ```

2. **Changing File Permissions**:

   Use the `chmod` command to modify file permissions. For example, to give the owner read and write permissions and the group read-only permissions to a file:

   ```bash
   chmod u=rw,g=r myfile.txt
   ```

3. **Changing File Owner**:

   The `chown` command allows you to change the owner of a file. To change the owner of a file named `myfile.txt` to a user named `newowner`:

   ```bash
   chown newowner myfile.txt
   ```

4. **Changing File Group**:

   The `chgrp` command is used to change the group associated with a file. To change the group of a file named `myfile.txt` to a group named `newgroup`:

   ```bash
   chgrp newgroup myfile.txt
   ```


# File Command and File Type


**The File Command - Knowing the File Type**:

The "file" command in Unix-like operating systems is used to determine the type of a file by analyzing its contents. It provides information about the format of the file, which can be important for selecting the appropriate tools or programs to work with that file.

Here's how to use the "file" command:

```bash
file [options] filename
```

- `filename`: The name of the file you want to inspect.
- `[options]`: You can use various options to customize the output or behavior.

**Examples**:

1. **Determine the File Type**:

   To find out the type of a file, simply provide the filename as an argument to the "file" command. For example:

   ```bash
   file document.pdf
   ```

   This command will display information about the file type. In this case, it might show something like "PDF document, version 1.5."

2. **Using Wildcards**:

   You can use wildcards to check multiple files at once. For instance, to determine the types of all files with a ".txt" extension in a directory:

   ```bash
   file *.txt
   ```

   This command will provide information about each file's type in the specified directory.

3. **Customizing the Output**:

   The "file" command offers various options to customize the output. For example, you can use the `-b` option to suppress the filename in the output:

   ```bash
   file -b image.jpg
   ```

   This will show only the file type, such as "JPEG image data, JFIF standard 1.01."

4. **Using File Types in Scripts**:

   The "file" command is commonly used in shell scripts to perform different actions based on the file type. For example, you can use it to identify image files and process them differently from text files.

   ```bash
   if file document.txt | grep -q "text"; then
       echo "This is a text file."
   else
       echo "This is not a text file."
   fi
   ```

   In this script, it checks if the file is a text file by analyzing the output of the "file" command.

# CHMOD Command



**The Chmod Command - Changing File Permissions**:

The "chmod" (change mode) command in Unix-like operating systems is used to modify the file permissions of a file or directory. File permissions determine who can read, write, and execute the file. The "chmod" command allows you to grant or revoke these permissions for the owner, group, and others.

Here's the basic syntax of the "chmod" command:

```bash
chmod [options] permissions filename
```

- `permissions`: This specifies the new permissions that you want to assign. You can use symbolic notation (e.g., u=rw, g=r, o=r) or octal mode (e.g., 644, 755).
- `filename`: The name of the file or directory for which you want to change permissions.

**Examples**:

1. **Using Symbolic Notation**:

   - Symbolic notation allows you to specify permissions for the owner (u), group (g), and others (o) using symbols such as "r" for read, "w" for write, and "x" for execute.

   - Grant read and write permissions to the owner and read-only permissions to the group and others for a file named "mydata.txt":

     ```bash
     chmod u=rw,g=r,o=r mydata.txt
     ```

2. **Using Octal Mode**:

   - Octal mode represents permissions using a three-digit number. Each digit represents a permission set (owner, group, others) and is a combination of values: read (4), write (2), and execute (1).

   - Set the permissions to 644, which grants read and write permissions to the owner and read-only permissions to the group and others:

     ```bash
     chmod 644 mydata.txt
     ```

3. **Combining Permissions**:

   - You can combine permissions for different categories in symbolic notation. For example, to grant the owner read and write permissions and the group and others read-only permissions for a directory:

     ```bash
     chmod u=rw,go=r mydirectory/
     ```

4. **Revoking Permissions**:

   - To revoke permissions, use a minus sign ("-") before the permission you want to remove. For example, to remove write permission from the group for a file:

     ```bash
     chmod g-w myfile.txt
     ```

5. **Using Recursive Mode with Directories**:

   - To change permissions recursively for all files and subdirectories within a directory, use the `-R` option. For example, to give read-only permissions to all files and directories under "mydir":

     ```bash
     chmod -R u=r,go=r mydir/
     ```

# CHOWN Command
 

**The Chown Command - Changing the Owner of a File**:

The "chown" (change owner) command in Unix-like operating systems is used to change the owner of a file or directory. The owner of a file has special privileges, including the ability to change file permissions and make modifications. The "chown" command allows you to transfer ownership from one user to another.

Here's the basic syntax of the "chown" command:

```bash
chown [options] newowner:group filename
```

- `newowner`: The new owner to whom you want to transfer ownership of the file.
- `group`: The new group for the file (optional).
- `filename`: The name of the file or directory for which you want to change the owner.

**Examples**:

1. **Changing the Owner**:

   - To change the owner of a file named "myfile.txt" to a user named "newowner":

     ```bash
     chown newowner myfile.txt
     ```

2. **Changing Owner and Group**:

   - You can also change the group along with the owner. To change the owner to "newowner" and the group to "newgroup" for a file:

     ```bash
     chown newowner:newgroup myfile.txt
     ```

3. **Recursive Change for Directories**:

   - To change ownership recursively for all files and subdirectories within a directory, use the `-R` option. For example, to change the owner of all files and directories under "mydir" to "newowner":

     ```bash
     chown -R newowner mydir/
     ```

4. **Preserving File Permissions**:

   - By default, the "chown" command also changes the file permissions to those of the new owner. To keep the existing file permissions when changing the owner:

     ```bash
     chown --no-preserve=owner newowner myfile.txt
     ```

5. **Changing the Group Only**:

   - To change the group of a file while keeping the owner intact, use a colon without specifying a new owner:

     ```bash
     chown :newgroup myfile.txt
     ```
# CHGRP Command
 

**The Chgrp Command - Changing the Group of a File**:

The "chgrp" (change group) command in Unix-like operating systems is used to change the group associated with a file or directory. Groups allow multiple users to share access to files with specific permissions. The "chgrp" command is useful when you want to change the group ownership of a file or directory.

Here's the basic syntax of the "chgrp" command:

```bash
chgrp [options] newgroup filename
```

- `newgroup`: The new group to which you want to assign ownership of the file.
- `filename`: The name of the file or directory for which you want to change the group ownership.

**Examples**:

1. **Changing the Group**:

   - To change the group of a file named "myfile.txt" to a group named "newgroup":

     ```bash
     chgrp newgroup myfile.txt
     ```

2. **Changing Group Ownership of Directories Recursively**:

   - To change the group ownership recursively for all files and subdirectories within a directory, use the `-R` option. For example, to change the group ownership of all files and directories under "mydir" to "newgroup":

     ```bash
     chgrp -R newgroup mydir/
     ```

3. **Changing Group While Keeping Owner Intact**:

   - To change the group of a file while keeping the owner intact, simply provide the new group name and use a colon without specifying a new owner:

     ```bash
     chgrp :newgroup myfile.txt
     ```

4. **Changing the Group with Symbolic Permissions**:

   - The "chgrp" command can also be used in combination with "chmod" to change both the group and permissions. For example, to change the group and set read and write permissions for the group on a file:

     ```bash
     chgrp newgroup myfile.txt && chmod g+rw myfile.txt
     ```
 


 # UNIT 3 PART-2

 

1. **Shell Variables:**
   Shell variables are used to store data within a shell script. You can declare and assign values to variables using the `=` operator. Here's an example:

   ```bash
   my_variable="Hello, World!"
   echo $my_variable
   ```

   In this example, we've assigned the string "Hello, World!" to the variable `my_variable` and then printed its value using `echo`.

2. **The Export Command:**
   The `export` command is used to make a variable available to child processes or subshells. For instance:

   ```bash
   export my_var="Exported Variable"
   bash   # Start a new subshell
   echo $my_var  # This will still print "Exported Variable"
   exit  # Exit the subshell
   ```

   The variable `my_var` is exported and can be accessed in the subshell created by `bash`.

3. **The Read Command:**
   The `read` command is used to read input from the user and store it in a variable. For example:

   ```bash
   echo -n "Enter your name: "
   read username
   echo "Hello, $username!"
   ```

   This script prompts the user for their name and then prints a greeting using the entered name.

4. **Positional Parameters:**
   Positional parameters are used to access arguments passed to a shell script. For instance:

   ```bash
   echo "The script name is: $0"
   echo "The first argument is: $1"
   echo "The second argument is: $2"
   echo "The number of arguments is: $#"
   ```

   If you run the script with arguments like `./script.sh arg1 arg2`, it will display the script name, the first argument, and the second argument.

5. **The $? Variable (Exit Status):**
   `$?` stores the exit status of the last executed command. A value of 0 indicates success, while non-zero values indicate an error. For example:

   ```bash
   ls /nonexistent_directory  # This will result in an error
   if [ $? -eq 0 ]; then
       echo "Command succeeded."
   else
       echo "Command failed with exit status $?"
   fi
   ```

6. **The Set Command:**
   The `set` command is used to modify shell options and positional parameters. For example, to set or unset options:

   ```bash
   set -x  # Enable debugging
   echo "This is a debug message."
   set +x  # Disable debugging
   ```

7. **The Exit Command:**
   The `exit` command is used to terminate a shell script or session and return an exit status code. For example:

   ```bash
   echo "Script is about to exit."
   exit 2  # Exiting with a non-zero status code (indicating an error)
   ```

8. **The Expr Command (Performing Integer Arithmetic):**
   The `expr` command is used for integer arithmetic and expression evaluation. For example:

   ```bash
   result=$(expr 5 + 3)
   echo "5 + 3 = $result"
   ```

9. **Real Arithmetic in Shell Programs:**
   Shell scripts typically handle integer arithmetic. For real number arithmetic, you might need external tools like `bc`, or use a different scripting language like Python.

10. **The Here Document (<<):**
    A here document is a way to include multi-line text within a script. For example, creating a text file:

   ```bash
   cat <<EOF > myfile.txt
   This is a
   multiline
   text block.
   EOF
   ```

11. **The Sleep Command:**
    `sleep` is used to pause script execution for a specified number of seconds:

   ```bash
   echo "Start of script"
   sleep 3
   echo "End of script"
   ```

   This will introduce a 3-second delay between the two echo statements.

12. **The Script Command:**
    The `script` command is used to create a typescript of a terminal session:

   ```bash
   script my_session.log
   echo "This is a recorded session."
   exit
   ```

   This creates a log of everything that happens in the terminal session.

13. **The Eval Command:**
    `eval` is used to execute shell commands stored in a string. For example:

   ```bash
   command="echo Hello, World!"
   eval $command
   ```

   This will execute the command stored in the `command` variable.

14. **The Exec Command:**
    `exec` is used to replace the current shell process with a new command. For example:

   ```bash
   exec ls  # Replaces the shell with the 'ls' command
   echo "This will not be executed."
   ```

   In this example, the shell is replaced by the `ls` command, and the echo statement is not executed.

 