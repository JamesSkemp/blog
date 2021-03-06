+++
title = "Installing Apache 2.2.4 to a Windows-based computer, locally: Part 1"
description = "In this article, we'll be covering how to install Apache 2.2.4 to a local, Windows XP Home Edition, computer."
draft = false
comments = true
date = "2007-03-17T10:00:00-05:00"
modified = "2007-07-23T22:12:36-05:00"
slug = "Installing-Apache-224-to-a-Windows-based-computer-locally-Part-1"
blogengine = "78d1e330-f12e-46ff-951e-7eb534551c6c"
categories = ["article", "tutorials / guides"]
tags = ["apache"]
+++

<p>
In February 2006, I wrote an <a href="http://strivinglife.net/wordpress/2006/02/16/45/installing-apache-to-a-windows-based-computer-locally/">article covering the installation of Apache 1.3.34</a>, which can be found on my site, StrivingLife.net. In August 2006, I covered <a href="http://strivinglife.net/wordpress/2006/08/22/198/installing-apache-2059-to-a-windows-based-computer-locally-part-1/">the installation of Apache 2.0.59</a>. This time, I&#39;ll be covering the installation of the current version of Apache 2.2.x, Apache 2.2.4, to a Windows XP machine, for the purpose of local development.
</p>
<p>
While I&#39;ll be covering an installation of Apache 2.2.4 that will work along with Apache 1.3.x and Apache 2.0.x, this guide will work equally well if you&#39;re installing Apache 2.2.x by itself.
</p>
<!--more--><!--adsense-->
<p>
If you&#39;ve been following along with my <a href="http://strivinglife.net/wordpress/a-local-apache-web-server-on-a-windows-xp-computer/">other tutorials on this local server setup</a>, you may have setup Perl, PHP, MySQL, PostgreSQL, and/or ColdFusion, among other things. Later parts will cover these setups in further detail.
</p>
<h4>My environment</h4>
<p>
The computer I&#39;ll be using for this installation is an HP Pavilion a620n, 2.20 GHz, 960 MB (1 GB) of RAM, and with Windows XP Home, SP2.
</p>
<h4>Downloading Apache</h4>
<p>
The first thing, obviously, is to download the current version of Apache 2.2.x from <a href="http://www.apache.org/" onclick="window.open(this.href);return false;">http://www.apache.org/</a>. At the time of this writing, Apache 2.2.4 is the current release, and &quot;represents the best available version of Apache HTTP Server.&quot;
</p>
<p>
Since we&#39;re installing to Windows, we want to download the file apache_2.2.4-win32-x86-no_ssl.msi, which is under 4.5 MB in size. If you&#39;ve been following along with the other tutorials, then you&#39;ll want to save this file to the same location as your other download files. If you haven&#39;t been following along, save the installation file to a directory where you can save all of your installation files.
</p>
<p>
While the file is downloading, if you&#39;re currently running a version of Apache on your machine, stop the server, as we don&#39;t want it running while we do the installation. If you have any other services running that may be running through port 80 (other Web servers), you&#39;ll also want to stop those services. 
</p>
<p>
If you&#39;ve already installed Apache 2.2.x, you may want to backup the install directory (the default is C:\Program Files\Apache Software Foundation\Apache2.2\).
</p>
<h4>Installing Apache 2.2.4</h4>
<p>
Once the installation file has been downloaded, run the file to begin installation. Continue throught the first window, to the second, where you can read and accept the license agreement. On the next window there&#39;s a bit of additional text to read.
</p>
<p>
Finally, you&#39;ll be asked for server information. Since we&#39;re installing this locally, we&#39;ll be using <strong>localhost</strong> as both the Network Domain, as well as the Server Name. In Administrator&#39;s Email Address, enter your real email address. Last, install Apache HTTP Server 2.2 programs and shortcuts for &quot;All Users, on Port 80, as a Service&quot;.
</p>
<p>
You can now setup the server in a typical manner, or custom. Since we want to have control, select Custom.
</p>
<p>
On the first screen, you can select which features you want to install, and where they should be installed. We&#39;ll be installing everything, and leaving the installation directory as C:\Program Files\Apache Software Foundation\Apache2.2\.
</p>
<p>
And that&#39;s it. Press Install on the next screen to begin the installation.
</p>
<p>
Once the service has been created, you may recieve an alert from Windows Firewall regarding the Apache HTTP Server. Choose to Unblock this program.
</p>
<p>
In addition, if you&#39;ve already installed Apache, and have the Apache monitor running, you&#39;ll receive an error that the monitor is already running.
</p>
<p>
Once the installation has finished, press the Finish button.
</p>
<p>
Apache HTTP Server 2.2.4 will now be running, and by going to http://localhost/, you&#39;ll see the text &quot;It works!&quot; in your browser.
</p>
<p>
If you do not see this, or the service does not start, you can find an error.log file in the logs directory in your Apache install directory which can help you troubleshoot your issue.
</p>
<h4>Apache Service Monitor, and setting startup types </h4>
<p>
In your taskbar, there will now be an icon from the Apache Service Monitor. Using the monitor, you can easily start and stop the Apache HTTP Server, as well as access other services.
</p>
<p>
For now, hit the Services button to bring up the Services console. Next, right click on the Apache2 service, and select Properties. What we&#39;re going to do now is change the startup type from Automatic to Manual. This means that we&#39;ll need to manually start Apache whenever we restart our computer, but it also means that the service isn&#39;t unnecessarily running.
</p>
<p>
However, if you&#39;ll be running Apache every time you login, you may want to let Apache startup automatically when you log in. Either way, it&#39;s nice to know where you can change this.
</p>
<p>
While you&#39;re here, note that you can also see what version of Apache is running, in the Description field. 
</p>
<h4>Wait a second, what about the Apache 2.0.59 service?!?</h4>
<p>
If you&#39;ve installed Apache 2.0.59 previously, you may be wondering what happened to the Apache2 service for that version of Apache.
</p>
<p>
Unfortunately, Apache 2.0.59 and Apache 2.2.4 use the same service name. This means that any previous Apache2 services will be overwritten.
</p>
<p>
Luckily, with the help of Windows, Microsoft, and some advice from Mark Lennox (given in a <a href="http://strivinglife.net/wordpress/2006/09/16/228/installing-subversion-and-tortoisesvn-to-a-windows-xp-home-edition-sp2-local-machine-with-dreamweaver-8/">Subversion article</a>), we can create a service for Apache 2.0.59 a couple of ways.
</p>
<p>
First, run cmd via the Run command (Window + R, or via the Start menu). At the prompt, enter the following. Please note that you&#39;ll want to confirm that the path information is correct for you.
</p>
<blockquote>
	<p>
	sc create Apache2.0 binpath= &quot;\&quot;C:\Program Files\Apache Group\Apache2\bin\Apache.exe\&quot; -k runservice&quot; displayname= &quot;Apache 2.0&quot; depend= Tcpip/Afd
	</p>
</blockquote>
<p>
You can learn more <a href="http://support.microsoft.com/kb/251192/" onclick="window.open(this.href);return false;">creating Windows services using the SC tool (Sc.exe)</a> by reading support article 251192 on Microsoft.com.
</p>
<div class="tip">
<p>
You may also want to create new services for Apache 2.2.x, and Apache 1.3.x. However, keep in mind that once you change your configuration, you may need to remove/update the services that you create. Either way, the new services should display in the Apache Services Monitor.
</p>
<blockquote>
	<p>
	sc create Apache1.3 binpath= &quot;\&quot;C:\Program Files\Apache Group\Apache\Apache.exe\&quot; --ntservice&quot; displayname= &quot;Apache 1.3&quot; depend= Tcpip/Afd
	</p>
</blockquote>
<p>
(Note that there&#39;s two dashes in front of <strong>ntservice</strong>.)
</p>
<blockquote>
	<p>
	sc create Apache2.2 binpath= &quot;\&quot;C:\Program Files\Apache Software Foundation\Apache2.2\bin\httpd.exe\&quot; -k runservice&quot; displayname= &quot;Apache 2.2&quot; depend= Tcpip/Afd
	</p>
</blockquote>
<p>
If you&#39;ve been following along with my other tutorials, you may want to update your <a href="http://strivinglife.net/wordpress/2006/08/28/207/installing-apache-2059-to-a-windows-based-computer-locally-part-4/">batch files</a> so that they stop all the Apache services (Apache, Apache2, Apache1.3, Apache2.0, Apache2.2) and start our new services, depending upon which version you want to run (currently, that would be either Apache1.3 or Apache2.0).
</p>
</div>
<h4>Configuring Apache with httpd.conf</h4>
<p>
If we start Apache 2.2 back up, via services, and browse to http://localhost/ once again, we&#39;ll see that &quot;It works!&quot; screen. That&#39;s all well and good, but it&#39;s using C:\Program Files\Apache Software Foundation\Apache2.2\htdocs\ as the Web directory, from which is serves content, which is far too deep to dig.
</p>
<p>
It&#39;s better to create another folder, with less pathing information. I&#39;ve decided to use the shorter directory of C:\home\, however, you can create whatever folder you&#39;d like. In this directory, you&#39;ll store any files that you&#39;ll want to be served by Apache. There&#39;s exceptions to this statement, but, for now, we&#39;ll let it slide.
</p>
<p>
Once you&#39;ve created this directory, head over to the conf folder in the install directory of Apache 2.2.x (default of C:\Program Files\Apache Software Foundation\Apache2.2\conf\) and make a copy of the httpd.conf file. This copy will serve as the original, just in case something happens. This is a working version of the configuration file for Apache HTTP Server, so don&#39;t overwrite it (but if you do, there&#39;s a copy in the default folder). Now open the httpd.conf file.
</p>
<p>
With the httpd.conf file open, do a search for <strong>DocumentRoot</strong>. The second instance will take you to a line that reads as follows.
</p>
<blockquote>
	<p>
	DocumentRoot &quot;C:/Program Files/Apache Software Foundation/Apache2.2/htdocs&quot;
	</p>
</blockquote>
<p>
Change the quoted text to your Web root folder (make note of the direction of the slashes, and absence of a slash at the end). Since I created a folder at C:\home, I&#39;ll be using the following line.
</p>
<blockquote>
	<p>
	DocumentRoot &quot;C:/home&quot;
	</p>
</blockquote>
<p>
Find the next instance of <strong>DocumentRoot</strong> and you&#39;ll see this line of text two lines down.
</p>
<blockquote>
	<p>
	&lt;Directory &quot;C:/Program Files/Apache Software Foundation/Apache2.2/htdocs&quot;&gt;
	</p>
</blockquote>
<p>
Change the directory as you did just moments ago.
</p>
<blockquote>
	<p>
	&lt;Directory &quot;C:/home&quot;&gt; 
	</p>
</blockquote>
<p>
Note that in this file you can also change what port Apache 2.2.x will listen on. There&#39;s two instances of the port number, and a search for <strong>80</strong> will turn up both, if you choose the options we did above. Otherwise, you&#39;ll turn up four instances (as Apache will be listening on Port 8080).
</p>
<p>
Save the httpd.conf file and restart, or start, Apache.
</p>
<p>
If you go to http://localhost/ now, you&#39;ll either see a directory listing, or a Web page, depending upon whether you have an index.html file in your Web root. If this worked, then you can make a backup copy of your newly working httpd.conf file.
</p>
<p>
And with that, you&#39;ve setup Apache 2.2.4 on a local Web server.
</p>
<p>
In later guides, we&#39;ll cover the setting up of a number of additional services, but for now, you can work static Web pages.
</p>
<p>
If you&#39;ve followed some of <a href="http://strivinglife.net/wordpress/a-local-apache-web-server-on-a-windows-xp-computer/">my other tutorials</a>, you can easily switch between versions of Apache, but you&#39;ll need to configure any batch files you may use so that they stop the new Apache 2.2.x service.
</p>
<p>
Questions or comments can be left below, or emailed to me directly (email at the bottom of the page). Thanks for reading!
</p>

