---
layout: post
title: Managing Users in Linux
date: 2024-10-07 16:00:00 +0930
---
### Managing users in Linux and their permissions
The following will be useful for administrating users via a Linux system; this assumes familiarity with ls -la.

### Permissions and ownership

Recall that {% highlight shell %}ls -la{% endhighlight %} returns a list of files and directories and their permissions

![ls-la-return]({{ site.baseurl }}/images/ls-la.png)

Permissions in Linux are printed as a 10 character string, drwxrwxrwx.
The first character represents whether permissions are associated with a directory (d)
or a file (-).

The next 9 characters represent permissions in groups of 3 characters for the three groups; User, Group and then other (everyone else).
R = read, W = write, x=execute, - (hyphen) = null.

**chmod - change permissions on files and directories**

{% highlight shell %}
chmod u+rwx, g+rwx, o+rwx login_sessions.txt
{% endhighlight %}

Changes user (u), group (g), and other (o) permissions to add (+) read (r), write (w), and execute (x) permissions for the login_sessions.txt file

{% highlight shell %}
chmod u-wx, u+r, g-wx, g+r, o-rwx projects/.project_x.txt
{% endhighlight %}

Hidden files start with a . (period)
Changes privilege's so that only the user and the group can read the file.

{% highlight shell %}
chmod g-rwx, o-rwx drafts
{% endhighlight %}

changes the directory permissions of the drafts folder so that only the user can interact with the directory.

**chown - change ownership of a file or directory, used with sudo (more on sudo below)**

{% highlight shell %}
sudo chown cale access.txt
{% endhighlight %}

Changes the user owner of access.txt file to cale.

{% highlight shell %}
sudo chown :security access.txt
{% endhighlight %}

changes the group owner of access.txt to security, a colon (:) must be entered before the group name.

**groupdel - deletes a group from the system, used with sudo**

{% highlight shell %}
sudo groupdel accounting
{% endhighlight %}

deletes accounting as a group

**sudo - super user do**
Temporarily grants elevated permissions to specific users, users must be in a sudoers file to have access to sudo.

{% highlight shell %}
sudo useradd cale
{% endhighlight %}

Grants elevated permissions to the user running this command so that this user can use the useradd command to add cale as a new user to the system.

**useradd - adds a new user, used with sudo**

{% highlight shell %}
sudo useradd -g security cale
{% endhighlight %}

adds cale as a new user and uses the -g option to set their primary group as security.

{% highlight shell %}
sudo useradd -G finance,admin cale
{% endhighlight %}

adds cale as a new user and uses the -G option to add them to the supplemental groups of finance and admin.

**userdel - deletes a user from the system, used with sudo**

{% highlight shell %}
sudo userdel cale
{% endhighlight %}

deletes cale as a user.

{% highlight shell %}
sudo userdel -r cale
{% endhighlight %}

deletes cale as a user and removes all file in their home directory.

**usermod - modify an existing user, use with sudo**

{% highlight shell %}
sudo usermod -g finance cale
{% endhighlight %}

uses the -g option to change the existing cale user's primary group to be the finance group.

{% highlight shell %}
sudo usermod -G accounting cale
{% endhighlight %}

uses the -G option to replace any supplemental groups that the existing cale user is in with the supplemental accounting group.
Removes all other groups cale is in.

{% highlight shell %}
sudo usermod -a -G finance cale
{% endhighlight %}

uses the -a -G options to append the finance group to the user cale, this will not remove existing user groups from the user.

{% highlight shell %}
sudo usermod -d /home/cale_b
{% endhighlight %}

uses the -d option to change the existing cale user's home directory to /home/cale_b.

{% highlight shell %}
sudo usermod -L cale
{% endhighlight %}

uses the -L option to lock the existing cale user's account so that they cannot log in.

{% highlight shell %}
sudo usermod -l caleb cale
{% endhighlight %} 

uses the -l option to change the existing cale user's login name to caleb.