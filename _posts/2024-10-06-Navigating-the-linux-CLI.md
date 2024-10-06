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

{% highlight shell %}
cd reports
{% endhighlight %}

navigates from the current working directory to its subdirectory reports

{% highlight shell %}
cd \home\cale\reports
{% endhighlight %}


navigates to the reports directory; the full pathname is required when reports is not a subfirectory of the current working directory

{% highlight shell %}
cd ..
{% endhighlight %}

Navigates to the directory that is one level above the current working directory

**ls - displays the names of files and directories**

{% highlight shell %}
ls \home\cale\reports
{% endhighlight %}

Displays the names of the files and directories in the reports directory; providing an argument that specifies the path to a directory is necessary to display the contents of a directory other than the user's current working directory.

{% highlight shell %}
ls -a
{% endhighlight %}

Displays hidden files when displaying the names of files and directories inside the current working directory.

{% highlight shell %}
ls -l
{% endhighlight %}

Displays permissions to files and directories in the current working directory; also displays other additional information such as owner name, group, file size and the time of last modification.

{% highlight shell %}
ls -la
{% endhighlight %}

displays permissions to files and directories in the current working directoy; including hidden files. Also displays other additional information. This argument is a combination of both -a and -l and combines the output of both.

**pwd - prints the working directory to the screen**

{% highlight shell %}
pwd
{% endhighlight %}

Prints the current working directory to screen, such as \home\cale

**whoami - returns the username of the current user**

{% highlight shell %}
whoami
{% endhighlight %}

returns the current username, such as cale or admin.

### Reading files
The following details commands that are helpful when reading files

**cat - displays the contents of a file**

{% highlight shell %}
cat updates.txt
{% endhighlight %}

displays the content of the updates.txt file

**head - displays the first 10 lines of a file**

{% highlight shell %}
head updates.txt
{% endhighlight %}

displays the first 10 lines of the updates.txt file

{% highlight shell %}
head -n 5 updates.txt
{% endhighlight %}

displays only the first 5 lines of the file.
the -n option allows the user to specify the _number_ of lines to return.

less - returns the content of a file one page at a time

{% highlight shell %}
less updates.txt
{% endhighlight %}

returns the content of updates one page at a time; the less command changes the terminal window to a display which allows users to easily move forward and backward through content.

**tail - displays the last 10 lines of a file**

{% highlight shell %}
tail updates.txt
{% endhighlight %}

displays the last 10 lines of the updates.txt file

{% highlight shell %}
tail -n 5 updates.txt
{% endhighlight %}

returns the last 5 lines of updates.txt. The -n option allows the user to specify the number of lines to return.

### Filter content
These commands are useful for filtering content.

**find - searches for directories and files that meet the specified criteria**

{% highlight shell %}
find \home\cale\projects
{% endhighlight %}

searches for all files starting at the projects directory

{% highlight shell %}
find \home\cale\projects -iname "*log*"
{% endhighlight %}

searches for all files in the projects directory that contain the work log in the filename.
-iname searches for a specified string and is not case-sensitive; * is a wildcard and can represent zero or more unknown characters.

{% highlight shell %}
find \home\cale\projects -mtime -3
{% endhighlight %}

Searches for all files in the projects directory that have been modified within the past 3 days.
-mtime bases its search for files or directories that were modifed within the specified number of days.

{% highlight shell %}
find \home\cale\projects -nmin -15
{% endhighlight %}

Searches for all files in the projects directory that have been modified within the past 15 minutes.
-nmin bases its search for files or directories that were modified within the specified number of minutes.

**grep - searches within a specified file and returns all lines containing a specified string.**

{% highlight shell %}
grep OS updates.txt
{% endhighlight %}

searches the updates.txt file and returns all lines containing the string OS

**\| (piping) - sends the output of one command as the input of another command for further processing.**

{% highlight shell %}
ls \home\analyst\reports | grep users
{% endhighlight %}

redirects the standard output of ls \home\cale\reports to be standard input for the grep users command, meaning the grep users identifies files and subdirectories in the \home\cale\reports directory that contain the string users within their filename.

{% include note.html content="There is a lot that you can do with piping, It is crucial to understand the basic concept as we will be using this later." %}
