+++
title = "Installing Apache to a Windows-based computer, locally"
description = "In this tutorial, we'll be walking through the installation of Apache 1.3 to an average home computer running Windows XP, Home Edition (SP1).  Anyone running an average home computer, with a newer version of Windows, like XP, should be able to follow these steps and have an installation of their own.  Older versions of Windows, like 98 and Me, should also be able to handle an installation, although some steps may differ slightly."
draft = false
comments = true
date = "2006-02-16T17:24:00-06:00"
modified = "2009-12-21T08:15:34-06:00"
slug = "Installing-Apache-to-a-Windows-based-computer-locally"
blogengine = "6b256599-e702-4993-8306-995e9e6e977a"
categories = ["software", "tutorials / guides"]
tags = ["apache"]
+++

<p>In this tutorial, we'll be walking through the installation of Apache 1.3 to an average home computer running Windows XP, Home Edition (SP1). Anyone running an average home computer, with a newer version of Windows, like XP, should be able to follow these steps and have an installation of their own. Older versions of Windows, like 98 and Me, should also be able to handle an installation, although some steps may differ slightly.<!--more--><!--adsense--></p>
<p>I use Firefox, and have goofed around with Linux (installation and usage), but I nonetheless recommend Windows XP. With technology as it is, you can purchase a fairly good computer for under $500. I also recommend at least 512MB of memory, and a processor speed of 1GHz or more. Again, today's computers easily meet or surpass these numbers.</p>
<h3>Why would I want to install Apache to my machine?</h3>
<p>There's a number of very good reasons to install Apache locally. If you're interested in Web site design or programming, or would like to host your own Web site, Apache is a great resource.</p>
<p>There is an alternative, however, which is Microsoft's IIS. While many versions of Windows ship with IIS (Microsoft's Internet Information Services), not all do, and a large portion of cheap Web site providers don't use IIS. The version of IIS you may be able to install through your installation of Windows may also be severely limited in just how much it can do. While it will indeed function, Apache functionality is based almost solely upon your hardware and software environment.</p>
<h3>What can I do with Apache? What can't I do?</h3>
<p>Immediately after installation, you'll be able to run a basic Web site on your own computer. Depending upon your connection to the Internet, you may also be able to allow other people to access your site. (However, you'll never want to do this immediately after installation for a number of very important security reasons.) You'll also be able to install other applications which will allow you to go beyond simple Web pages. For example, you can install PHP and MySQL to create dynamic pages, and allow you to install other applications, like WordPress, and other free content management systems.</p>
<p>What you won't be able to do is create dynamic Web sites without installing another language (as pointed out above, like Apache or MySQL). You also won't be able to run certain programming languages like ASP or ColdFusion, without the proper resources. On the other hand, if you install IIS, you can usually run ASP, a dynamic programming language, almost right away.</p>
<p>In other words, Apache is a great initial step that will provide a backbone for expansion.</p>
<h3>How difficult is it to install Apache?</h3>
<p>If you can install a program on Windows, you're in great shape. An installation of Apache will involve a little more work, in that you'll need to modify some files manually, but it's fundamentally the same as installing any program on Windows.</p>
<h3>I'm ready to install. How do I start?</h3>
<p>First, you need to determine what you'll be installing Apache for. Will you be installing Apache so you can learn how to create a Web site? So you can practice coding in a language? Or will you be installing Apache so that you can have a development server, along with your actual site with some other provider?</p>
<p>This is an important question to ask yourself because you have options when you install Apache (as well as other software) yourself. Apache currently has two versions available, both of which function and are available for installation. However, the newer version (and 'subversions') may not be available with all hosts (Web site providers).</p>
<p>If you'll be using Apache just to work on a generic Web site, you'll probably want to look at installing Apache 2.x. On the other hand, if you'd like to do development work, or have a test site, where you can do your testing, and then upload the finished product to a host, you should look at Apache 1.x. Of course, this really only applies if you'll be using the full functionality of either. If you just want to work with plain old HTML files, do yourself a favor and install Apache 1.x, as it's slightly better to run the older version of Apache with PHP. Of course, if you do have a host, it's probably a good idea to use what they're using &ndash; it makes things as similar in the two environments as possible.</p>
<p>For this installation, we'll be installing Apache 1.3.34, the most current version of Apache 1.x.</p>
<h3>Initial steps before installation</h3>
<p>Before we install Apache, we should prepare our environment, in this case, our computer.</p>
<p>First, we should verify that our anti-virus software is updated, and that our computer is free of viruses. Running a quick spyware/adware check would also be beneficial.</p>
<p>We'll also want to run a quick defragmentation on our computer.</p>
<p>Next, determine where you want your Web site to reside. When you create a Web site, the pages that you want to display must reside in a folder. For this guide, I recommend it be a folder very close to your C drive. For example, C:\wwwroot\, or C:\web\. Based on an installation on Linux, you may want to do something like C:\home\website\public_html\, where website can be changed on whim. For example, I might so C:\home\strivinglife\public_html\ for StrivingLife.net, and C:\home\jamesrskemp\public_html\ for JamesRSkemp.net. This gives you the great ability to have a number of different Web sites locally, with just one installation of Apache.</p>
<p>For this guide, I'll be assuming that we'll be installing our Web site to C:\home\website\public_html\. So, let's go ahead and create these folders.</p>
<p>Next, we'll need to download a copy of Apache. Since we'll be installing the current version of Apache 1.x, 1.3.34, we'll head over to the Apache HTTP Server Project at http://httpd.apache.org/, and download apache_1.3.34-win32-x86-no_src.exe or .msi. The latter will save you about 3 MB of download time. If you click on the Other files link, then binaries/, win32/, you'll see the files available for download. For this guide, we'll be using the MSI file.</p>
<p>I recommend you download this file to a new folder on your computer, specific to this guide. The sole reason being so that you can easily back this folder up, since, depending upon how much you end up installing, you'll need to download a number of files. No sense doing something twice when you can do it once the right way.</p>
<p>Now that you've downloaded the file, it's time to install.</p>
<h3>Installing Apache 1.3.34</h3>
<p>First, we'll open the MSI file we just downloaded. It's pretty obvious that we need to click a bunch of Next buttons, the first one at the 'splash' screen, and the next one after agreeing to the License.</p>
<p>There's some important information on the next screen, worth reading &ndash; since it's so short, it's hardly a time-dump.</p>
<blockquote>Apache should never be used as a production server under any consumer operating system such as Windows 95, 98, or ME (Millennium Edition). Only Windows NT 4.0 or 2000 should be considered, and only with appropriate NTFS file system and user security administration. Apache runs on these consumer Windows environments only to provide test, development or trusted intranet server platforms.<br />Apache on Win32 should be considered initial-release quality code. It has not been subjected to the same stresses on its stability and security that the Unix releases have enjoyed, so there is a greater possibility of undiscovered vulnerabilities to stability or security of the Win32 port.</blockquote>
<p>Again, while you'll be able to actually run a Web site that others will be able to see, it's not a good idea to do so at this point. There's a number of things to understand before you do so, the scope of which is beyond this guide.</p>
<p>On the next screen, you'll be prompted to enter server information. For our installation, we'll be typing localhost into the first two fields, and our email into the third. If you're running Windows XP, run Apache as a service for all users.</p>
<p>On the next screen, you'll be prompted whether you want to do a Complete or a Custom installation. Pick Custom, and leave things how they are. If you want to install Apache to somewhere other than C:\Program Files\Apache Group\, you can do so, but I don't recommend it. Then hit the Install button, and Finish to complete the installation.</p>
<p>Once the installation has completed, Apache will start as a service. It will also start whenever we start Windows. You can confirm that Apache is running in a number of ways. First, you can check Task Manager for the Apache.exe process. Secondly, you can check running services in Windows XP. In the Control Panel, you'll find an Administrative Tools folder, which has a Services shortcut. There will be an Apache item listed here, as well as it's status. You can restart, stop, and start Apache from here. The final way is to type http://localhost/ or http://127.0.0.1/ into your browser. If Apache is setup and running, you'll see a message saying that Apache has been setup successfully.</p>
<p>If you're wondering where this content is coming from, when Apache installs itself it creates a htdocs folder in the installation directory. In the standard case, C:\Program Files\Apache Group\Apache\htdocs\ However, in my opinion, this is far too deep for any good, which is why we created our C:\home\ folders.</p>
<p>To change this, we'll have to make a modification to a text file. We can modify this by going to Start &gt; All Programs &gt; Apache HTTP Server &gt; Configure Apache Server &gt; Edit the Apache httpd.conf Configuration File. You can also navigate to C:\Program Files\Apache Group\Apache\conf\httpd.conf and open this file in Notepad.</p>
<p>You need to now do a search for "DocumentRoot".</p>
<blockquote># DocumentRoot: The directory out of which you will serve your<br /># documents. By default, all requests are taken from this directory, but<br /># symbolic links and aliases may be used to point to other locations.<br />#<br />DocumentRoot "C:/Program Files/Apache Group/Apache/htdocs"</blockquote>
<p>We're going to change this to our directory, C:\home\website\public_html, but note the differences in the slashes.</p>
<blockquote>DocumentRoot "C:/home/website/public_html"</blockquote>
<p>We'll do one more find for "DocumentRoot", or scroll down just a bit, to find another line we need to change, to the same directory.</p>
<blockquote># This should be changed to whatever you set DocumentRoot to.<br />#<br />&lt;directory "C:/Program Files/Apache Group/Apache/htdocs"&gt;</blockquote>
<p>Save this file, and perhaps even make a backup copy, which you can place in the same folder you downloaded the Apache installer to.</p>
<p>If you go to localhost (http://localhost/), you'll notice that it's still showing the old location. You'll need to restart Apache for the configuration changes to take effect. You can do this via the Start menu, or vai the Services.</p>
<h3>Post-installation</h3>
<p>Now that we've successfully installed Apache, we can begin working on our Web site. To do this, we'll just need to create our HTML files, and place them in the folder we created above &ndash; C:\home\website\public_html\. We can also create new folders under this folder, to add new folders to our site.</p>
<p>Note that you'll need to create an index.html file if you don't want to see the Apache file structure.</p>
<p>To do this, open Notepad and paste the below into a blank document.</p>
<pre class="code"><code class="html">&lt;html&gt;
&lt;body&gt;
&lt;p&gt;Hello world!
&lt;/body&gt;
&lt;/html&gt;</code></pre>
<p>Save this document to the public_html folder, and refresh, or go to, http://localhost/. You should see "Hello world!" displayed in the browser. Notice that you don't have to restart Apache to see this change. Also, if you change the filename to index.htm, or home.html, or home.htm, it will go back to displaying the basic file structure. If you click on the file, however, it will display the appropriate content.</p>
<p><a href="http://strivinglife.com/local-apache-server/">View all of the steps to creating a local Web server, for development</a>.</p>
