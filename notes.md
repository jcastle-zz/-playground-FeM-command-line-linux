# FeM Command Line and Linux

- Course outline - bit.ly/linux-cli
- GitHub repo - https://github.com/btholt/complete-intro-to-linux-and-the-cli

## Setting up

- If don't have Linux box running and want to run from Mac, use [Multipass](https://multipass.run/)
- Can also use VirtualBox
- tmux for multi-window terminal

## Choose terminal program

- exec bash - to switch to bash
- exec zsh - to switch to zsh
- echo \$0 - see which program you are using

* doesn't affect new terminal windows, will default to chosen emulator

## File system

- ../ - one up
- ../.. - two up
- pwd - present working directory
- cd - change directory
- ls - list folders/files directory
- echo - output whatever put in there
- which - tells path to program that is running
- touch - creates a file

## Flags

- --help - help file for item
- -l - long form output of item
- -l -a - show the hidden files in the directory
- long flags are like --help, use two "--"
- short flags are like -a, use one "-", one dash means it can be a bunch of flags right away
- lsah - provides full output - file size, hidden files, human readable

## Moving around

- cd ~ - go to home directory
- cd / - go to root directory
- up and down keys on keyboard - scroll through history, these commands are stored in bash history and bad if passing passwords
- control r - search bash history, type a letter or keyword
- tail ~/.bash_history - shows last ten commands, can go into to bash_history to clear it
- !! - represents last command, can insert with another command (e.g., sudo !!)

## Power of CTRL

- CTRL + A – takes you to the beginning of the line
- CTRL + E – takes you to the end of the line
- CTRL + K – "yank" everything after the cursor
- CTRL + U – "yank" everything before the cursor
- CTRL + Y - "paste" (paste in quotes because it doesn't actually go into your system clipboard) everything you yanked
- CTRL + L - clear the screen
- CTRL + R – reverse search through history

## Signals

- CTRL + C - signal interrupt, send signal to stop the program
- CTRL + D - signal quit, shuts everything down, ends terminal session
- kill -l - will show all the signal commands

## Nano

- open source editor, usually get thrown in to if Vim isn't available
- ^ - means control

## Vim

- text editor, most common for editing files by line
- insert and command modes
- ex and vi fed into creation of Vim
- i - insert mode, use to insert text then escape
- :wq - write quit to save and close file
- :q! - quit without saving changes, quit no matter what

## Interacting with files

- less - allows you to read a file, opens in full page like Vim but only for reading
- man - stands for manual, provides manual for command (e.g., man less)
- cat - prints everything out in the terminal, good for short text files, adds file to standard out
- tail - outputs last ten lines
- head - outputs first ten lines
- mkdir - create folder (can use -p to nest folders)
- touch - creates file if it doesn't already exist, if it does exist it will update last modified time
- rm - remove file and folder
- rm -rf - remove file and folder and all corresponding files and folders (note: don't ever rm -rf the root or rm -rf /)
- cp - copy a file to another file or directory to another directory
- mv - move a file or folder to a new location

## Streams

- redirecting the output of a program
- ">" - used to replace the file
- ">>" - appends the file
- can use 1> (standard out) and 2> (standard error)
- /dev/null - used when you don't care about whatever goes into it
- "<" - used to output file into terminal

## Pipes

- ps aux - show all running processes
- ps aux | grep "ps aux" or ps aux | grep "yes" - find all running processes with "ps aux"

## Users and Groups

- whoami - returns userID
- principle of least privilege - want each user to have the least amount of power
- sudo su - become superuser
- sudo - call super user do command to run a program

## Permissions

- d rwx rwx rwx - permissions for a directory, rwx are permissions, first one is for the user, next is the group, last is everyone else group
- r - read
- w - write
- x - execute
- chown - change ownership - change ownership of a file or directory
- chmod - change modification - change permissions on a file or directory

## Environments

- variables can be setup as temporary per session or stored for later use
- printenv - show all env variables
- .bashrc - use this one, always run, keep all env here
- .bash_profile - older one, only run when opening bash - offers bash script to only look at .bashrc

## Processes

- only processes within terminal and linux, doesn't see programs on mac that are running
- ps - all processes being run by root user
- ps aux - all processes being run on machine by all users

## Exit Codes

- 0: means it was successful. Anything other than 0 means it failed
- 1: a good general catch-all "there was an error"
- 2: a bash internal error, meaning you or the program tried to use bash in an incorrect way
- 126: Either you don't have permission or the file isn't executable
- 127: Command not found
- 128: The exit command itself had a problem, usually that you provided a non-integer exit code to it
- 130: You ended the program with CTRL+C
- 137: You ended the program with SIGKILL
- 255: Out-of-bounds, you tried to exit with a code larger than 255
