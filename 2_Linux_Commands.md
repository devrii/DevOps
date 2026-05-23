# 🐧 Linux Commands 

## Basic Navigation

| Command            | Explanation                                        |
| ------------------ | -------------------------------------------------- |
| `pwd`              | Shows current working directory path               |
| `ls`               | Lists files and directories                        |
| `ls -a`            | Shows hidden files also                            |
| `ls -la`           | Detailed list including hidden files               |
| `ls -l`            | Detailed file listing                              |
| `ls -laht`         | Long list sorted by time with human-readable sizes |
| `ls -lahtr`        | Reverse time-sorted listing                        |
| `ls -lahs`         | Shows file sizes in blocks                         |
| `ls -lahr`         | Reverse order detailed listing                     |
| `ls -c`            | Sorts files by change time                         |
| `clear`            | Clears terminal screen                             |
| `man command_name` | Opens manual/help page for a command               |

---

# APT Package Manager

| Command                         | Explanation                     |
| ------------------------------- | ------------------------------- |
| `sudo apt install package_name` | Installs a package              |
| `sudo apt update`               | Updates package repository list |
| `sudo apt upgrade`              | Upgrades installed packages     |

## Difference Between `update` and `upgrade`

| Command       | Working                             |
| ------------- | ----------------------------------- |
| `apt update`  | Refreshes package information       |
| `apt upgrade` | Installs newer versions of packages |

---

# Package Information

| Command                 | Explanation                         |
| ----------------------- | ----------------------------------- |
| `apt list --installed`  | Shows installed packages            |
| `apt list --upgradable` | Shows packages that can be upgraded |

---

# System Information

| Command               | Explanation                 |
| --------------------- | --------------------------- |
| `cat /etc/os-release` | Displays OS details         |
| `id`                  | Shows user and group IDs    |
| `uname`               | Displays system/kernel info |

---

# Important Paths

| Path | Meaning        |
| ---- | -------------- |
| `~`  | Home directory |
| `/`  | Root directory |

---

# Directory Navigation

| Command | Explanation             |
| ------- | ----------------------- |
| `cd`    | Change directory        |
| `cd ..` | Move one directory back |
| `cd ~`  | Go to home directory    |
| `cd /`  | Go to root directory    |

---

# Directory & File Management

| Command         | Explanation                              |
| --------------- | ---------------------------------------- |
| `mkdir dirname` | Creates a directory                      |
| `tree`          | Shows directory structure in tree format |
| `stat`          | Displays file details                    |
| `basename`      | Shows file name from path                |

---

# File Creation

| Command                 | Explanation            |
| ----------------------- | ---------------------- |
| `touch file_name`       | Creates empty file     |
| `touch file{1..10}.txt` | Creates multiple files |
| `touch .file_name`      | Creates hidden file    |

---

# Writing Content to Files

| Command                          | Explanation             |
| -------------------------------- | ----------------------- |
| `echo "Hello World" > file.txt`  | Writes content to file  |
| `echo "Append text" >> file.txt` | Appends content to file |

---

# File Reading

| Command               | Explanation                         |
| --------------------- | ----------------------------------- |
| `cat file.txt`        | Displays file content               |
| `less file.txt`       | Reads file page by page             |
| `more file.txt`       | Reads file page-wise                |
| `head file.txt`       | Shows first 10 lines                |
| `head -c 20 file.txt` | Shows first 20 characters           |
| `tail file.txt`       | Shows last 10 lines                 |
| `tail -c 20 file.txt` | Shows last 20 characters            |
| `wc file.txt`         | Counts words, lines, and characters |
| `file file.txt`       | Shows file type                     |

---

# Copy, Move, Rename & Delete

| Command                | Explanation                     |
| ---------------------- | ------------------------------- |
| `cp file newfile`      | Copies file                     |
| `cp -r dir copied_dir` | Copies directory recursively    |
| `mv oldfile newfile`   | Renames file                    |
| `mv file1 /path/file2` | Moves file                      |
| `rm file`              | Deletes file                    |
| `rmdir dir`            | Removes empty directory         |
| `rm -r dir`            | Deletes directory with contents |

---

# Disk Usage

| Command           | Explanation               |
| ----------------- | ------------------------- |
| `du file_name`    | Shows disk usage          |
| `du -h file_name` | Human-readable disk usage |

---

# Text Editors

| Command         | Explanation       |
| --------------- | ----------------- |
| `nano filename` | Opens Nano editor |
| `vim filename`  | Opens Vim editor  |

---

# Streams (Channels)

| Stream   | Meaning         |
| -------- | --------------- |
| `STDIN`  | Standard Input  |
| `STDOUT` | Standard Output |
| `STDERR` | Standard Error  |

---

# Redirection Operators

| Command | Explanation                 |
| ------- | --------------------------- |
| `>`     | Redirect output (overwrite) |
| `>>`    | Redirect output (append)    |
| `1>`    | Redirect standard output    |
| `1>>`   | Append standard output      |
| `2>`    | Redirect errors             |

## Examples

```bash
ls 1> hello.txt
```

Redirects output to file.

```bash
du -h file.txt 2> error.txt
```

Redirects errors to file.

```bash
ls > /dev/null
```

Discards output.

```bash
ls 2> /dev/null
```

Discards error messages.

---

# Piping

| Command                        | Explanation                         |                     |
| ------------------------------ | ----------------------------------- | ------------------- |
| `ls`                           | wc -l                              | Counts listed files |
| `cat file.txt \| grep "hello"` | Searches text in file               |                     |
| `tee file.txt`                 | Saves output and prints on terminal |                     |

## Example

```bash
cat file.txt | grep "hello" | tee result.txt
```

Searches and stores matching lines.

```bash
ping google.com | tee ping.txt
```

Stores ping output while displaying it.

---

# Environment Variables

| Command      | Explanation            |
| ------------ | ---------------------- |
| `echo $USER` | Displays current user  |
| `echo $HOME` | Displays home path     |
| `echo $PATH` | Displays PATH variable |

---

# Creating Environment Variables

```bash
export PORT_NO=5010
echo $PORT_NO
```

Creates and displays variable.

```bash
export HELLO="This is env content"
echo $HELLO
```

Creates string variable.

```bash
export HELLO="Hello, $USER"
echo $HELLO
```

Uses another variable inside value.

---

# Reassigning Variables

```bash
HELLO="Hello world"
echo $HELLO
```

Updates variable value.

---

# Globbing (Pattern Matching)

| Command                         | Explanation                         |
| ------------------------------- | ----------------------------------- |
| `ls *.txt`                      | Lists all `.txt` files              |
| `ls dir/*.txt`                  | Lists `.txt` files inside directory |
| `echo *.txt`                    | Expands matching files              |
| `echo '*.txt'`                  | Disables globbing                   |
| `echo file*`                    | Matches files starting with `file`  |
| `echo file.???`                 | Matches 3-character extensions      |
| `echo ?????.txt`                | Matches 5-character file names      |
| `echo img[0-9].[a-z][a-z][a-z]` | Matches patterns using ranges       |
| `echo dir/*.txt`                | Matches `.txt` files in directory   |
| `echo **/*.txt`                 | Recursive matching of `.txt` files  |

```
