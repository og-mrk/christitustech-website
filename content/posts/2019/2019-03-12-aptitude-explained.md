---
title: Aptitude Explained
author: Chris Titus
type: post
date: 2019-03-12T20:35:00+00:00
url: /aptitude-explained/
image: https://www.christitus.com/wp-content/uploads/2019/03/aptitude-e1570564649126.jpg
categories:
  - Linux
tags:
  - Aptitude
---
In this article, I am going over the aptitude command and explaining all of the commands and usage that goes with its usage. <!--more-->

### Install Aptitude

Run the following command to install aptitude and task select: **sudo apt install aptitude tasksel**

## Why Aptitude?

Aptitude provides greater dependency resolution and wildcard installations. Making installing or reinstalling entire packages far easier. For instance the following command installs KDE in a simple command: `aptitude install ~t^desktop$ ~t^kde-desktop$`

### **aptitude install**

  * install one or more packages:
      * `sudo aptitude install gedit`
  * remove a package
      * `sudo aptitude install gedit`
  * purge a package
      * `sudo aptitude install gedit_`
  * hold a package at its current version
      * `sudo aptitude install gedit=`
  * build dependencies for a package
      * `sudo aptitude install gedit&BD`

### aptitude remove, purge, reinstall

These are the same as using the above commands under install, however, you can utilizing these independent commands with wildcards like below

  * `sudo aptitude purge ^kde-desktop$`

### aptitude hold, unhold, keep

  * hold is the same as the install, but again I like to use this long hand version when utilizing wildcards. 
  * **unhold** &#8211; is a great way to release held packages
  * **keep** &#8211; I **DO NOT USE** because it merely cancelled scheduled tasks for that package&#8230; only it will continue to be upgraded later. 

### aptitude update, safe-upgrade, full-upgrade

  * **update** &#8211; updates the cache
  * **safe-upgrade** &#8211; upgrades all packages but will not remove unused packages
  * **full-upgrade** &#8211; upgrades all packages but **WILL** remove unused packages
  * 

### aptitude search

  * **search <package>** &#8211; searches for the package, these search results can use wildcards, be sorted, and culled as needed using various options
  * search examples:
      * Search for packaged installed from outside stable repo
          * `aptitude search '?narrow(?installed, !?archive(stable))'`
      * Search for packages installed by the testing repo but not stable
          * `aptitude search '?narrow(?installed, ?archive(testing) !?archive(stable))'`
      * List installed packages
          * `aptitude search ~i`
      * List reverse dependencies for gedit
          * `aptitude search ~Dgedit`
      * show broken packages
          * `aptitude search ~b`
      * display packages on hold
          * `aptitude search ~ahold`
      * Find and install all packages with the name tightvnc in it
          * `aptitude search ~ntightvnc`
      * Install a specific version of a package
          * `aptitude install php=5.6`

### **aptitude show**

  * **aptitude show <package>**
      * displays information about the package

### aptitude why, why-not

  * **aptitude why <package>** &#8211; explains why a package can&#8217;t be installs because of a missing dependency
  * **aptitude why-not <package>** &#8211; show conflicts in which the package dependency can not be installed

### aptitude clean and autoclean

  * **aptitude clean** &#8211; removes all previously downloaded packages from the cache directory
  * **aptitude autoclean** &#8211; removes cached packages which no longer exist in your repositories

### aptitude search terms

<https://www.debian.org/doc/manuals/aptitude/ch02s04s05.en.html#tableSearchTermQuickGuide>

## Video Walkthrough

[![aptitude-yt](https://img.youtube.com/vi/xca3Ywf54N0/0.jpg)](https://www.youtube.com/watch?v=xca3Ywf54N0)  
_Note: YouTube Video - Hold Ctrl + Left Click to open in new window_

I live stream on [Twitch][1] and encourage you to drop in and ask a question. I regularly publish on [YouTube][2] and [christitus.com][3], but if you need immediate assistance, check out our discord channel at [Chris Titus Tech Discord][4].

 [1]: https://twitch.tv/christitustech
 [2]: https://www.youtube.com/c/ChrisTitusTech
 [3]: https://www.christitus.com/
 [4]: https://www.christitus.com/discord