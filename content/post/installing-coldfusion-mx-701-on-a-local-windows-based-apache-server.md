+++
title = "Installing ColdFusion MX 7.0.1 on a local Windows-based, Apache, server"
description = "In this article, we'll be walking through an installation of ColdFusion MX 7.0.1, Developer's Edition. Since we've already covered the installation of ColdFusion MX 6.1, Developer's Edition, you may already have CFMX 6.1 on your computer, like I did while writing this guide. If you do, that's okay (since I do). Otherwise, your installation will vary slightly."
draft = false
comments = true
date = "2006-03-31T00:21:00-06:00"
modified = "2007-09-06T22:13:39-05:00"
slug = "Installing-ColdFusion-MX-701-on-a-local-Windows-based-Apache-server"
blogengine = "8683fc84-32e4-4c1f-a8ca-acbf4bf6061f"
categories = ["software", "tutorials / guides"]
tags = ["coldfusion", "apache"]
+++

<div class="note">
<p>
<em>Note: For information on updating to ColdFusion MX 7.0.2, see <a href="http://strivinglife.com/words/post/Upgrading-our-installation-of-ColdFusion-MX-701-on-a-local-Windows-based%2c-Apache%2c-server.aspx">Upgrading our installation of ColdFusion MX 7.0.1 on a local Windows-based, Apache, server</a>.</em>
</p>
<p>
Update: October 10, 2006 @ 7:11 pm - Thanks to Michael Bryce for his helpful comments regarding this documentation.
</p>
</div>
<p>
In this article, we&#39;ll be walking through an installation of ColdFusion MX 7.0.1, Developer&#39;s Edition. Since we&#39;ve already covered the installation of <a href="http://strivinglife.com/words/post/Installing-ColdFusion-on-a-local-Windows-based%2c-Apache%2c-server.aspx">ColdFusion MX 6.1, Developer&#39;s Edition</a>, you may already have CFMX 6.1 on your computer, like I did while writing this guide. If you do, that&#39;s okay (since I do). Otherwise, your installation will vary slightly.
</p>
<p>
First, we&#39;ll need to download the installer for the Developer&#39;s Edition. This can be downloaded from <a href="http://www.macromedia.com/software/coldfusion/trial/">http://www.macromedia.com/software/coldfusion/trial/</a>. The download size is almost 300 MB, so you may have a wait on your hands.
</p>
<p>
While you&#39;re waiting, if you&#39;ve already installed ColdFusion MX 6.1, you can backup the CFIDE and cfdocs folders in your Web directory. If you&#39;ve been following along, this would be c:\home\ (or whatever your <strong>DocumentRoot</strong> has been set to in your Apache httpd.conf file). Put a copy in a new folder called CFMX6.1_docs.
</p>
<p>
Now, even if you haven&#39;t installed CFMX 6.1, make a copy of your httpd.conf file, found in C:\Program Files\Apache Group\Apache\conf, and place it along with your other httpd.conf backups, or in your downloads folder (c:\home\downloads\ if you&#39;ve been following along). Make a note that this is before the installation of CFMX 7.0.1. For example, httpd_20060319_PreCFMX7.01.conf (where 20060319 is the last date this file was changed).
</p>
<p>
Also, make sure ColdFusion MX 6.1 is stopped (and that it won&#39;t start up when you start your computer). Remember, this is in the Services control panel, and the item you want is the ColdFusion MX Application Server. Change this to Manual, and make sure it&#39;s stopped. If you haven&#39;t installed ColdFusion MX 6.1 before, then skip this step.
</p>
<p>
Note, you could just uninstall ColdFusion MX 6.1 as well. Your call, depending upon how much hard drive space you have.
</p>
<p>
Once your download has completed, start the installer.
</p>
<p>
Click next, reading as you go, until you&#39;re asked where to install ColdFusion MX 7. Keep the default of C:\CFusionMX7\.
</p>
<p>
Next, if 6.1 is installed, you&#39;ll have the ability to either configure Apache to use 7.0.1, or use ColdFusion MX 7.0.1&#39;s built-in server to run both 6.1 and 7.0.1. We don&#39;t really need both, so let&#39;s just &ldquo;Configure my web server for ColdFusion MX (recommended)&rdquo;.
</p>
<p>
Next, you&#39;ll need to &ldquo;Add Web Servers/Sites&rdquo;. Enter the following information.
</p>
<p>
Web Server: Apache<br />
Configuration Directory: C:\Program Files\Apache Group\Apache\conf<br />
Directory and file name of server binary: C:\Program Files\Apache Group\Apache\Apache.exe
</p>
<p>
Select OK, followed by Next.
</p>
<p>
On the next screen, change the web root to c:\home (or whatever your <strong>DocumentRoot</strong> has been set to in your Apache httpd.conf file), and select Next. Here, enter an Administrator password twice. On the next, keep RDS enabled, and just use the same password you entered for the Administrator.
</p>
<div class="tip">
<p>
Thanks to Mike Bryce for pointing out that there are actually two places you need to enter your Web root directory. The first is for the DocumentRoot, and the next is a dozen lines down in a Directory tag. The following is a snippet from the Apache 1.3.x httpd.conf file, which is very similar to the Apache 2.0.x httpd.conf file (for this particular section). The two important lines are <strong>bold</strong>.
</p>
<blockquote>
	<p>
	#<br />
	# DocumentRoot: The directory out of which you will serve your<br />
	# documents. By default, all requests are taken from this directory, but<br />
	# symbolic links and aliases may be used to point to other locations.<br />
	#<br />
	<strong>DocumentRoot &quot;c:/home&quot;</strong>
	</p>
	<p>
	#<br />
	# Each directory to which Apache has access, can be configured with respect<br />
	# to which services and features are allowed and/or disabled in that<br />
	# directory (and its subdirectories). <br />
	#<br />
	# First, we configure the &quot;default&quot; to be a very restrictive set of <br />
	# permissions. <br />
	#<br />
	&lt;Directory /&gt;<br />
	Options FollowSymLinks<br />
	AllowOverride None<br />
	&lt;/Directory&gt;
	</p>
	<p>
	#<br />
	# Note that from this point forward you must specifically allow<br />
	# particular features to be enabled - so if something&#39;s not working as<br />
	# you might expect, make sure that you have specifically enabled it<br />
	# below.<br />
	#
	</p>
	<p>
	#<br />
	# This should be changed to whatever you set DocumentRoot to.<br />
	#<br />
	<strong>&lt;Directory &quot;c:/home&quot;&gt;</strong><br />
	</p>
</blockquote>
</div>
<p>
Finally, you&#39;ll see that ColdFusion MX 7.0.1 requires 426 MB of space, so go ahead and Install.
</p>
<p>
Once the installation has completed, go backup the httpd.conf file again (httpd_20060330_PostCFMX7.01.conf was mine). Next, restart Apache, and head over to the ColdFusion Administrator, at <a href="http://localhost/CFIDE/administrator/index.cfm">http://localhost/CFIDE/administrator/index.cfm</a>.
</p>
<p>
Type the password that you just created, which will begin the server configuration, which may take a short while.
</p>
<p>
Since we&#39;ve already setup some data sources (if you&#39;ve been following along), we&#39;ll need to do some migration. It&#39;ll first export your settings, and then import them. Finally, click OK to start the ColdFusion Getting Started Experience.
</p>
<p>
Note that index.cfm may need to be setup as a directory index. Open the httpd.conf file, search for DirectoryIndex, and add index.cfm and index.cfml to the second instances&#39; line. For example:
</p>
<blockquote>
	<p>
	DirectoryIndex index.php index.cfm index.cfml index.html index.htm
	</p>
</blockquote>
<p>
Restart Apache if you need to add these.
</p>
<p>
If you&#39;ve already setup MySQL or PostgreSQL, or both, then you can now run the CFM files that we created early to verify our connections, as well as use the Data Sources area (under Data &amp; Services). If you&#39;re testing PostgreSQL, make sure you copy the jar file to the C:\CFusionMX7\lib folder (if you&#39;ve been following along, something along the lines of postgresql-8.1-405.jdbc3.jar).
</p>
<p>
And with that, you&#39;ve successfully setup ColdFusion MX 7.0.1 on an Apache server.
</p>
<p>
You may want to setup ColdFusion MX 7 Application Server (in Services) to startup manually, instead of automatically.
</p>
<hr />
<p>
Note that it&#39;s completely possible to now run both ColdFusion MX 6.1 and 7.0.1 on the same instance of Apache, albeit not at the same time. The following is only for advanced users.
</p>
<p>
You&#39;ll remember that we created a copy of the CFIDE and cfdocs folders from ColdFusion MX 6.1. If you now create a copy of these folders for ColdFusion MX 7.0.1, you&#39;ll have a copy of each folder for each installation. I also suggested you create a backup of your httpd.conf file both before and after our upgrade. If you do a comparison on the httpd.conf file, using a program like WinMerge, you&#39;ll see the exact lines that got changed.
</p>
<p>
Stop ColdFusion MX 7 Application Server, and Apache. Now, swap (making sure you don&#39;t overwrite your copy of the MX 7 files) the httpd.conf file and CFIDE and cfdocs folders from the 7.0.1 installation, to the 6.1 installation. Start Apache, and once it&#39;s started, start the ColdFusion Application Server (for 6.1). Hit the Administrator page and you&#39;re now running 6.1.
</p>
<p>
You can switch back to 7.0.1 at any time by stopping the Application Server, Apache, and swapping the two folders and one file.
</p>
<div class="note">
<p>
Keep in mind that if you try to log in to ColdFusion Administrator, but see &#39;gobbledygook&#39;, that probably means that you&#39;ve got the wrong CFIDE and cfdocs folders for the version you&#39;re running. Swap in the correct folders, or change to the other version.
</p>
</div>
<p>
Have fun, and stay safe.
</p>
<p>
<a href="http://strivinglife.com/local-apache-server/">View all of the steps to creating a local Web server, for development.</a>
</p>

