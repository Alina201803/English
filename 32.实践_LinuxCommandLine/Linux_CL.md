



## Index

```python
['Part 1 – Learning The Shell',
 'Part 2 – Configuration And The Environment',
 'Part 3 – Common Tasks And Essential Tools',
 'Part 4 – Writing Shell Scripts',]
```





## Introduction

- **Freedom**

  Many people speak of “freedom” with regard to Linux, but I don't think most people know what this freedom really means. Freedom is the power to decide what your computer does, and the only way to have this freedom is to know what your computer is doing. Freedom is a computer that is without secrets, one where everything can be known if you care enough to find out. 


- **Why Use The Command Line?**

  It's been said that “graphical user interfaces make easy tasks easy, while command line interfaces make difficult tasks possible” and this is still very true today.





## Part 1 Learning The Shell



### 1. What is Shell

```python
[(0, 'Part 1 Learning The Shell'),
 'What Is The Shell' =  [(1, 'Terminal Emulators'),
                         (2, 'Your First Keystrokes'),
                         (3, 'Command History'),
                         (4, 'Cursor Movement'),
                         (5, 'A Few Words About Mice And Focus'),
                         (6, 'Try Some Simple Commands'),
                         (7, 'Ending A Terminal Session'),
                         (8, 'The Console Behind The Curtain'),
                         (9, 'Summing Up'),
                         (10, 'Further Reading')]
```

- **What is Shell?**

  [Shell (computing) - Wikipedia](https://en.wikipedia.org/wiki/Shell_(computing))

  When we speak of the command line, we are really referring to the shell. The shell is a program that takes keyboard commands and passes them to the operating system to carry out. Almost all Linux distributions supply a shell program from the GNU Project called bash. The name “bash” is an acronym for “Bourne Again SHell”, a reference to the fact **bash is an enhanced replacement for sh,** the original Unix shell program written by Steve Bourne.

- In [computing](https://en.wikipedia.org/wiki/Computing), a **shell** is a [user interface](https://en.wikipedia.org/wiki/User_interface) for access to an [operating system](https://en.wikipedia.org/wiki/Operating_system)'s services. In general, operating system shells use either a [command-line interface](https://en.wikipedia.org/wiki/Command-line_interface) (CLI) or [graphical user interface](https://en.wikipedia.org/wiki/Graphical_user_interface) (GUI), depending on a computer's role and particular operation. **It is named a shell because it is the outermost layer around the operating system [kernel](https://en.wikipedia.org/wiki/Kernel_(operating_system)).[[1\]](https://en.wikipedia.org/wiki/Shell_(computing)#cite_note-Economist-1)[[2\]****](https://en.wikipedia.org/wiki/Shell_(computing)#cite_note-JargonFile-2)**

- Kernel

- ​

- The **kernel** is a [computer program](https://en.wikipedia.org/wiki/Computer_program) that is the core of a computer's [operating system](https://en.wikipedia.org/wiki/Operating_system), with complete control over everything in the system.[[1\]](https://en.wikipedia.org/wiki/Kernel_(operating_system)#cite_note-Linfo-1) On most systems, it is one of the first programs loaded on [start-up](https://en.wikipedia.org/wiki/Booting) (after the [bootloader](https://en.wikipedia.org/wiki/Bootloader)). It handles the rest of start-up as well as [input/output](https://en.wikipedia.org/wiki/Input/output) requests from [software](https://en.wikipedia.org/wiki/Software), translating them into [data-processing](https://en.wikipedia.org/wiki/Data_processing)instructions for the [central processing unit](https://en.wikipedia.org/wiki/Central_processing_unit). It handles memory and [peripherals](https://en.wikipedia.org/wiki/Peripheral) like keyboards, monitors, printers, and speakers.

  <img src='https://upload.wikimedia.org/wikipedia/commons/thumb/8/8f/Kernel_Layout.svg/440px-Kernel_Layout.svg.png' style='zoom:50%'>

  ​

  ​

  ​

- Further Reading

  - To learn more about Steve Bourne, father of the Bourne Shell, see this Wikipedia article:
     http://en.wikipedia.org/wiki/Steve_Bourne
  - Here is an article about the concept of shells in computing: 
    http://en.wikipedia.org/wiki/Shell_(computing)

  ​

### 2. Navigation

The first thing we need to learn (besides just typing) is how to navigate the file system on our Linux system. In this chapter we will introduce the following commands:

1. pwd - Print name of current working directory

2. cd - Change directory

3. ls - List directory contents



#### Understanding the File System Tree

Like Windows, a Unix-like operating system such as Linux organizes its files in what is called a **hierarchical directory structure.** This means that they are organized in a tree-like pattern of directories (sometimes called folders in other systems), which may contain files and other directories. The first directory in the file system is called the root direc- tory. The root directory contains files and subdirectories, which contain more files and subdirectories and so on and so on.

Note that unlike Windows, which has a separate file system tree for each storage device, Unix-like systems such as Linux always have a single file system tree, regardless of how many drives or storage devices are attached to the computer. Storage devices are attached (or more correctly, mounted) at various points on the tree according to the whims of the system administrator, the person (or persons) responsible for the maintenance of the system.

> Mounted,
>
> [mount (Unix) - Wikipedia](https://en.wikipedia.org/wiki/Mount_(Unix))
>
> Before a user can access a [file](https://en.wikipedia.org/wiki/Computer_file) on a [Unix-like](https://en.wikipedia.org/wiki/Unix-like) machine, the [file system](https://en.wikipedia.org/wiki/File_system) that contains it needs to be mounted with the **mount** command. Frequently **mount** is used for [SD card](https://en.wikipedia.org/wiki/SD_card), [USB storage](https://en.wikipedia.org/wiki/USB_storage), [DVD](https://en.wikipedia.org/wiki/DVD) and other removable storage devices.
>
> The **mount** command instructs the [operating system](https://en.wikipedia.org/wiki/Operating_system) that a [file system](https://en.wikipedia.org/wiki/File_system) is ready to use, and associates it with a particular point in the overall file system hierarchy (its *mount point*) and sets options relating to its access. Mounting makes file systems, files, directories, devices and special files available for use and available to the user. Its counterpart **umount** instructs the operating system that the file system should be disassociated from its mount point, making it no longer accessible and may be removed from the computer. It is important to **umount** a device before removing it since changes to files may have only partially been written and are completed as part of the **umount**.
>
> The **mount** and **umount** commands require [root user](https://en.wikipedia.org/wiki/Root_user) privilege to effect changes. Alternately, specific privileges to perform the corresponding action may have been previously granted by the root user. A file system can be defined as user mountable in the `/etc/fstab` file by the root user.

#### The Current Working Directory

Imagine that the file system is a **maze** shaped like an upside-down tree and we are able to stand in the middle of it. At any given time, we are inside a single directory and we can see the files contained in the directory and the pathway to the directory above us (called the parent directory) and any subdirectories below us. The directory we are standing in is called the current working directory. To display the current working directory, we use the pwd (print working directory) command.

```python
pwd
```



#### Listing The Contents of A Direcotry

```python
ls
```



#### Changing The Current Working Directory

To change your working directory (where we are standing in **our tree-shaped maze**) we use the cd command. To do this, type cd followed by the pathname of the desired work- ing directory. A pathname is the route we take along the branches of the tree to get to the directory we want. Pathnames can be specified in one of two different ways; as absolute pathnames or as relative pathnames. Let's deal with absolute pathnames first.

- Absolute Pathnames
- Relative Pathnames





### 3. Exploring The System



Now that we know how to move around the file system, it's time for a guided tour of our Linux system. Before we start however, we’re going to learn some more commands that will be useful along the way:

1. ls – List directory contents

2. file – Determine file type

3. less – View file contents



#### More Fun With ls

- Options And Arguments
- A Longer Look At Long Format





#### Determine A File's Type With file

- **View Files Contens Wtih less**

  > **What Is “Text”?**
  >
  > There are many ways to represent information on a computer. All methods involve defining **a relationship between the information and some numbers that will be used to represent it**. Computers, after all, only understand numbers and all data is converted to numeric representation.
  >
  > Some of these representation systems are very complex (such as compressed video files), while others are rather simple. One of the earliest and simplest is called ASCII text. **ASCII** (pronounced "As-Key") is short for American Standard Code for Information Interchange. This is a simple encoding scheme that was first used on Teletype machines to **map keyboard characters to numbers.**
  >
  > **Text is a simple one-to-one mapping of characters to numbers.** It is very compact. Fifty characters of text translates to fifty bytes of data. It is important to understand that text only contains a simple mapping of characters to numbers. It is not the same as a word processor document such as one created by Microsoft Word or LibreOffice Writer. Those files, in contrast to simple ASCII text, contain many non-text elements that are used to describe its structure and formatting. Plain ASCII text files contain only the characters themselves and a few rudimentary control codes like tabs, carriage returns and line feeds.
  >
  > Throughout a Linux system, many files are stored in text format and there are many Linux tools that work with text files. Even Windows recognizes the importance of this format. The well-known NOTEPAD.EXE program is an editor for plain ASCII text files.

  - **Why would we want to examine text files?**

    Because many of the files that contain system settings (called configuration files) are stored in this format, and being able to read them gives us insight about how the system works. In addition, some of the actual programs that the system uses (called scripts) are stored in this format. In later chapters, we will learn how to edit text files in order to modify systems settings and write our own scripts, but for now we will just look at their contents.

  ​

  - Table 3-3: less Commands

    | Command            | Action                                                |
    | ------------------ | ----------------------------------------------------- |
    | Page Up or b       | Scroll back one page                                  |
    | Page Down or space | Scroll forward one page                               |
    | Up Arrow           | Scroll up one line                                    |
    | Down Arrow         | Scroll down one line                                  |
    | G                  | Move to the end of the text file                      |
    | 1G or g            | Move to the beginning of the text file                |
    | /characters        | Search forward to the next occurrence of characters   |
    | n                  | Search for the next occurrence of the previous search |
    | h                  | Display help screen                                   |
    | q                  | Quit less                                             |

> Less is more
>
> The less program was designed as an improved replacement of an earlier Unix program called more. The name “less” is a play on the phrase “less is more”—a motto of modernist architects and designers. less falls into the class of programs called “pagers,” programs that allow the easy viewing of long text documents in a page by page manner. Whereas the more program could only page forward, the less program allows paging both forward and backward and has many other features as well.

​     	 	

### 4. Manipulating Files and Dirctories

At this point, we are ready for some real work! This chapter will introduce the following commands:

1. cp – Copy files and directories
2. mv – Move/rename files and directories

3. mkdir – Create directories

4. rm – Remove files and directories

5. ln – Create hard and symbolic links


These five commands are among the most frequently used Linux commands. They are used for manipulating both files and directories.

- **Wildcards**

  Table 4-1 Wildcards

  | Wildcard      | Meaning                                                      |
  | ------------- | ------------------------------------------------------------ |
  | *             | Mathes any chracters                                         |
  | ?             | Matches any sigle character                                  |
  | [characters]  | Matches any character that is a member of the set characters |
  | [!characters] | Matches any character that is not a member of the set characters |
  | [[:class:]]   | Matches any character that is a member of the specified class |

- **Commonly Used Character Classes**

  | Character Class | Meaning                            |
  | --------------- | ---------------------------------- |
  | [:alnum:]       | Matches any alphanumeric character |
  | [:alpha:]       | Matches any alphabetic character   |
  | [:digit:]       | Matches any numeral                |
  | [:lower:]       | Matches any lowercase letter       |
  | [:upper:]       | Matches any uppercase letter       |

  Using wildcards makes it possible to construct very sophisticated selection criteria for filenames. Here are some examples of patterns and what they match:

-  *Table 4-3: Wildcard Examples*

  | Pattern                | Matches                                                      |
  | ---------------------- | ------------------------------------------------------------ |
  | *                      | All files                                                    |
  | g*                     | Any file beginning with “g”                                  |
  | b*.txt                 | Any file beginning with “b” followed by,any characters and ending with “.txt” |
  | Data???                | Any file beginning with “Data” followed, by exactly three characters |
  | [abc]*                 | Any file beginning with either an “a”, a “b”, or a “c”       |
  | BACKUP.[0-9][0-9][0-9] | Any file beginning with “BACKUP.”  followed by exactly three numerals |
  | [[:upper:]]*           | Any file beginning with an uppercase letter                  |
  | [![:digit:]]*          | Any file not beginning with a numeral                        |
  | *[[:lower:]123]        | Any file ending with a lowercase letter or  the numerals “1”, “2”, or “3” |

  **Wildcards** can be used with any command that accepts filenames as arguments, but we’ll talk more about that in Chapter 7.

- Creating Hard Links

   Now we'll try some links. First the hard links. We’ll create some links to our data file like




- **Create Links**

  ```python
  # the way to create links
  ln file link
  ln -s item link
  ```

  ```python
  #Hard links 
  $ln fun fun-hard
  $ ln fun dir1/fun-hard
  $ ln fun dir2/fun-hard
  # symbolic links
  # The first example is pretty straightforward, we simply add the “-s” option to create a symbolic link rather than a hard link. But what about the next two? Remember, when we create a symbolic link, we are creating a text description of where the target file is relative to the symbolic link. It's easier to see if we look at the ls output:
  $ ln -s fun fun-sym
  $ ln -s ../fun dir1/fun-sym
  $ ln -s ../fun dir2/fun-sym
  ```


- **Hard links**

  One thing you notice is that the second field in the listing for fun and fun-hard both contain a “4” which is the number of hard links that now exist for the file. You'll remem- ber that a file will always have at least one link because the file's name is created by a link. **So, how do we know that fun and fun-hard are, in fact, the same file?** In this case, ls is not very helpful. While we can see that fun and fun-hard are both the same size (field 5), our listing provides no way to be sure. To solve this problem, we're going to have to dig a little deeper.

  When thinking about hard links, it is helpful to imagine that files are made up of two parts: 

  - 1) the data part containing the file's contents 

  - 2) and the name part which holds the file's name. 

      hen we create hard links, we are actually creating additional name parts that all refer to the same data part. The system assigns a chain of disk blocks to what is called an inode, which is then associated with the name part. Each hard link therefore refers to a specific inode containing the file's contents. 

      ```python
      $ ls -li
      total 32
      8604514497 drwxr-xr-x  4 gaowei  staff   128 Mar 17 14:44 dir1
      8604514498 drwxr-xr-x  4 gaowei  staff   128 Mar 17 14:44 dir2
      8604514601 -rw-r--r--@ 4 gaowei  staff  6774 Mar 17 14:19 fun
      8604514601 -rw-r--r--@ 4 gaowei  staff  6774 Mar 17 14:19 fun-hard
      8604517186 lrwxr-xr-x  1 gaowei  staff     3 Mar 17 14:43 fun-sym -> fun
      # 8604514601 8604514601 the same file
      ```


- **Symbolic Links**

  The first example is pretty straightforward, we simply add the “-s” option to create a symbolic link rather than a hard link. But what about the next two? Remember, when we create a symbolic link, **we are creating a text description of where the target file is relative to the symbolic link.** It's easier to see if we look at the ls output:

  The listing for fun-sym in dir1 shows that it is a symbolic link by the **leading “l”** in the first field and that it points to “../fun”, which is correct. Relative to the location of fun-sym, fun is in the directory above it. **Notice too, that the length of the symbolic link file is 6,** the number of characters in the string “../fun” rather than the length of the file to which it is pointing. 	 	




- **Further Reading**
  - A discussion of symbolic links: http://en.wikipedia.org/wiki/Symbolic_link

  ​



### 5. Working With Commands

Up to this point, we have seen a series of mysterious commands, each with its own mysterious options and arguments. In this chapter, we will attempt to remove some of that mystery and even create some of our own commands. The commands introduced in this chapter are:

1. type – Indicate how a command name is interpreted
2. which – Display which executable program will be executed
3. help – Get help for shell builtins
4. man – Display a command's manual page
5. apropos – Display a list of appropriate commands
6. info – Display a command's info entry
7. whatis – Display a very brief description of a command
8. alias – Create an alias for a command




#### What Exactly Are Commands?

A command can be one of four different things:

1. **An executable program** like all those files we saw in /usr/bin. Within this category, programs can be compiled binaries such as programs written in C and C++, or programs written in scripting languages such as the shell, perl, python, ruby, etc.

2. A command built into the shell itself. bash supports a number of commands in- ternally called shell builtins. The cd command, for example, is a shell builtin.

3. A shell function. These are miniature shell scripts incorporated into the environ- ment. We will cover configuring the environment and writing shell functions in later chapters, but for now, just be aware that they exist.

4. An alias. Commands that we can define ourselves, **built from other commands.**

   ​

#### Identifying Commands

- **type - Display A Command's Type**

  ```python
  # The type command is a shell builtin that displays the kind of command the shell will execute, given a particular command name. It works like this:

  gaowei at Max-2018 in ~/desktop/playground
  $ type ls
  ls is aliased to `command ls -G'
  gaowei at Max-2018 in ~/desktop/playground
  $ command ls -G
  dir1     dir1-sym dir2     fun-sym
  ```

- which - Display An Execuable's Location

  ```python
  # Sometimes there is more than one version of an executable program installed on a system. While this is not very common on desktop systems, it's not unusual on large servers. To determine the exact location of a given executable, the which command is used:
  gaowei at Max-2018 in ~/desktop/playground
  $ which ls
  /bin/ls
  gaowei at Max-2018 in ~/desktop/playground
  $ which cd
  /usr/bin/cd
  ```

- **help - Get Help For Shell Builtins**

  ```python
  cd: cd [-L|-P] [dir]
      Change the current directory to DIR.  The variable $HOME is the
      default DIR.  The variable CDPATH defines the search path for
      the directory containing DIR.  Alternative directory names in CDPATH
      are separated by a colon (:).  A null directory name is the same as
      the current directory, i.e. `.'.  If DIR begins with a slash (/),
      then CDPATH is not used.  If the directory is not found, and the
      shell option `cdable_vars' is set, then try the word as a variable
      name.  If that variable has a value, then cd to the value of that
      variable.  The -P option says to use the physical directory structure
      instead of following symbolic links; the -L option forces symbolic links
      to be followed.
  ```

  - A Note on notation:

    When square brackets appear in the description of a command's syn- tax, they indicate optional items. A vertical bar character indicates **mutually exclusive items**. In the case of the cd command above:

    `cd [-L|[-P[-e]]][dir] `

    This notation says that the command cd may be followed optionally by either a “-L” or a “-P” and further, if the “-P” option is specified the “-e” option may also be included fol- lowed by the optional argument “dir”.

    While the output of help for the cd commands is concise and accurate, it is by no means tutorial and as we can see, it also seems to mention a lot of things we haven't talked about yet! Don't worry. We'll get there.

- **--help – Display Usage Information**

  ```python
  $ ls --help
  ls: illegal option -- -
  usage: ls [-ABCFGHLOPRSTUWabcdefghiklmnopqrstuwx1] [file ...]
  ```

- man -Display A Program's Manual Page

  `man program`

  where “program” is the name of the command to view. Man pages vary somewhat in format but generally contain a title, a synopsis of the com- mand's syntax, a description of the command's purpose, and a listing and description of each of the command's options. Man pages, however, do not usually include examples, and are intended as a reference, not a tutorial. As an example, let's try viewing the man page for the ls command:

- **apropos – Display Appropriate Commands**

- **whatis – Display A Very Brief Description Of A Command**

  - The Most Brutal Man Page Of Them All

    As we have seen, the manual pages supplied with Linux and other Unix-like sys- tems are intended as reference documentation and not as tutorials. Many man pages are hard to read, but I think that the grand prize for difficulty has got to go to the man page for bash. As I was doing my research for this book, I gave it careful review to ensure that I was covering most of its topics. When printed, it's over 80 pages long and extremely dense, and its structure makes absolutely no sense to a new user.

    On the other hand, it is very accurate and concise, as well as being extremely complete. So check it out if you dare

  ​

#### Creating Your Own Commands With Alias

```python
$ alias foo='cd /usr; ls;cd -'
$ alias name='string'
$ unalias foo
```



- Summing Up

  Further Reading

  There are many online sources of documentation for Linux and the command line. Here are some of the best:

  - The Bash Reference Manual is a reference guide to the bash shell. It’s still a ref- erence work but contains examples and is easier to read than the bash man page. http://www.gnu.org/software/bash/manual/bashref.html
  - The Bash FAQ contains answers to frequently asked questions regarding bash. This list is aimed at intermediate to advanced users, but contains a lot of good in- formation. http://mywiki.wooledge.org/BashFAQ
  - The GNU Project provides extensive documentation for its programs, which form the core of the Linux command line experience. You can see a complete list here: http://www.gnu.org/manual/manual.html
  - Wikipedia has an interesting article on man pages: http://en.wikipedia.org/wiki/Man_page

### 6.Redirection

- In this lesson we are going to unleash what may be the coolest feature of the command line. It's called I/O redirection. The “I/O” stands for input/output and with this facility you can redirect the input and output of commands to and from files, as well as connect multiple commands together into powerful command pipelines. To show off this facility, we will introduce the following commands:

  ```python
  1. cat - Concatenate files
  2. sort - Sort lines of text
  3. uniq - Report or omit repeated lines
  4. grep - Print lines matching a pattern
  5. wc - Print newline, word, and byte counts for each file
  6. head - Output the first part of a file
  7. tail - Output the last part of a file
  8. tee - Read from standard input and write to standard output and files
  ```

  ​

  #### Standard Input, Output, and Error

  Keeping with the Unix theme of “everything is a file,” programs such as ls actually send their results to a special file called standard output (often expressed as stdout) and their status messages to another file called standard error (stderr). By default, both standard output and standard error are linked to the screen and not saved into a disk file.

  I/O redirection allows us to change where output goes and where input comes from. **Normally, output goes to the screen** and input comes from the keyboard, but with I/O redi- rection, we can change that.



#### Redirecting Standard Output

```python
# Redirect
$ ls -l /usr/bin > ls_output.mc
# Error and truncate
$ ls -l /bin/usr > ls_output.txt
ls: /bin/usr: No such file or directory
#Append
$ ls -l /usr/bin >> ls_output.md
```

We repeated the command three times resulting in an output file three times as large.



#### Redirect Standard Errors

- A file descriptor

  To redirect standard error we must refer to its **file descriptor.** A program can produce output on any of several numbered file streams. While we have referred to the first three of these file streams as standard input, output and error, the shell references them **internally as file descriptors 0, 1 and 2, respectively.** The shell provides a notation for redirecting files using the file descriptor number. Since standard error is the same as file descriptor number 2, we can redirect standard error with this notation:

```python
$ ls -l /bin/usr 2> ls_error.md
# The file descriptor “2” is placed immediately before the redirection operator to perform the redirection of standard error to the file ls-error.txt.

# Redirect Standard Output and Standard Error to One File
$ ls -l /bin/usr > ls_output.md 2>&1
#&1是合并到1的意思

#dispoing of Unwanted Output
```

> **/dev/null In Unix Culture**
>
> The bit bucket is an ancient Unix concept and due to its universality, it has ap- peared in many parts of Unix culture. When someone says he/she is sending your comments to /dev/null, now you know what it means. For more examples, see the Wikipedia article on “/dev/null”.



#### Redict Standard Input

- Cat Concatenate Files

```python
# concatenate
cat file1 file2 > file3
# cat accepts standard input
$ cat > lazy_dog.md
The quick brown fox jumped over the lazy dog.^D  
# 
```



#### Pipelines

Remember how we said there was one we already knew **that accepts standard input? It's less.** We can use less to display, page-by-page, the output of any command that sends its results to standard output:

```python
$ tree -d | less
```

> **The Difference Between > and |**
>
> At first glance, it may be hard to understand the redirection performed by the pipeline operator | versus the redirection operator >. Simply put, the redirection operator connects a command with a file while the pipeline operator connects the output of one command with the input of a second command.
>
> ```shell
> command1 > file1 
> command1 | command2 
> ```
>
> A lot of people will try the following when they are learning about pipelines, “just to see what happens.”
>
> command1 > command2 Answer: Sometimes something really bad.

- **Filters**

  ```python
  ls /bin /usr/bin | sort | les
  ```



- **uniq - Report Or Omit Repeated Lines**

  ```python
  $ ls /bin /usr/bin | sort | uniq | less
  $ ls /bin /usr/bin | sort | uniq -d | less
  ```

  ​

- wc – Print Line, Word, And Byte Counts

  The wc (word count) command is used to display the number of lines, words, and bytes contained in files. For example:

  ```python
  $ ls /bin /usr/bin | sort | uniq | wc -l
      1012
  $ ls /bin /usr/bin | sort | uniq | wc 
      1012    1011    8327
  ```

  ​

- grep — Print Lines Matching A Pattern

  **grep** is a [command-line](https://en.wikipedia.org/wiki/Command_line_interface) utility for searching plain-text data sets for lines that match a [regular expression](https://en.wikipedia.org/wiki/Regular_expression). Its name comes from the [ed](https://en.wikipedia.org/wiki/Ed_(text_editor)) command *g/re/p* (**\*g**lobally search a **r**egular **e**xpression and **p**rint*), which has the same effect: doing a global search with the regular expression and printing all matching lines.[[3\]](https://en.wikipedia.org/wiki/Grep#cite_note-3)[[4\]](https://en.wikipedia.org/wiki/Grep#cite_note-etymology-4) Grep was originally developed for the [Unix](https://en.wikipedia.org/wiki/Unix) operating system, but later available for all [Unix-like](https://en.wikipedia.org/wiki/Unix-like) systems.

  ```shell
  $ ls /bin /usr/bin | sort | uniq | grep zip
  bunzip2
  bzip2
  bzip2recover
  funzip
  gunzip
  gzip
  ```

  There are a couple of handy options for grep: “-i” which causes grep to ignore case when performing the search (normally searches are case sensitive) and “-v” which tells grep to only print lines that do not match the pattern.

  ​

- **Head and tail**

  ```python
  tail -f /var/log/system.log
  ```

  Using the “-f” option, tail continues to monitor the file and when new lines are ap- pended, they immediately appear on the display. This continues until you type Ctrl-c.



- **tee — Read From Stdin and Output to Stout And Files**

  ```python
  $ ls /usr/bin | tee ls.md | grep zip
  bunzip2
  bzip2
  bzip2recover
  funzip
  gunzip
  gzip
  unzip
  unzipsfx
  zip
  zipcloak
  zipdetails
  zipdetails5.18
  zipgrep
  zipinfo
  zipnote
  zipsplit
  ```



#### **Summing Up**

  As always, check out the documentation of each of the commands we have covered in this chapter. We have only seen their most basic usage. They all have a number of inter- esting options. As we gain Linux experience, we will see that the redirection feature of the command line is extremely useful for solving specialized problems. There are many commands that make use of standard input and output, and almost all command line pro- grams use standard error to display their informative messages.

  ​

- **Linux Is About  Imagination**

  When I am asked to explain the difference between Windows and Linux, I often use a **toy analogy**.

  Windows is like a Game Boy. 

  <img src='https://cdn.thisiswhyimbroke.com/images/nintendo-game-boy-notebook-thinkgeek1-300x250.jpg' style='zoom:80%'>

  You go to the store and buy one all shiny new in the box. You take it home, turn it on and play with it. Pretty graphics, cute sounds. After a while though, you get tired of the game that **came with it** so you go back to the store and buy another one. This cycle repeats over and over. Finally, you go back to the store and say to the person behind the counter, “I want a game that does this!” only to be told that no such game exists because there is no “market demand” for it. Then you say, “But I only need to change this one thing!” The person behind the counter says you can't change it. The games are all **sealed up** in their cartridges. You discover that your toy is limited to the games that others have decided that you need and no more.

  Linux, on the other hand, is like the world's largest Erector Set. 

  <img src='https://images-na.ssl-images-amazon.com/images/I/61oNH948JuL._SL500_AC_SS350_.jpg' style='zoom:100%'>

  You open it up and it's just a huge collection of parts. A lot of steel struts, screws, nuts, gears, pulleys, motors, and a few suggestions on what to build. So you start to play with it. You build one of the suggestions and then another. After a while you discover that you have your own ideas of what to make. You don't ever have to go back to the store, as you already have everything you need. The Erector Set takes on the shape of your imagination. It does what you want.

  Your choice of toys is, of course, a personal thing, so which toy would you find more satisfying?

  ​


### 7. Seeing The World As The Shell Sees It



In this chapter we are going to look at some of the “magic” that occurs on the command line when we press the enter key. While we will examine several interesting and complex features of the shell, we will do it with just one new command:

- echo -Display a line of text


#### Expansion

```python
$ echo *
Cheatsheet Coding Homework PriRepo Principles PubRepo Work Xmind english ls.md
```

So what just happened? Why didn't echo print “*”? As we recall from our work with wildcards, the “*” character means match any characters in a filename, but what we didn't see in our original discussion was how the shell does that. The simple answer is that the shell expands the `*` into something else (in this instance, the names of the files in the current working directory) before the echo command is executed. When the enter key is pressed, the shell automatically expands any qualifying characters on the command line before the command is carried out, so the echo command never saw the `*`, only its expanded result. Knowing this, we can see that echo behaved as expected.

- Pathname Expansion

```python
    gaowei at Max-2018 in ~/desktop
    $ ls
    Cheatsheet Homework   Principles Work       english
    Coding     PriRepo    PubRepo    Xmind      ls.md

    gaowei at Max-2018 in ~/desktop
    $ echo H*
    Homework

    gaowei at Max-2018 in ~/desktop
    $ echo *s
    Principles

    gaowei at Max-2018 in ~/desktop
    $ echo [A-Z]*
    Cheatsheet Coding Homework PriRepo Principles PubRepo Work Xmind english ls.md

    gaowei at Max-2018 in ~/desktop
    $ echo /usr/*/share
    /usr/local/share
```

- Pathnames Expansion Of Hidden Files

  As we know, filenames that begin with a period character are hidden. Pathname expansion also respects this behavior. An expansion such as:

  `echo *`

  does not reveal hidden files.

  It might appear at first glance that we could include hidden files in an expansion by starting the pattern with a leading period, like this:

  `echo .*`

  It almost works. However, if we examine the results closely, we will see that the names “.” and “..” will also appear in the results. Since these names refer to the current working directory and its parent directory, using this pattern will likely produce an incorrect result. We can see this if we try the command:

  `ls -d .* | less`

  To better perform pathname expansion in this situation, we have to employ a more specific pattern:

  `echo .[!.]*`

  This pattern expands into every filename that begins with a period, does not in- clude a second period, and followed by any other characters. This will work cor- rectly with most hidden files (though it still won't include filenames with multiple leading periods). The ls command with the -A option (“almost all”) will provide a correct listing of hidden files:

  `ls -A`

  ​

-  **Tilde Expansion**

```shell
gaowei at Max-2018 in ~/desktop
$ echo ~
/Users/gaowei
```



- **Arithmetic Expansion**

  Arithmetic expansion uses the form: 

  `$((expression))`

  `echo $((2 + 2))`

  ***Table 7-1: Arithmetic Operators***

  | Operator | Description                                                  |
  | -------- | ------------------------------------------------------------ |
  | +        | Addition                                                     |
  | -        | Subtraction                                                  |
  | *        | Multiplication                                               |
  | /        | Division (but remember, since expansion only supports integer, arithmetic, results are integers). |
  | %        | Modulo, which simply means, “ remainder.”                    |
  | **       | Exponentiation                                               |

  ```python
  $ echo Five divided by two equals $((5/2))
  Five divided by two equals 2
  $ echo with $((5%2)) left over
  with 1 left over
  ```

- **Brace Expansion**

  ```python
  # a range of letters in reversed order:
  $ echo {Z..A}
  Z Y X W V U T S R Q P O N M L K J I H G F E D C B A
  #Brace expansions my be nested
  gaowei at Max-2018 in ~/desktop
  $ echo a{A{1,2}, B{3,4}}b
  a{A1, a{A2, B3}b B4}b
  #以上是错误的案例, 注意中间不能有空格.
  $ echo a{A{1,2},B{3,4}}b
  aA1b aA2b aB3b aB4b
  #create multiple files
  $ echo {2007..2009}-{1..12}
  2007-1 2007-2 2007-3 2007-4 2007-5 2007-6 2007-7 2007-8 2007-9 2007-10 2007-11 2007-12 2008-1 2008-2 2008-3 2008-4 2008-5 2008-6 2008-7 2008-8 2008-9 2008-10 2008-11 2008-12 2009-1 2009-2 2009-3 2009-4 2009-5 2009-6 2009-7 2009-8 2009-9 2009-10 2009-11 2009-12
  ```

  ​

- **Parameter Expansion**

  ```python
  $ echo $USER
  gaowei
  $ printenv | less
  ```

  ​

- **Command Substitution**

  Command substitution allows us to use the output of a command as an expansion:

  ```python
  $ echo $(ls)
  Cheatsheet Coding Homework PriRepo Principles PubRepo Work Xmind english ls.md
  $ ls -l $(which cp)
  -rwxr-xr-x  1 root  wheel  29008 Sep 21 12:35 /bin/cp
  $ file $(ls -d /usr/bin/* | grep zip)
  /usr/bin/bunzip2:        Mach-O 64-bit executable x86_64
  /usr/bin/bzip2:          Mach-O 64-bit executable x86_64
  /usr/bin/bzip2recover:   Mach-O 64-bit executable x86_64
  /usr/bin/funzip:         Mach-O 64-bit executable x86_64
  /usr/bin/gunzip:         Mach-O 64-bit executable x86_64
  /usr/bin/gzip:           Mach-O 64-bit executable x86_64
  /usr/bin/unzip:          Mach-O 64-bit executable x86_64
  /usr/bin/unzipsfx:       Mach-O 64-bit executable x86_64
  /usr/bin/zip:            Mach-O 64-bit executable x86_64
  /usr/bin/zipcloak:       Mach-O 64-bit executable x86_64
  /usr/bin/zipdetails:     Perl script text executable
  /usr/bin/zipdetails5.18: Perl script text executable
  /usr/bin/zipgrep:        POSIX shell script text executable, ASCII text
  /usr/bin/zipinfo:        Mach-O 64-bit executable x86_64
  /usr/bin/zipnote:        Mach-O 64-bit executable x86_64
  /usr/bin/zipsplit:       Mach-O 64-bit executable x86_64
  $ ls -l `which cp`
  -rwxr-xr-x  1 root  wheel  29008 Sep 21 12:35 /bin/cp
  ```



#### Quoting

  Now that we've seen how many ways the shell can perform expansions, it's time to learn how we can control it. Take for example:

- Double Quotes

  Remember, **parameter expansion, arithmetic expansion, and command substitution** still take place within double quotes:

  ```python
  gaowei at Max-2018 in ~/desktop/english on master [!]
  $ echo "$USER $((2+2)) $(cal)"
  gaowei 4      March 2018       
  Su Mo Tu We Th Fr Sa  
               1  2  3  
   4  5  6  7  8  9 10  
  11 12 13 14 15 16 17  
  18 19 20 21 22 23 24  
  25 26 27 28 29 30 31  
  ```

  - Word Splitting 

    By default, word-splitting looks for the presence of **spaces, tabs, and newlines (linefeed characters)** and treats them as delimiters between words. This means that unquoted spaces, tabs, and newlines are not considered to be part of the text. They only serve as separators. Since they separate the words into different arguments, our example command line contains a command followed by four distinct arguments. If we add double quotes:

    word-splitting is suppressed and the embedded spaces are not treated as delimiters, rather they become part of the argument. Once the double quotes are added, our command line contains a command followed by a single argument.

    The fact that newlines are considered delimiters by the word-splitting mechanism causes.

    ```python
    #In the first instance, the unquoted command substitution resulted in a command line containing 38 arguments.
    $ echo $(cal)
    March 2018 Su Mo Tu We Th Fr Sa 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30 31
    #In the second, a command line with one argument that includes the embedded spaces and newlines.
    $ echo "$(cal)"
         March 2018       
    Su Mo Tu We Th Fr Sa  
                 1  2  3  
     4  5  6  7  8  9 10  
    11 12 13 14 15 16 17  
    18 19 20 21 22 23 24  
    25 26 27 28 29 30 31
    ```

- Single Quote

  In the second, a command line with one argument that includes the embedded spaces and newlines.

  ```python
  # Unquoted 
  $ echo text ~/*.txt {a,b} $(echo foo) $((2+2)) $USER
  text /Users/gaowei/*.txt a b foo 4 gaowei

  #double quoted
  $ echo "text ~/*.txt {a,b} $(echo foo) $((2+2)) $USER"
  text ~/*.txt {a,b} foo 4 gaowei

  #single quoted
  $ echo 'text ~/*.txt {a,b} $(echo foo) $((2+2)) $USER'
  text ~/*.txt {a,b} $(echo foo) $((2+2)) $USER
  ```

- Escaping **Character**

  Sometimes we only want to quote a single character. To do this, we can precede a charac- ter with a backslash, which in this context is called the escape character. Often this is done inside double quotes to selectively prevent an expansion:

  ```python
  $ echo "The balance for user $USER is: \$5.00"
  The balance for user gaowei is: $5.00
  ```

  > **Control Code**
  >
  > | Escape Sequence | Meaning                                                  |
  > | --------------- | -------------------------------------------------------- |
  > | \a              | Bell (“Alert” - causes the computer to beep)             |
  > | \b              | Backspace                                                |
  > | \n              | Newline. On Unix-like systems, this produces a linefeed. |
  > | \r              | Carriage return                                          |
  > | \t              | tab                                                      |
  >
  > Adding the “-e” option to echo will enable interpretation of escape sequences. You may also place them inside $' '. Here, using the sleep command, a sim- ple program that just waits for the specified number of seconds and then exits, we can create a primitive countdown timer:
  >
  > ```python
  > $ sleep 10; echo -e "Time's up \a"
  > $ sleep 10; echo "Time's up" $"\a"
  > ```
  >
  > ​

#### Summing UP

  As we move forward with using the shell, 

  we will find that expansions and quoting will be used with increasing frequency, so it makes sense to get a good understanding of the way they work. In fact, it could be argued that they are the most important subjects to learn about the shell. Without a proper understanding of expansion, the shell will always be a source of mystery and confusion, and much of its potential power wasted.


  #### Further Reading

- The bash man page has major sections on both expansion and quoting which cover these topics in a more formal manner.
- The Bash Reference Manual also contains chapters on expansion and quoting: http://www.gnu.org/software/bash/manual/bashref.html



### 8. Advanced Keyboard Tricks

I often kiddingly describe Unix as “the operating system for people who like to type.” Of course, the fact that it even has a command line is a testament to that. But command line users don't like to type that much. Why else would so many commands have such short names like cp, ls, mv, and rm? In fact, one of the most cherished goals of the command line is laziness; doing the most work with the fewest number of keystrokes. Another goal is never having to lift your fingers from the keyboard, never reaching for the mouse. In this chapter, we will look at bash features that make keyboard use faster and more effi- cient.

The following commands will make an appearance:

1. clear – Clear the screen

2. history – Display the contents of the history list


#### Command line Editing

- Cursor Movement

- Text Editing Commands

- Cut and Paste Command

  ​

#### Completion

- Tab



#### Using History

```python
$ history | less
$ history | grep /usr/bin
```





### 9. Permissions

In this chapter we are going to look at this essential part of system security and introduce the following commands:

1. id – Display user identity

2. chmod – Change a file's mode

3. umask – Set the default file permissions

4. su – Run a shell as another user

5. sudo – Execute a command as another user

6. chown – Change a file's owner
7. chgrp – Change a file's group ownership

8. passwd – Change a user's password

#### Owners, Group Members, And Everybody Else



#### Reading, Writing, And Executing

- chmod - Change File Mode



- umask

  [umask - Wikipedia](https://en.wikipedia.org/wiki/Umask)

  In computing, **umask** is a command that determines the settings of a [mask](https://en.wikipedia.org/wiki/Mask_(computing)) that controls how [file permissions](https://en.wikipedia.org/wiki/File_permissions) are set for newly created files. It also may refer to a [function](https://en.wikipedia.org/wiki/Function_(computing)) that sets the mask, or it may refer to the mask itself, which is formally known as the **\*file mode creation mask***. The mask is a grouping of [bits](https://en.wikipedia.org/wiki/Bit), each of which restricts how its corresponding permission is set for newly created files. The bits in the mask may be changed by invoking the **umask** command.



- Setting File Mode With GUI




#### Change identities 

/etc/ edit to configure



### 10. Process



This chapter will introduce the following commands:

1. ps – Report a snapshot of current processes

2. top – Display tasks

3. jobs – List active jobs

4. bg – Place a job in the background

5. fg – Place a job in the foreground

6. kill – Send a signal to a process

7. killall – Kill processes by name

8. shutdown – Shutdown or reboot the system



#### How A Process Work

- View Processes

  ```python
  $ ps
    PID TTY           TIME CMD
    728 ttys000    0:00.44 -bash
  #  tty is short for teletype
  ```

  - Table 10-1 Process state

  ​

#### View Processes Dynamically with top

swap vitual  memory



#### Controlling Processes



- Interrupting a Process



- Putting a Process in the Background

  ```python
  xlogo &
  #& 这里的&显然是表示链接的
  ```

- Returing A Process to The Foreground

  ```python
  jobs
  fg % 
  ```

#### Signals








## Part 2 Configuration  And The Environment







## Part 3 Common Task and Essential Tools





## Part 4 Writing Shell Scripts







## Vocabulary

- **inode** [inode - Wikipedia](https://en.wikipedia.org/wiki/Inode)

  The **inode** is a [data structure](https://en.wikipedia.org/wiki/Data_structure) in a [Unix-style file system](https://en.wikipedia.org/wiki/Unix_filesystem) that describes a [filesystem](https://en.wikipedia.org/wiki/Filesystem) object such as a [file](https://en.wikipedia.org/wiki/Computer_file) or a [directory](https://en.wikipedia.org/wiki/Directory_(computing)). Each inode stores the attributes and disk block location(s) of the object's data.[[1\]](https://en.wikipedia.org/wiki/Inode#cite_note-1) Filesystem object attributes may include [metadata](https://en.wikipedia.org/wiki/Metadata) (times of last change,[[2\]](https://en.wikipedia.org/wiki/Inode#cite_note-2) access, modification), as well as owner and [permission](https://en.wikipedia.org/wiki/File_system_permissions) data.[[3\]](https://en.wikipedia.org/wiki/Inode#cite_note-3)

  Directories are lists of names assigned to inodes. A directory contains an entry for itself, its parent, and each of its children.

  An *inode* is a [*data structure*](http://www.linfo.org/data_structure.html) on a [*filesystem*](http://www.linfo.org/filesystem.html) on [Linux](http://www.linfo.org/linuxdef.html) and other [Unix-like](http://www.linfo.org/unix-like.html) [operating systems](http://www.linfo.org/operating_system.html) that stores all the [information](http://www.linfo.org/information.html) about a [*file*](http://www.linfo.org/file.html) except its name and its actual [data](http://www.linfo.org/data.html).

  A data structure is a way of storing data so that it can be used efficiently. Different types of data structures are suited to different types of applications, and some are highly specialized for specific types of tasks.

  ​

**Symbol** /ˈsɪm.bəl/

1. 助记,

   Sym(together) + bol(throw)

   from assimilated form of syn- "together" (see [syn-](https://www.etymonline.com/word/syn-?ref=etymonline_crossreference)) + bole "a throwing, a casting, the stroke of a missile, bolt, beam,"

   象征就是被扔出来,代表一个整合的概念.

   比如'自由女神'是自由的象征,她不是自由本身, 是被扔出来代表自由这个整合概念.

2. 词源,

   **Origin**

   Late Middle English (denoting the Apostles' Creed): from Latin symbolum ‘symbol, Creed (as the mark of a Christian)’, from Greek sumbolon ‘mark, token’, **from sun- ‘with’ + ballein ‘to throw’.**

   **Etymology**

   early 15c., "creed, summary, religious belief," from Late Latin symbolum "creed, token, mark," from Greek symbolon "token, watchword, sign by which one infers; ticket, a permit, licence" (the word was applied c.250 by Cyprian of Carthage to the Apostles' Creed, on the notion of the "mark" that distinguishes Christians from pagans), literally "that which is thrown or cast together," **from assimilated form of syn- "together" (see [syn-](https://www.etymonline.com/word/syn-?ref=etymonline_crossreference)) + bole "a throwing, a casting, the stroke of a missile, bolt, beam,"** from bol-, nominative stem of ballein "to throw" (from PIE root [*gwele-](https://www.etymonline.com/word/*gwele-?ref=etymonline_crossreference) "to throw, reach").The sense evolution in Greek is from "throwing things together" to "contrasting" to "comparing" to "token used in comparisons to determine if something is genuine." Hence, "outward sign" of something. The meaning "something which stands for something else" first recorded 1590 (in "Faerie Queene"). As a written character, 1610s.

3. 释义,

   1) 标志，象征 **a sign, shape, or object that is used to represent something else**

   ​


**Ball** /bɑːl/ 舞会

1. 助记,

   Ball 舞会

2. 词源

   **Origin**

   Early 17th century: from French bal ‘a dance’, from late Latin ballare ‘to dance’; related to Greek ballizein ‘to dance’ (also ballein ‘to throw’).

   **Etymology**

   "dancing party, social assembly for dancing," 1630s, from French, from Old French baller "to dance," from Late Latin ballare "to dance," from Greek ballizein "to dance, jump about," literally "to throw one's body" (ancient Greek dancing being highly athletic), from PIE root [*gwele-](https://www.etymonline.com/word/*gwele-?ref=etymonline_crossreference) "to throw, reach." Extended meaning "very enjoyable time" is American English slang from 1945, perhaps 1930s in African-American vernacular.

3. 释义,

   1) 舞会a large formal occasion where people dance


**Ballet** /bælˈeɪ/ 芭蕾舞

1. 助记,

   Late Latin ballare "to dance," 

   词根from PIE root [*gwele-](https://www.etymonline.com/word/*gwele-?ref=etymonline_crossreference) "to throw, reach."

   跳舞就是伸胳膊伸腿

   ball, 舞会, from French bal ‘a dance’, from late Latin ballare ‘to dance’

   ​

2. 词源,

   **OED Origin**

   Mid 17th century: from French, from Italian balletto, **diminutive of ballo ‘a dance’**, from late Latin ballare ‘to dance’ (see ball).


   **Etymology**

   "theatrical, costumed dance and pantomime performance telling a story and representing characters and passions by gestures and groupings," 1660s, from French ballette from Italian balletto, diminutive of **ballo "a dance,"** from Late Latin ballare "to dance," from Greek ballizein "to dance, jump about" (see [ball](https://www.etymonline.com/word/ball?ref=etymonline_crossreference) (n.2)).

3. 释义

   1) 芭蕾舞；芭蕾舞剧a type of dancing where carefully organized movements tell a story or expressan idea, or a theatre work that uses this type of dancing


**Problem** /ˈprɑː.bləm/

1. 助记,
  Pro(towards, forwards) + blem(ball), 

  Problem = to throw, throw forwards

  因此Problem不是前进障碍, 而是前进的哨兵,

  problem是主动扔出去的, 投石问路, 是往前走的抓手.

  另外对待,problem(to throw, to dance),要抱着跳舞💃的心态.

   解释, Problem is “A difficult question proposed for solution,"

2. 词源, 
   From pro "forward" (from PIE root *per- (1) "forward”, before,) + **ballein "to throw**" (from PIE root *gwele- "to throw, reach").
   与ball(舞蹈)同一词根, 从球引申为 to throw
   可以理解为,摆在眼前的一只球,等我去踢.并且是摆放在我和解决方案面前的一只球.
   **Origin**
   Late Middle English (originally denoting a riddle or a question for academic discussion): from Old French probleme, via Latin from Greek problēma, from proballein ‘put forth’, from pro ‘before’ + ballein ‘to throw’.
   **Etymology**
   late 14c., "a difficult question proposed for solution," from Old French problème (14c.) and directly from Latin problema, from Greek problema "a task, that which is proposed, a question;" also "anything projecting, headland, promontory; fence, barrier;" also "a problem in geometry," literally "thing put forward," from proballein "propose," from pro "forward" (from PIE root *per- (1) "forward") + ballein "to throw" (from PIE root ***gwele**- "to throw, reach").
   ***gwele-**
   *gwelə-, also *gwel-, Proto-Indo-European root meaning **"to throw, reach**," with extended sense "to pierce."
   It forms all or part of: anabolic; arbalest; astrobleme; **ball (n.2) "dancing party;**" ballad; ballet; ballista; ballistic; ballistics; belemnite; catabolism; devil; diabolical; discobolus; emblem; embolism; hyperbola; hyperbole; kill (v.); metabolism; palaver; parable; parabola; parley; parliament; parlor; parol; parole; problem; quell; quail (v.) "lose heart, shrink, cower;" 
   .
   It is the hypothetical source of/evidence for its existence is provided by: Sanskrit apa-gurya "swinging," balbaliti "whirls, twirls;" Greek ballein "to throw, to throw so as to hit," also in a looser sense, "to put, place, lay," bole "a throw, beam, ray," belemnon "dart, javelin," belone "needle," ballizein "to dance;" Armenian kelem "I torture;" Old Church Slavonic zali "pain;" Lithuanian galas "end," gėla "agony," gelti "to sting."

3. 释义
  1) 困难, trouble
  2) 问题, question



**Alias** /ˈeɪ.li.əs/ 别名

1. 助记,

   Alias,  alter, alternative name

2. 词源,

   **OED Origin**

   Late Middle English: from Latin, ‘at another time, otherwise’.

   **Etymology**

   mid-15c., "otherwise called," from Latin alias (adv.) "at another time," in Late Latin also "in another way, under other circumstances," from alius "another, other, different," from PIE root [*al-](https://www.etymonline.com/word/*al-?ref=etymonline_crossreference) (1) "beyond," which is the source also of English [else](https://www.etymonline.com/word/else?ref=etymonline_crossreference).

3. 释义,

   1) used when giving the name that a person is generally known by, after giving theirreal name

4. 拓展,

   Alter, Alternative

**Else **/els/ 

1. 助记,

2. 词源,

   **Origin**

   Old English elles, of Germanic origin; related to Middle Dutch els and Swedish eljest.

   **Etymology**

   Old English elles "in another manner, other, otherwise, besides, different," from Proto-Germanic *aljaz (source also of Gothic aljis "other," Old High German eli-lenti, Old English el-lende, both meaning "in a foreign land;" see also [Alsace](https://www.etymonline.com/word/Alsace?ref=etymonline_crossreference)), an adverbial genitive of the neuter of PIE root [*al-](https://www.etymonline.com/word/*al-?ref=etymonline_crossreference) "beyond" (source also of Greek allos "other," Latin alius). **As a quasi-adjective, synonymous with [other](https://www.etymonline.com/word/other?ref=etymonline_crossreference), from 1660s**; the nuances of usage are often arbitrary.Productive of a number of handy compounds that somehow never got traction or have been suffered to fall from use: elsehow (1660s) "somehow or other;" elsewards (adv.), 1882, "somewhere else;" Old English elsewhat (pron.) "something else, anything else;" elsewhen(adv.), early 15c., "at another time; elsewhence (c. 1600); elsewho (1540s). Among the survivors are [elsewhere](https://www.etymonline.com/word/elsewhere?ref=etymonline_crossreference), [elsewise](https://www.etymonline.com/word/elsewise?ref=etymonline_crossreference). Menacing or else, with omitted but implied threat, is from 1833.

3. 释义,

**Synopsis** sɪˈnɑːp.sɪs/  梗概

1. 助记,
  from Greek synopsis "a general view,"
  syn(together) + opsis(see) = see together, see all

  概要就是看到全部.

2. 词源,
  **OED Origin**
  Early 17th century: via late Latin from Greek, from sun- ‘together’ + opsis ‘seeing’.

  **Etymology**
  *synopsis (n.)*
  1610s, "a general view, an outline," from Late Latin synopsis "a synopsis," from Greek synopsis "a general view," literally "a seeing altogether, a seeing all at once," from syn- "together" (see syn-) + opsis "sight, appearance," from PIE root *okw- "to see."

3. 释义,
  1) （电影、书籍等的）概要，梗概，提要 a short description of the contents of something such as a film or book

**Optic** /ˈɑːp.tɪk/

1. 助记,

   from Greek optikos, from optos ‘seen’.

2. 词源,

   **Origin**

   Late Middle English: from French optique or medieval Latin opticus, from Greek optikos, from optos ‘seen’.

   **Etymology**

   early 15c., from Middle French optique, obtique (c. 1300) and directly from Medieval Latin opticus "of sight or seeing," from Greek optikos "of or having to do with sight," from optos "seen, visible," related to ops "eye," from PIE root [*okw-](https://www.etymonline.com/word/*okw-?ref=etymonline_crossreference) "to see."

3. 释义

   光学的；眼睛的；视觉的relating to light or the eyes

   光缆a [fibre](https://dictionary.cambridge.org/zhs/%E8%AF%8D%E5%85%B8/%E8%8B%B1%E8%AF%AD-%E6%B1%89%E8%AF%AD-%E7%AE%80%E4%BD%93/fibre) optic [cable](https://dictionary.cambridge.org/zhs/%E8%AF%8D%E5%85%B8/%E8%8B%B1%E8%AF%AD-%E6%B1%89%E8%AF%AD-%E7%AE%80%E4%BD%93/cable)




**Concatenate** /kənˈkæt̬.ə.neɪt/ 

1. 助记,

   from con- ‘together’ + catenare, from catena ‘chain’.

2. 词源,

   **Origin**

   Late 15th century (as an adjective): from late Latin concatenat- ‘linked together’, from the verb concatenare, from con- ‘together’ + catenare, from catena ‘chain’.

   **Etymology**

   "to link together, unite in a series or chain, " 1590s, from Late Latin concatenatus, past participle of concatenare "to link together," from com "with, together" (see [con-](https://www.etymonline.com/word/con-?ref=etymonline_crossreference)) + catenare, from catena"a chain" (see [chain](https://www.etymonline.com/word/chain?ref=etymonline_crossreference) (n.)). Related: Concatenated; concatenating. As an adjective, concatenate"linked together" is attested from 1540s.

3. 释义,

   1) 使连接,使连锁，把…连成一串to put things together as aconnected series

   ​


**plummet** /ˈplʌm.ɪt/ 暴跌

1. 助记：plummet /‘plʌmɪt/ n. 铅锤，坠子 vi. 垂直落下,

   来自古法语plomet,铅，铅球. plumb-=lead，作为名词，表示铅；-et为名词后缀，表示小东西。铅很重，所以引申为“铅垂，垂直下落”。

   同根词 plunge vi. 投入；跳进；陷入

2. 词源：

   **Origin**

   Late Middle English (as a noun): from Old French plommet ‘small sounding lead’, **diminutive of plomb ‘lead’**. The current verb sense dates from the 1930s.

    **Etymology**

   Late 14c., "ball of lead, plumb of a bob-line," from Old French plomet "graphite, lead; plummet, sounding lead," diminutive of plom "sounding lead" (see plumb (n.)).

   *plumb*

   Middle English (originally in the sense ‘sounding lead’): via Old French from Latin plumbum ‘l

   ead’.

    lead hung on a string to show the vertical line," early 14c., from Old French *plombe, plomee "sounding lead," and directly from Late Latin *plumba, originally plural of Latin plumbum "lead (the metal), lead ball; pipe; pencil," a word of unknown origin, related to Greek molybdos "lead" (dialectal bolimos) and perhaps from an extinct Mediterranean language, perhaps Iberian.

3. 定义：

   ​    to fall very quickly and suddenly 非常突然，急速的下降



**Tee** /tiː/ 

1. 助记, ()

2. 词源,(略)

3. 释义,

   1) （高尔夫）球座；发球区

   a short plastic stick with a cup-shaped top on which a golf ballis put to be hit, or the areawhere this is used to start theplay for each hole

   <img src='https://media.treehugger.com/assets/images/2011/10/White-Composite-Launcher-Tee.JPG' style='zoom:50%'>

   2) 字母T

   In computing, **tee** is a [command](https://en.wikipedia.org/wiki/Command_(computing)) in [command-line interpreters](https://en.wikipedia.org/wiki/Command-line_interpreter) ([shells](https://en.wikipedia.org/wiki/Shell_(computing))) using [standard streams](https://en.wikipedia.org/wiki/Standard_streams) which reads standard input and writes it to both standard output and one or more files, effectively duplicating its input.[[1\]](https://en.wikipedia.org/wiki/Tee_(command)#cite_note-UNIX_Man_Page-1) It is primarily used in conjunction with [pipes](https://en.wikipedia.org/wiki/Pipeline_(Unix)) and [filters](https://en.wikipedia.org/wiki/Filter_(Unix)). The command is named after the [T-splitter used in plumbing](https://en.wikipedia.org/wiki/Piping_and_plumbing_fitting#Tee).[[2\]

   ![img](https://upload.wikimedia.org/wikipedia/commons/thumb/2/24/Tee.svg/400px-Tee.svg.png)


**Plumb**  /plʌm/  铅直, 安装水管

1. 助记,

   Plum - 法语的(lead) 铅

   水管工需要测量安装水管的铅直度.

2. 词源, 

   **OED Origin**

   Late 19th century (in the sense ‘work as a plumber’): back-formation from plumber.

   **Etymology**

   "lead hung on a string to show the vertical line," early 14c., from Old French *plombe, plomee"sounding lead," and directly from Late Latin *plumba, originally plural of Latin plumbum"lead (the metal), lead ball; pipe; pencil," a word of unknown origin, related to Greek molybdos"lead" (dialectal bolimos) and perhaps from an extinct Mediterranean language, perhaps Iberian.

3. 释义,

   1) 给…装水管(WATER)

   to supply a building or a device with water pipes, or to connect a building or a device to a water pipe

   2)  测（尤指水）的深度engineering to measure how deep something is, especially water

   3) 完全，彻底(COMPLETELY)
    completely

   4) 垂直的 exactly straight, usually describing a vertical surface or line

   ​

   **Plumber** /ˈplʌm.ɚ/ 水管安装工

   1. 助记,

      原意,"a worker in any sort of lead" (roofs, gutters, pipes), 

      安装水管,需要用到'铅坠'测量水管的垂直度.

   2. 词源,

      **OED Origin**

      Late Middle English (originally denoting a person dealing in and working with lead): from Old French plommier, from Latin plumbarius, from plumbum ‘lead’.

      **Etymology**

      late 14c. (from c. 1100 as a surname), "a worker in any sort of lead" (roofs, gutters, pipes), from Old French plomier "lead-smelter" (Modern French plombier) and directly from Latin plumbarius "worker in lead," noun use of adjective meaning **"pertaining to lead,"** from plumbum "lead" (see [plumb](https://www.etymonline.com/word/plumb?ref=etymonline_crossreference) (n.)). Meaning focused 19c. on "workman who installs pipes and fittings" as lead water pipes became the principal concern of the trade. In U.S. Nixon administration (1969-74), the name of a special unit for investigation of "leaks" of government secrets.

   3. 释义,

      1) 管子工，水暖工**a person whose job is tosupply and connect or repairwater pipes, baths, toilets, etc.**

      ​

**Fitting** /ˈfɪt.ɪŋ/ 

1. 助记,

   **fittings** A small part on or attached to a piece of furniture or equipment.

2. 词源,

   tee -- pipe fitting

3. 释义,

   A **fitting** is used in pipe systems to connect straight [pipe](https://en.wikipedia.org/wiki/Pipe_(fluid_conveyance))or [tubing](https://en.wikipedia.org/wiki/Tube_(fluid_conveyance)) sections, adapt to different sizes or shapes and for other purposes, such as regulating (or measuring) [fluid](https://en.wikipedia.org/wiki/Fluid) flow. "Plumbing" is generally used to describe the conveyance of water, gas, or liquid waste in domestic or commercial environments; "piping" is often used to describe the high-performance (high-pressure, high-flow, high-temperature or hazardous-material) conveyance of fluids in specialized applications. "Tubing" is sometimes used for lighter-weight piping, especially that flexible enough to be supplied in coiled form.

   Fittings (especially uncommon types) require money, time, materials and tools to install, and are an important part of [piping](https://en.wikipedia.org/wiki/Piping) and [plumbing](https://en.wikipedia.org/wiki/Plumbing) systems.[[1\]](https://en.wikipedia.org/wiki/Piping_and_plumbing_fitting#cite_note-1) [Valves](https://en.wikipedia.org/wiki/Valve) are technically fittings, but are usually discussed separately.

   <img src='https://upload.wikimedia.org/wikipedia/commons/thumb/8/8c/Robinetterie-raccords.JPG/440px-Robinetterie-raccords.JPG' style='zoom:80%'>






**Expand** /ɪkˈspænd/ 扩展

1. 助记,

   ex (out) + pand(pace,step) 向外迈出一步,即是扩展.

   pace(一步；一步之距): a single step, or thedistance you move when you take a single step

   ex- ‘out’ + pandere ‘to spread’

   PIE root [*pete-](https://www.etymonline.com/word/*pete-?ref=etymonline_crossreference) "to spread"

2. 词源,

   **OED  Origin**

   Late Middle English: from Latin expandere ‘to spread out’, from ex- ‘out’ + pandere ‘to spread’.

   **Etymology**

   early 15c., "spread out, open out, spread flat, extend widely;" also transitive, "cause to grow larger;" from Anglo-French espaundre, Old French espandre "spread, spread out, be spilled," and directly from Latin expandere "to spread out, unfold, expand," from ex "out" (see [ex-](https://www.etymonline.com/word/ex-?ref=etymonline_crossreference)) + pandere "to spread, stretch" (from nasalized form of PIE root [*pete-](https://www.etymonline.com/word/*pete-?ref=etymonline_crossreference) "to spread"). Related: Expanded; expanding.

3. 释义,

   1) （使）（尺寸、数量或重要性）扩大，增加；（使）膨胀

   to increase in size, number, or importance, or to make something increase in this way

4. 拓展, 

   expansion /ɪkˈspæn.ʃən/

   （尺寸、数量或重要性的）扩大，增加，扩展 the increase of something in size, number, or importance

   ​

**Compass** /ˈkʌm.pəs/  指南针, 圆规

1. 助记,

   Com(together) + pass(pace)

   走过的每一步的集合, 圆规画圆形是无数点的集合

   指南针,是指导如何一步一步的走完行程.

2. 词源,

   **OED Origin**

   Middle English: from Old Frech compas (noun), compasser (verb), based on Latin com- ‘together’ + passus ‘a step or pace’. Several senses (‘measure’, ‘artifice’, ‘circumscribed area’, and ‘pair of compasses’) which appeared in Middle English are also found in Old French, but their development and origin are uncertain. The transference of sense to the magnetic compass is held to have occurred in the related Italian word compasso, from the circular shape of the compass box.

   **Etymology**

   c. 1300, "space, area, extent, circumference," from Old French compas "circle, radius; size, extent; pair of compasses" (12c.), from compasser "to go around, measure (with a compass); divide equally," from Vulgar Latin *compassare "to pace out," from Latin com "with, together" (see [com-](https://www.etymonline.com/word/com-?ref=etymonline_crossreference)) + passus "a step" (from PIE root [*pete-](https://www.etymonline.com/word/*pete-?ref=etymonline_crossreference) "to spread").The mathematical instrument for describing circles was so called in English from mid-14c. The mariners' directional tool (so called since early 15c.) took the name, perhaps, because it's round and has a point like the mathematical instrument.Meaning "limits, boundary" is from 1550s. Sense of "range of notes which a given voice or instrument can produce" is from 1590s. The word is in most European languages, with a mathematical sense in Romance, a nautical sense in Germanic, and both in English. In Middle English it also could mean "ingenuity, subtlety, cunning." Also an adverb in Middle English: to go compass was "go in a circle, go around."

3. 释义,

   1)  (DIRECTION DEVICE) 指南针
   a device for finding direction with a needle that can move easily and that always points to magnetic north

   2)  (MEASURING DEVICE) 圆规
   a V-shaped device that is used for drawing circles or measuring distances on maps

   3) （能力、活动、兴趣等的）界限，范围，范畴 formal a particular range (of ability, activity, interest, etc.)



**Pace** /peɪs/ 一步,步速

1. 助记

   from Old French pas, from Latin passus ‘stretch (of the leg)’, from pandere ‘to stretch’.

   迈开腿走一步,是词根pete(spread)的原型.

2. 词源,

   **OED Origin**

   Middle English: from Old French pas, from Latin passus ‘stretch (of the leg)’, from pandere ‘to stretch’.

   **Etymology**

   late 13c., "a step in walking; rate of motion," from Old French pas "a step, pace, trace," and directly from Latin passus, passum "a step, pace, stride," noun use of past participle of pandere"to stretch (the leg), spread out," probably from PIE *pat-no-, nasalized variant form of root [*pete-](https://www.etymonline.com/word/*pete-?ref=etymonline_crossreference) "to spread." Also, "a measure of five feet" [Johnson]. Pace-setter in fashion is from 1895.

3. 释义,

   1) （移动的）步速；（发生的）速度；节奏 

   the speed at which someone or something moves, or with which something happens or changes

   2) 一步；一步之距

   a single step, or the distance you move when you take a single step

   ​


**Slick**

1. 助记,

   <img src='http://oimagec2.ydstatic.com/image?url=http://www.hji.co.uk/hjimages/images/qhs2243/hji/medium/2006-men-slick.jpg&product=PICDICT'>

   smooth + click

   ​

2. 词源,

   **OED Origin**

   Middle English (in the senses ‘glossy’ and ‘make smooth or glossy’): probably from Old English and related to Old Norse slíkr ‘smooth’; compare with sleek.

   **Etymology**

   *slick (n.)*

   1620s, a kind of cosmetic, from [slick](https://www.etymonline.com/word/slick?ref=etymonline_crossreference) (v.). Meaning "smooth place on the surface of water caused by oil, etc." is attested from 1849. Meaning "a swindler, clever person" is attested from 1959.

   *slick (v.)*

   Old English -slician (in nigslicod "newly made sleek"), from Proto-Germanic *slikojan, from base *slikaz (source also of Old Norse slikr "smooth," Old High German slihhan "to glide," German schleichen "to creep, crawl, sneak," Dutch slijk "mud, mire"), from PIE *sleig- "to smooth, glide, be muddy," from root *(s)lei- "slimy" (see [slime](https://www.etymonline.com/word/slime?ref=etymonline_crossreference) (n.)). Related: Slicked;

3. 释义,

   1) 熟练自如的，娴熟的
   operating or performing skilfully and effectively, without problems and without seeming to need effort

   2) 油滑的，华而不实的
   skilful and effective but not sincere or honest

   ​

   ​



**Sleek** **/sliːk/

1. 助记,

2. 词源,

3. 释义,

   **(especially of hair, clothes, orshapes) smooth, shiny, andlying close to the body, andtherefore looking well cared for; not untidy and with no partssticking out**

   （尤指头发、衣服）平滑发亮的，整洁的；（外形）线条流畅的



**Parameter**

1. 助记

   在附近测量,Para(beside,near)+meter

2. 词源,

   [Parameter - Wikipedia](https://en.wikipedia.org/wiki/Parameter)

   **Computer programming**

   In [computer programming](https://en.wikipedia.org/wiki/Computer_programming), two notions of [parameter](https://en.wikipedia.org/wiki/Parameter_(computer_programming)) are commonly used, and are referred to as [parameters and arguments](https://en.wikipedia.org/wiki/Parameter_(computer_programming)#Parameters_and_arguments)—or more formally as a **formal parameter** and an **actual parameter**.

   For example, in the definition of a function such as

   `y = f(x) = x + 2,`


   *x* is the *formal parameter* (the *parameter*) of the defined function.

   When the function is evaluated for a given value, as in

   `f(3): or, y = f(3) = 3 + 2 = 5,`


    is the *actual parameter* (the *argument*) for evaluation by the defined function; it is a given value (actual value) that is substituted for the *formal parameter* of the defined function. (In casual usage the terms *parameter* and *argument* might inadvertently be interchanged, and thereby used incorrectly.)

   These concepts are discussed in a more precise way in [functional programming](https://en.wikipedia.org/wiki/Functional_programming) and its foundational disciplines, [lambda calculus](https://en.wikipedia.org/wiki/Lambda_calculus) and [combinatory logic](https://en.wikipedia.org/wiki/Combinatory_logic). Terminology varies between languages; some computer languages such as [C](https://en.wikipedia.org/wiki/C_(programming_language)) define parameter and argument as given here, while [Eiffel](https://en.wikipedia.org/wiki/Eiffel_(programming_language)) uses an [alternative convention](https://en.wikipedia.org/wiki/Parameter_(computer_programming)#Alternative_convention_in_Eiffel).

   In the function definition `f(x) = x*x` the variable x is a parameter; in the function call `f(2)` the value 2 is the argument of the function. Loosely, a parameter is a type, and an argument is an instance.

   > [Parameter (computer programming) - Wikipedia](https://en.wikipedia.org/wiki/Parameter_(computer_programming)#Parameters_and_arguments)
   >
   > Parameters appear in procedure definitions; arguments appear in procedure calls. In the function definition `f(x) = x*x` the variable x is a parameter; in the function call `f(2)` the value 2 is the argument of the function. **Loosely, a parameter is a type, and an argument is an instance.**

    **Mathematical functions[[edit source](https://en.wikipedia.org/w/index.php?title=Parameter&action=edit&section=1)]**

   [Mathematical functions](https://en.wikipedia.org/wiki/Mathematical_function) have one or more [arguments](https://en.wikipedia.org/wiki/Argument_of_a_function) that are designated in the definition by [variables](https://en.wikipedia.org/wiki/Variable_(mathematics)). A function definition can also contain parameters, but unlike variables, parameters are not listed among the arguments that the function takes. When parameters are present, the definition actually defines a whole family of functions, one for every valid set of values of the parameters. For instance, one could define a general [quadratic function](https://en.wikipedia.org/wiki/Quadratic_function) by declaring


   here, the variable *x* designates the function's argument, but *a*, *b*, and *c* are parameters that determine which particular quadratic function is being considered. A parameter could be incorporated into the function name to indicate its dependence on the parameter. For instance, one may define the base-*b* logarithm by the formula

3. 释义,

      限定因素 a set of facts or a fixed limit that establishes or limits how something can or musthappen or be done

      Technical A numerical or other measurable factor forming one of a set that defines a system or sets the conditions of its operation.   ‘there are three parameters by which a speaker is able to modify the meaning of the utterance—pitch, volume, and tempo’

4. 拓展

      parameter : para-,在旁，在周围，-meter,测量，规定，词源同meter,measure.引申词义参数，规范.【数学】参(变)数；参(变)量.



**Paradox** /ˈper.ə.dɑːks

1. 助记,

   para- "contrary to" (see [para-](https://www.etymonline.com/word/para-?ref=etymonline_crossreference) (1)) + doxa "opinion,"

   Para(contrary to) + dox(doc, documents)

   相反的观点.

2. 词源,

   **Origin**

   Mid 16th century (originally denoting a statement contrary to accepted opinion): via late Latin from Greek paradoxon ‘contrary (opinion)’, neuter adjective used as a noun, from para- ‘distinct from’ + doxa ‘opinion’.

   **Etymology**

   1530s, "statement contrary to common belief or expectation," from Middle French paradoxe (14c.) and directly from Latin paradoxum "paradox, statement seemingly absurd yet really true," from Greek paradoxon, noun use of neuter of adjective paradoxos "contrary to expectation, incredible," from para- "contrary to" (see [para-](https://www.etymonline.com/word/para-?ref=etymonline_crossreference) (1)) + doxa "opinion," from dokein "to appear, seem, think" (from PIE root [*dek-](https://www.etymonline.com/word/*dek-?ref=etymonline_crossreference) "to take, accept"). Meaning "statement that is seemingly self-contradictory yet not illogical or obviously untrue" is from 1560s.

3. 释义, 

   自相矛盾的情况；似非而是的说法，悖论

   a situation or statement thatseems impossible or is difficultto understand because itcontains two opposite facts orcharacteristics



**Substitute** /ˈsʌb.stə.tuːt/ 取代

1. 助记,

   sub(under) + sti(stand) +tute

   放在下面的东西站了起来,取代

2. 词源,

   **Origin**

   Late Middle English (denoting a deputy or delegate): from Latin substitutus ‘put in place of’, past participle of substituere, based on statuere ‘set up’.

   **Etymology**

   late 14c., "appointment of a subordinate or successor," from Middle French substitution or directly from Late Latin substitutionem (nominative substitutio) "a putting in place of (another)," noun of action from past participle stem of Latin substituere "put in place of another, place under or next to, present, submit," from sub "under" (see [sub-](https://www.etymonline.com/word/sub-?ref=etymonline_crossreference)) + statuere "set up," from PIE root [*sta-](https://www.etymonline.com/word/*sta-?ref=etymonline_crossreference) "to stand, make or be firm," with derivatives meaning "place or thing that is standing."

3. 释义,

   1) 用…代替，代之以to use something or someone instead of another thing or person

   2)取代，代替 **to perform the same jobas another thing or to take its place**

   ​

   ​


**Permit** /pɚˈmɪʃ.ən/

1. 助记,

   Per(before, in front of ) + mit(mission) 

   before mission, in front of mission.

   在做任务之前要获得许可.Permit.

2. 词源,

   **Origin**

   Late Middle English (originally in the sense ‘commit, hand over’): from Latin permittere, from per- ‘through’ + mittere ‘send, let go’.

   **Etymology**

   late 15c., from Middle French permetre and directly from Latin permittere "let pass, let go, let loose; give up, hand over; let, allow, grant, permit," from per "through" (from PIE root [*per-](https://www.etymonline.com/word/*per-?ref=etymonline_crossreference) (1) "forward," hence "through") + mittere "let go, send" (see [mission](https://www.etymonline.com/word/mission?ref=etymonline_crossreference)). Related: Permitted; permitting.

3. 释义,

   1) 允许，准许 to allow something

   2) 允许；使…有可能 to make something possible



**2018-03-20**

**Mission** ['mɪʃən] 

1. 词源,
   "a sending abroad," originally of Jesuits, from Latin missionem
   派遣,源自耶稣教会的传教.
   from 词根,mittere ‘send’. 比如导弹missile
   **OED Origin**
   Mid 16th century (denoting the sending of the Holy Spirit into the world): from Latin missio(n-), from mittere ‘send’.
   **Etymology**
   1590s, "a sending abroad," originally of Jesuits, from Latin missionem (nominative missio) "act of sending, a dispatching; a release, a setting at liberty; discharge from service, dismissal," noun of action from past participle stem of mittere "to release, let go; send, throw," which de Vaan traces to a PIE *m(e)ith- "to exchange, remove," also source of Sanskrit methete, mimetha "to become hostile, quarrel," Gothic in-maidjan "to change;" he writes, "From original 'exchange', the meaning developed to 'give, bestow' ... and 'let go, send'."

2. 助记 

   mission, missile

3. 释义
  any work that someone believes it is their duty to do
  1) 军事任务, an important job, especially a military one, that someone is sent somewhere to do
  2) 天职,尤其指传教, The vocation or calling of a religious organization, especially a Christian one, to go out into the world and spread its faith.
  3) 使命,雄心壮志. A strongly felt aim, ambition, or calling.



**Essential** /ɪˈsen.ʃəl/ 要素

1. 助记,
  Essence+ial

2. 词源,
  **OED Origin**
  Middle English (in the sense ‘in the highest degree’): from late Latin essentialis, from Latin essentia (see essence).

  **Etymology**
  mid-14c., "that is such by its essence," from Late Latin essentialis, from essentia "being, essence," abstract noun formed (to translate Greek ousia "being, essence") from essent-, present participle stem of esse "to be," from PIE root [*es-](https://www.etymonline.com/word/*es-?ref=etymonline_crossreference) "to be." Meaning "pertaining to essence" is from late 14c., that of "constituting the essence of something" is from 1540s; that of "necessary" is from 1520s. Essentials"indispensable elements" is from early 16c. Related: Essentially.

3. 释义,
  要素 necessary or needed，a basic thing that you cannot live without

4. 拓展
  essential : 来自essence,本质。
  quintessence（精华）：被视为万物精华的“第五物质”
  古代希腊哲学家认为世间除了常见的水、火、土、气等四种物质外，还存在第五种物质。这种物质是万物之精华，构成了天体，并弥漫在所有其他物质中。亚里斯多德将这种物质命名为“以太”（ether）。拉丁语将这种物质称为quinta essentia（第五物质）。该词经由法语进入英语后，拼写改为quintessence。中世纪的炼金术士致力于提炼这种物质，认为它能治百病，并且具有长生不老的功效。现在，该词一般用来比喻“精华、精髓、典范”。



**Essence** /ˈes.əns/ 本质, 香精

1. 助记, 

   from Latin essentia "being"

   from PIE root [*es-](https://www.etymonline.com/word/*es-?ref=etymonline_crossreference) "to be." (to be存在, 烂俗的一句 to be or not to be)

   from Latin essentia, from esse ‘be’.

   'es'是`I am` 中的`am`的词根.

   本质是存在物.

2. 词源,

   **OED Origin**

   Late Middle English: via Old French from Latin essentia, from esse ‘be’.

   **Etymology**

   late 14c., essencia (respelled late 15c. on French model), from Latin essentia "being, essence," abstract noun formed (to translate Greek ousia "being, essence") from essent-, present participle stem of esse "to be," from PIE root [*es-](https://www.etymonline.com/word/*es-?ref=etymonline_crossreference) "to be."Originally "substance of the Trinity;" the general sense of "basic element of anything" is first recorded in English 1650s, though this is the underlying notion of the first English use of [essential](https://www.etymonline.com/word/essential?ref=etymonline_crossreference). Meaning "ingredient which gives something its particular character" is from c. 1600, especially of distilled oils from plants (1650s), hence "fragrance, perfume" (17c.). In 19c. U.S., essence-peddler could mean "medical salesman" and "skunk."

3. 释义

   1) 本质；实质；要素(IMPORTANCE)
    the basic or most important idea or quality of something

   2) 香精，香料，精油(SMELL/TASTE) （通常取自植物或花的）

   a strong liquid, usually from a plant or flower, that is used to add a flavour or smell to something

   ​

**Am** /æm/

1. 助记,(略)

2. 词源,

   **Etymology**

   first person singular present **indicative of [be](https://www.etymonline.com/word/be?ref=etymonline_crossreference) (q.v.);** Old English eom bMercian eam, Northumbrian am), from Proto-Germanic *izm(i)-, from PIE *esmi- (source also of Old Norse emi, Gothic im, Hittite esmi, Old Church Slavonic jesmi, Lithuanian esmi), first person singular form of root [*es-](https://www.etymonline.com/word/*es-?ref=etymonline_crossreference) "to be."In Old English it formed only present tenses, all other forms being expressed in the W-BASE (see [were](https://www.etymonline.com/word/were?ref=etymonline_crossreference), [was](https://www.etymonline.com/word/was?ref=etymonline_crossreference)). This cooperative verb is sometimes referred to by linguists as *es-*wes-. Until the distinction broke down 13c., *es-*wes- tended to express "existence," with beon meaning something closer to "come to be."Old English am had two plural forms: 1. sind/sindon, sie and 2. earon/aron. The s- form (also used in the subjunctive) fell from English in the early 13c. (though its cousin continues in German sind, the 3rd person plural of "to be") and was replaced by forms of be, but aron (see [are](https://www.etymonline.com/word/are?ref=etymonline_crossreference)) continued, and as am and be merged it encroached on some uses that previously had belonged to be. By the early 1500s it had established its place in standard English.

3. 释义,(略)



**is**

1. 助记,

2. 词源,

   **Etymology**

   third person singular present indicative of [be](https://www.etymonline.com/word/be?ref=etymonline_crossreference), Old English is, from Germanic stem *es- (source also of Old High German, German, Gothic ist, Old Norse es, er), from PIE *es-ti- (source also of Sanskrit asti, Greek esti, Latin est, Lithuanian esti, Old Church Slavonic jesti), third person singular form of root [*es-](https://www.etymonline.com/word/*es ref=etymonline_crossreference) "to be." Old English lost the final -t-.Until 1500s, pronounced to rhyme with kiss. Dialectal use for all persons (I is) is in Chaucer. Phrase it is what it is, indicating resigned acceptance of an unpleasant but inevitable situation or circumstance about which nothing truly positive can be said, is attested by 2001.

3. 释义,(略)



**Identify** /aɪˈden.t̬ə.faɪ/ 

1. 助记,

   from late Latin identitas (see identity) + Latin -ficare (from facere ‘make’).

2. 词源

   **Origin**

   Mid 17th century (in the sense ‘treat as being identical with’): from medieval Latin identificare, from late Latin identitas (see identity) + Latin -ficare (from facere ‘make’).

   **Etymology**

   1640s, "regard as the same," from French identifier, from identité (see [identity](https://www.etymonline.com/word/identity?ref=etymonline_crossreference)). Sense of "determine the identity of, recognize as or prove to be the same" first recorded 1769. Meaning "make one (with), associate (oneself), regard oneself as being the essence of" is from 1780. Sense of "serve as means of identification" is attested by 1886. Related: Identified; identifying.

3. 释义,

   1) 认出，识别 to recognize someone or something and say or prove who or what that person or thing is

   2) 确定；发现 to recognize a problem, need, fact, etc. and to show that it exists

   ​

**Identity** /aɪˈden.tə.ti

1. 助记, 

   ultimately from Latin idem (neuter) "the same" (see [idem](https://www.etymonline.com/word/idem?ref=etymonline_crossreference)).

   本身

2. 词源,

   **Origin**

   Late 16th century (in the sense ‘quality of being identical’): from late Latin identitas, from Latin idem ‘same’.s

   **Etymology**

   c. 1600, "sameness, oneness, state of being the same," from Middle French identité (14c.), from Medieval Latin identitatem(nominative identitas) "sameness," ultimately from Latin idem (neuter) "the same" (see [idem](https://www.etymonline.com/word/idem?ref=etymonline_crossreference)). [For discussion of Latin formation, see entry in OED.] Earlier form of the word in English was idemptitie (1560s), from Medieval Latin idemptitas. Term identity crisis first recorded 1954. Identity theft attested from 1995. Identity politics is attested by 1987.

   >  idem (adv.)
   >
   > "the same (as above)," used to avoid repetition in writing, Latin, literally "the same," from id "it, that one," from PIE pronominal stem *i-(see [yon](https://www.etymonline.com/word/yon?ref=etymonline_crossreference)) + demonstrative suffix -dem.

3. 释义,

   1) 身份；本身；特性 

   who a person is, or the qualities of aperson or group that make them different from others 

4. ​

   ​

**Administer** **/ədˈmɪn.ə.stɚ/ 管理

1. 助记,

   from Old French aministrer"help, aid, be of service to"

   from ad "to" (see [ad-](https://www.etymonline.com/word/ad-?ref=etymonline_crossreference)) + ministrare "to serve, attend, wait upon,

2. 词源,

   **OED Origin**

   Late Middle English: via Old French from Latin administrare, from ad- ‘to’ + ministrare (see ministration).

   **Etymology**

   *administer (v.)*

   late 14c., aministren, later administren, "to manage as a **steward**, control or regulate on behalf of others," from Old French aministrer"help, aid, be of service to" (12c., Modern French administrer), and directly from Latin administrare "to help, assist; manage, control, guide, superintend; rule, direct," from ad "to" (see [ad-](https://www.etymonline.com/word/ad-?ref=etymonline_crossreference)) + ministrare "to serve, attend, wait upon," from minister "inferior, servant, priest's assistant" (see [minister](https://www.etymonline.com/word/minister?ref=etymonline_crossreference) (n.)).The -d- was restored 14c.-16c. in French and after 15c. in English. In reference to punishment, justice, etc., "to dispense, bring into operation" (especially as an officer), from mid-15c. In reference to medicines, medical treatment, etc., "to give," from 1540s. Related: Administered; administering.

3. 释义,

   1) 掌管；料理事物**to control the operation or arrangement of something**

   2)管理；治理 **to govern a country, region, etc.**



**Minister** /ˈmɪn.ə.stɚ/

1. 助记,

   Minis(minus) + ter

   原意为地位卑微的服务生, servant

2. 词源,

   **Origin**

   Middle English (in minister (sense 2 of the noun)); also in the sense ‘a person acting under the authority of another’): from Old French ministre (noun), ministrer (verb), from Latin minister ‘servant’, from minus ‘less’.

   **Etymology**

   *minister (n.)*

   c. 1300, "one who acts upon the authority of another," from Old French menistre "servant, valet, member of a household staff, administrator, musician, minstrel" (12c.), from Latin minister (genitive ministri) **"inferior, servant, priest's assistant"** (in Medieval Latin, "priest"), from minus, minor "less," hence "subordinate" (from PIE root [*mei-](https://www.etymonline.com/word/*mei-?ref=etymonline_crossreference) (2) "small") + comparative suffix *-teros. Formed on model of magister. Meaning "priest" is attested in English from early 14c. Political sense of "high officer of the state" is attested from 1620s, from notion of "service to the crown."

   *minister (v.)*

   early 14c., "to perform religious rites, provide religious services;" mid-14c., "to serve (food or drink);" late 14c. "render service or aid," from Old French menistrer "to serve, be of service, administer, attend, wait on," and directly from Latin ministrare "to serve, attend, wait upon," from minister "inferior, servant, priest's assistant" (see [minister](https://www.etymonline.com/word/minister?ref=etymonline_crossreference) (n.)). Related: Ministered; ministering.

3. 释义

   1) 部长；大臣 (POLITICIAN)
    a member of the government in Britain and many other countries who is in charge of a particular department or has an important position in it

   2) 牧师 (IN CHURCH)
   a religious leader in certain Christian churches

   3)公使 (COUNTRY'S REPRESENTATIVE)
   specialized politics a person below the rank of ambassador whose job is to represent his or her country in a foreign country

   ​

**Administrative** /ədˈmɪn.ə.strə.t̬ɪv/ 行政的,管理的

1. 助记,略

2. 词源,

   **OED Origin**

   Mid 18th century: from Latin administrativus, from administrat- ‘managed’, from the verb administrare (see administrate).

   **Etymology**

   "pertaining to administration, having to do with the managing of public affairs," 1731, from Latin administrativus, from past participle stem of administrare "to manage, control, superintend" (see [administer](https://www.etymonline.com/word/administer?ref=etymonline_crossreference)). Related: Administratively.

3. 释义,

   管理的；行政的 relating to the arrangements and workthat is needed to control the operation of aplan or organization

   ​

**Administrate** 同administer

1. 助记

2. 词源,

   **Origin**

   Mid 16th century: from Latin administrat- ‘managed’, from the verb administrare (see administer).

   **Etymology**

   "manage or direct affairs," 1630s, from Latin administratus, past participle of administrare "manage, control, superintend" (see [administer](https://www.etymonline.com/word/administer?ref=etymonline_crossreference)) or else a back-formation from administrator

3. 释义, 略

   ​



**Mask **/mæsk/

1. 助记,

   Old French mascurer "to black (the face)," 

   But compare Occitan mascara "to blacken, darken," derived from mask- "black,"

   Mask就是把脸黑起来,把脸遮住.

2. 词源, 

   **Origin**

   Mid 16th century: from French masque, from Italian maschera, mascara, probably from medieval Latin masca ‘witch, spectre’, but influenced by Arabic masḵara ‘buffoon’.

   **Etymology**

   *mask (n.)*

   1530s, from Middle French masque "covering to hide or guard the face" (16c.), from Italian maschera, from Medieval Latin masca "mask, specter, nightmare," of uncertain origin, perhaps from Arabic maskharah "buffoon, mockery," from sakhira "be mocked, ridiculed." Or via Provençal mascarar, Catalan mascarar, Old French mascurer "to black (the face)," perhaps from a Germanic source akin to English [mesh](https://www.etymonline.com/word/mesh?ref=etymonline_crossreference) (q.v.). But compare Occitan mascara "to blacken, darken," derived from mask- "black," which is held to be from a pre-Indo-European language, and Old Occitan masco"witch," surviving in dialects; in Beziers it means "dark cloud before the rain comes." [See Walther von Wartburg, "Französisches Etymologisches Wörterbuch: Eine Darstellung galloromanischen sprachschatzes"]. Figurative use by 1570s.

3. 释义,

   1) 面具，面罩a covering for all or part of the face that protects, hides, or decorates the person wearing it

   2) 掩饰；伪装appearance or behaviour that hides the truth

   ​

   ​

**Mode**

1. 助记,

   mode, mold, measure

   measure是所有方法的源头.

2. 词源,

   **Origin**

   Late Middle English (in the musical and grammatical senses): from Latin modus ‘measure’, from an Indo-European root shared by mete; compare with mood.

   **Etymology**

   *mode (n.1)*

   "manner," late 14c., "kind of musical scale," from Latin modus "measure, extent, quantity; proper measure, rhythm, song; a way, manner, fashion, style" (in Late Latin also "mood" in grammar and logic), from PIE root [*med-](https://www.etymonline.com/word/*med-?ref=etymonline_crossreference) "take appropriate measures." Meaning "manner in which a thing is done" first recorded 1660s.

   *mode (n.2*)

   "current fashion," 1640s, from French mode "manner, fashion, style" (15c.), from Latin modus "a way, manner, fashion, style," from PIE root [*med-](https://www.etymonline.com/word/*med-?ref=etymonline_crossreference) "take appropriate measures."Related 

3. 释义,

   1) 方法；做法；方式a way ofoperating, living, or behaving






**Proceed** proʊˈsiːd/

1. 助记,

    from pro "forward" (from PIE root *per- (1) "forward") + cedere "to go"

   词根cede,是access succeed的

2. 词源,

   **OED Origin**

   Late Middle English: from Old French proceder, from Latin procedere, from **pro- ‘forward’ + cedere ‘go’.**

   **Proceed (v.)**

   late 14c., "to go on," also "to emanate from, result from," from Old French proceder (13c., Modern French procéder) and directly from Latin procedere (past participle processus) "go before, go forward, advance, make progress; come forward," from pro "forward" (from PIE root *per- (1) "forward") + cedere "to go" (from PIE root *ked- "to go, yield"). Related: Proceeded; proceeding.

3. 释义

   1) （朝特定方向）前进 to move forward or travel in a particular direction

   2) 继续进行，继续做  to continue as planned

   ​

**Success**

1. 助记, 

   From sub "next to, after" (see sub-) + cedere "go, move" (from PIE root *ked- "to go, yield")

   Success is ‘ go for next’

   所谓的成功就是去准备下一件事.

2. 词源,

   **OED Origin**

   Mid 16th century: from Latin successus, from the verb succedere ‘come close after’ (see succeed).

   **Etymology**

   1530s, "result, outcome," from Latin successus "an advance, a coming up; a good result, happy outcome," noun use of past participle of succedere "come after, follow after; go near to; come under; take the place of," also "go from under, mount up, ascend," hence "get on well, prosper, be victorious," from sub "next to, after" (see sub-) + cedere "go, move" (from PIE root *ked- "to go, yield"). Meaning "accomplishment of desired end" (good success) first recorded 1580s. Meaning "a thing or person which succeeds," especially in public, is from 1882.

   The moral flabbiness born of the bitch-goddess SUCCESS. That -- with the squalid interpretation put on the word success -- is our national disease. [William James to H.G. Wells, Sept. 11, 1906]

   Success story is attested from 1902. Among the French phrases reported by OED as in use in English late 19c. were succès d'estime "cordial reception given to a literary work out of respect rather than admiration" and succès de scandale "success (especially of a work of art) dependent upon its scandalous character."

3. 释义,(略)





**whim** /wɪm/

1. 助记,

2. 词源,

   **Origin**

   Late 17th century: of unknown origin. whim (sense 2) (mid 18th century) is a transferred use.

   **Etymology**

   1640s, "play on words, pun," shortened from [whimwham](https://www.etymonline.com/word/whimwham?ref=etymonline_crossreference) "fanciful object" (q.v.). Meaning "caprice, fancy, sudden turn or inclination of the mind" first recorded 1690s, probably a shortened form of [whimsy](https://www.etymonline.com/word/whimsy?ref=etymonline_crossreference).

3. 释义, 

   1) 突然的念头，冲动

   a sudden wish or idea,especially one that cannot bereasonably explained

   ​


**Maze**

1. 助记,

   Maze 想象迷宫的形状吧.

2. 词源,

   **Origin**

   Middle English (denoting delirium or delusion): probably from the base of amaze, of which the verb is a shortening.

   *maze (n.)*

   c. 1300, "delusion, bewilderment" (also as a verb, "stupefy, daze"), possibly from Old English *mæs, which is suggested by the compound amasod "amazed" and verb amasian "to confound, confuse" (compare [amaze](https://www.etymonline.com/word/amaze?ref=etymonline_crossreference)). Perhaps related to Norwegian dialectal mas "exhausting labor," Swedish masa "to be slow or sluggish." Meaning "labyrinth" first recorded late 14c.

3. 释义,

   1) （供娱乐用的）曲径，迷宫a complicated system of paths or passages that people try to find their way through for entertainment

   2) 迷宫似的区域 an area in which you can get easily lost because there are so many similar streets or passages

   3) 错综复杂的事物 a complicated set of rules,ideas, or subjects that you finddifficult to deal with orunderstand 

   ​

   Display the Linux Kernel




How to view the kernel on MacOS?

I am learning Linux command line by William Shotts,

The Kernal directory can been accessed by :

 	ls /bin 
​	# Contain Linux kernal, inital RAM disk image

How to view the kernel on MacOS?

​	$ ls /boot
​	ls: /boot: No such file or directory





## Questions

```python
#questions

```



Extract elements with `re`

```python

I Retrieve elements with code

    dirs = ['',
         'Applications              cores                     sbin',
         'Library                   dev                       tmp',
         'Network                   etc                       usr',
         'System                    home                      var',
         'Users                     installer.failurerequests vm',
         'Volumes                   net',
         'bin                       private',
         '']
    re.findall(r"[\w\.]+",str(dirs))
    
I output:

    ['Applications', 'cores', 'sbin', 'Library', 'dev', 'tmp', 'Network',    'etc', 'usr', 'System', 'home', 'var', 'Users', 'installer.failurerequests', 'vm', 'Volumes', 'net', 'bin', 'private']
    
Is it a best practice to convert a list to str while using 're'?
    
    
```















