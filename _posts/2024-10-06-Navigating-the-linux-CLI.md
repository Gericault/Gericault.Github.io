---
title: Navigating Linux CLI
layout: post
date: '2024-10-06 19:30:00 +0930'
---
### A quick crash course to using the Linux command line interface

- Navigate the file system
- Read files
- Manage the file system
- Filter content
- Manage users and their permissions
- Get help in Linux

### Navigating the file system

The following commands are used to navigate the Linux file system;

**cd** - Navigates between directories

```cd reports```
navigates from the current working directory to its subdirectory reports

```cd \home\cale\reports```
navigates to the reports directory; the full pathname is required when reports is not a subfirectory of the current working directory

```cd ..```
Naviates to the directory that is one level above the current working directory

**ls** - displays the names of files and directories

```ls \home\cale\reports```
Displays the names of the files and directories in the reports directory; providing an argument that specifies the path to a directory is necessary to display the contents of a directory other than the user's current working directory.

```ls -a```
Displays hidden files when displaying the names of files and directories inside the current working directory.

```ls -l```
Displays permissions to files and directories in the current working directory; also displays other additional information such as owner name, group, file size and the time of last modification.

```ls -la```
displays permissions to files and directories in the current working directoy; including hidden files. Also displays other additional information. This argument is a combination of both -a and -l and combines the output of both.

**pwd** - prints the working directory to the screen

```pwd```
Prints the current working directory to screen, such as \home\cale

**whoami** - returns the username of the current user

```whoami```
returns the current username, such as cale or admin.

### Reading files
The following details commands that are helpful when reading files

**cat** - displays the contents of a file

```cat updates.txt```
displays the content of the updates.txt file

**head** - displays the first 10 lines of a file

```head updates.txt```
displays the first 10 lines of the updates.txt file

```head -n 5 updates.txt```
displays only the first 5 lines of the file.
the -n option allows the user to specify the _number_ of lines to return.
