---
layout: post
title: Linux Vocab
---
Most of the definitions come from *The Linux Command Line* by William E. Shotts Jr.

### Part I: Learning the Shell
#### Chapter 1: What is the Shell?  
* **shell**  
A program that takes keyboard commands and passes them to the operating system to carry out.  Almost all Linux distributions supply a shell program from the GNU Project called **bash**.
* **bash**  
Stands for "Bourne Again Shell".  An enhanced replacement for sh, the original Unix shell program written by Steve Bourne.
* **terminal emulator**  
Gives you access to interact with the shell.  Examples: konsole, gnome-terminal
* **superuser**  
A special user account used for system administration.  On Unix-like systems, for example, the user with a user identifier (UID) of zero is the superuser.   Root is the conventional name of the user who has all rights or permissions (to all files and programs) in all modes.


#### Chapter 2: Navigation  
* **heirarchical directory structure**  
Linux organizes its files in a tree-like pattern of directories (ie, folders) which may contain files and other directories
* **root directory**  
The first directory in the file system
* **pathname**  
The route we take along the branches of the tree to get to the directory we want  
  - *absolute pathname*:
  begin with the root, represented by a leading slash /
  - *relative pathname*:
  begin with the working directory, represented by ./ or just implied!
  
#### Chapter 3: Exploring the System
* **pagers**  
A class of programs that allow for easy viewing of long text documents in a page-by-page manner. Example: `less`
* **Configuration Files**  
Contain system settings  
* **Linux Filesystem Heirarchy Standard**  
Defines the directory structure and directory contents in Unix-like operating systems
* **symbolic link** or **soft link** or **symlink**  
The nickname for any file that contains a reference to another file or directory in the form of an absolute or relative path and that affects pathname resolution

#### Chapter 4: Manipulating Files & Directories
* **wildcard**  
A symbol that can stand for one or more characters
* **globbing**  
The process of expanding a non-specific file name containing a wildcard character into a set of specific file names that exist in storage on a computer, server, or network
* **hard link**  
A directory entry that associates a name with a file on a file system. Cannot reference a directory, only a file.
* **inode**  
A data structure in a Unix-style file system which describes a filesystem object such as a file or a directory. Each inode stores the attributes and disk block location(s) of the object's data. Filesystem object attributes may include metadata (times of last change, access, modification), as well as owner and permission data.  Everything except its name and its actual data!


#### Chapter 5: Working with Commands
* **alias**  
A command we can define ourself, built from other commands
* **shell builtins**  
A command built into the shell itself.  Example: `cd`
* **shell functions**  
Mini shell scripts incorporated into the environment
* **environment**  

#### Chapter 6: Redirection
* **standard output, input and error**  
Special files where programs such as `ls` send their results and receive their arguments.  By default, standard output & error are linked to the screen and not saved in a file, and standard input is attached to the keeyboard.
* **pipeline**  
Using the pipe operator |, the standard output of one command can be piped into the standard input of another
* **filter**  
A command that takes input, changes it, and then ouputs it. Example: sort.  Often get chained into a pipeline.
* **file descriptor**  

#### Chapter 7: Seeing the World as the Shell Sees It
* **expansion**  
Process by which the shell converts an expression into something else before commands are issued
  * *pathname expansion*  
  the mechanism by which wildcards match files
  * *tilde expansion*  
  when a tilde character ~ is used at the beginning of a word, it expands into the name of the home directory of the named user (or the home directory of the current user if no user is named).
  * *arithmetic expansion*  
  perform arithmetic by expansion using the following form: `$((expression))`. only supports integers.
  * *brace expansion*  
  Create multiple text strings from a from a pattern or set contained in braces.  The brace expression may contain a comma-separated list of strings or a range of integers or single characters. Example 1: `echo {Z..A}`.  Example 2: `echo a{A{1,2}, B{3,4}}b` will print `aA1b aA2b aB3b aB4b`
  * *parameter expansion*  
  substitute the value of a variable for the variable's name.  Example: `$VARIABLE`.  
  * *command substitution*  
  substitute the output of a command as an expansion. Example: `$(which cp)`. Older syntax: \`which cp\`
* **word splitting**  
Process by which the shell removes extra white space - treats all spaces, tabs, and newlines as the same delimiter
* **quoting**  
Mechanism for the shell to selectively suppress unwanted expansions
  * *double quotes*  
    - all special characters used by the shell lose their special meaning with the exception of $, \, and \`  
    - word-splitting; pathname, tilde & brace expansion are suppressed  
    - parameter, arithmetic, and command substitution are still carried out. escape characters are still escaped!
  * *single quotes*  
    - suppress all expansions
* **escape character**  
backslash \

#### Chapter 8: Advanced Keyboard Tricks
* **Readline**  
Library for command-line editing routines
* **killing and yanking**  
Cutting and pasting
* **kill-ring**  
Buffer which stores copied text
* **meta-key**  
* **completion**  
When you press the tab key once whilst typing a command that is already uniquely determined
* **programmable completion**  
Allows you or your distribution provider to add additional completion rules
* **history expansion**  
Bash history is saved in `.bash_history`. **History expansion** expands `!88` into the 88th line in the history list.

#### Chapter 9: Permissions
* **user ID or uid**  
Assigned to a user upon creation  
* **primary group ID or gid**  
* **file type**  
A regular file (-), a directory (d), a symbolic link (l), a character special file (c), or a block special file (b)
* **file mode**  
Represents the read, write & execute permissions for the file's owner, file's group owner, and everybody else.  Most commonly used are 7 (rwx), 6 (rw-), 5 (r-x), 4 (r--), and 0 (---).
* **setuid**  
when applied to an executable file, it sets the effective user ID from that of the real user to that of the porgram's owner -- often, the superuser.

#### Chapter 10: Processes  
* **multitasking**  
Operating system which creates the illusion of doing more than one thing at once by rapidly switching from one executing program to another
* **processes**  
How linux organizes different programs waiting for their turn at the CPU
* **init scripts**  
A series of shell scripts, kicked off by `init` at system start-up, which start all system services
* **daemon programs**  
A program that runs as a background process, rather than being under the direct control of an interactive user.  In a Unix environment, the parent process of a daemon is often, but not always, the init process. Traditionally, the process names of a daemon end with the letter d, for clarification that the process is, in fact, a daemon.  For example, syslogd is the daemon that implements the system logging facility, and sshd is a daemon that serves incoming SSH connections.
* **process ID or PID**  
Assigned to processes in ascending order.  `init` always gets PID 1.  
* **teletype or TTY**  
* **controlling terminal**  
* **uptime**  
Time since machine was last booted
* **load average**  
The number of processes waiting to run.  In `top`, load average shows three values, one for the last 60 seconds, 5 minutes, and 15 minutes.  
* **jobspec** 
The number assigned to a background job - not to be confused with PID!  Allows you to move the job easily from foreground to background and back with `%[jobspec]`.

### Part II: Configuration & The Environment
#### Chapter 11: The Environment
* **environment**  
Body of information maintained by the shell during a session
* **shell variables**  
Data stored by bash
* **environment variables**  
Any variable that isn't a shell variable
* **login shell session**  
Session in which we are prompted for our username and password.  Reads the startup files located in `/etc/profile` (global configs) and `~/.bash_profile` (user)
* **non-login shell session**  
Example: when we launch a session from the GUI.  Reads the startup files `/etc/bash.bashrc` (global configs) and `~/.bashrc` (user)
