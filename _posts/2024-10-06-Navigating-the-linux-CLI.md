---
layout: post
title: Linux quick start reference
date: '2024-10-06 18:30:00 +0930'
Excerpt: A crash course to getting started with the Linux CLI
---
### A quick crash course to using the Linux command line interface (CLI)

- Navigate the file system
- Read files
- Manage the file system
- Filter content
- Manage users and their permissions
- Get help in Linux

### Navigating the file system

The following commands are used to navigate the Linux file system;

**cd - change directory**


`cd reports`

navigates from the current working directory to its subdirectory reports


`cd \home\cale\reports`

navigates to the reports directory; the full pathname is required when reports is not a subfirectory of the current working directory

`cd ..`

Navigates to the directory that is one level above the current working directory

**ls - displays the names of files and directories**

`ls \home\cale\reports`

Displays the names of the files and directories in the reports directory; providing an argument that specifies the path to a directory is necessary to display the contents of a directory other than the user's current working directory.

`ls -a`

Displays hidden files when displaying the names of files and directories inside the current working directory.

`ls -l`

Displays permissions to files and directories in the current working directory; also displays other additional information such as owner name, group, file size and the time of last modification.

`ls -la`

displays permissions to files and directories in the current working directoy; including hidden files. Also displays other additional information. This argument is a combination of both -a and -l and combines the output of both.

**pwd - prints the working directory to the screen**

`pwd`

Prints the current working directory to screen, such as \home\cale

**whoami - returns the username of the current user**

`whoami`

returns the current username, such as cale or admin.

### Reading files
The following details commands that are helpful when reading files

**cat - displays the contents of a file**

`cat updates.txt`

displays the content of the updates.txt file

**head - displays the first 10 lines of a file**

`head updates.txt`

displays the first 10 lines of the updates.txt file

`head -n 5 updates.txt`

displays only the first 5 lines of the file.
the -n option allows the user to specify the _number_ of lines to return.

less - returns the content of a file one page at a time

`less updates.txt`

returns the content of updates one page at a time; the less command changes the terminal window to a display which allows users to easily move forward and backward through content.

**tail - displays the last 10 lines of a file**

`tail updates.txt`

displays the last 10 lines of the updates.txt file

`tail -n 5 updates.txt`

returns the last 5 lines of updates.txt. The -n option allows the user to specify the number of lines to return.

### Filter content
These commands are useful for filtering content.

**find - searches for directories and files that meet the specified criteria**

`find \home\cale\projects`

searches for all files starting at the projects directory

`find \home\cale\projects -iname "*log*"`

searches for all files in the projects directory that contain the work log in the filename.
-iname searches for a specified string and is not case-sensitive; * is a wildcard and can represent zero or more unknown characters.

`find \home\cale\analyst\projects -mtime -3`

Searches for all files in the projects directory that have been modified within the past 3 days.
-mtime bases its search for files or directories that were modifed within the specified number of days.

`find \home\cale\projects -nmin -15`

Searches for all files in the projects directory that have been modified within the past 15 minutes.
-nmin bases its search for files or directories that were modified within the specified number of minutes.

**grep - searches within a specified file and returns all lines containing a specified string.**

`grep OS updates.txt`

searches the updates.txt file and returns all lines containing the string OS

**|| (piping) - sends the output of one command as the input of another command for further processing.**

`ls \home\analyst\reports | grep users`

redirects the standard output of ls \home\analyst\reports to be standard input for the grep users command, meaning the grep users identifies files and subdirectories in the \home\analyst\reports directory that contain the string users within their filename.

