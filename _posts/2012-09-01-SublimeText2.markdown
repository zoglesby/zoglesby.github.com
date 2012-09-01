---
layout: post
title: Sublime Text 2
---

{{ page.title }}
----------------
I love me some emacs, but while I was using OS X on a daily bases I started using [TextMate][1] on a daily basis. When I finally got a new computer that could run Fedora better then a Macbook Pro, I started to miss TextMate and that got me looking for an alternative. I finally found [Sublime Text 2][2] and it is a great editor.

Before anyone asks I am not sure why its better then gedit, I just enjoy it more. It also helps that on the rare occasion I need to use Windows at work (this is very rare) I can use the same editor with all the same features.

The only issue is that Sublime Text 2 is not open source, nor is their a package for it. This means that I must install more proprietary software on my computer (Skype and Spotify are the other two) and I needed to figure out the best way to work with it.

After looking around online I found an install guide that works better then anything else I have seen [here][3]. Their are a few issues with it but most of them are outlined in the comments.  


	Download Sublime Text 2
	tar -xvf sublime_text_file.tar.gz
	mv Sublime_Text_2/ /opt/Sublime_Text_2
	touch /usr/bin/sublime
	chmod 755 /usr/bin/sublime
	vi /usr/bin/sublime

Paste the following it in (this will create the executable)
	
	#!/bin/sh
	export SUBLIME_HOME="/opt/Sublime_Text_2"
 
	$SUBLIME_HOME/sublime_text $*

To create the desktop icon edit `/usr/share/applications/sublime.desktop`. Note that this is one of the issues that was in the original posts instructions (the icon was moved because they added more sizes) 
	
	[Desktop Entry]
	Encoding=UTF-8
	Name=Sublime
	Comment=Sublime Text Editor
	Exec=sublime
	Icon=/opt/Sublime_Text_2/Icon/128x128/sublime_text.png
	Terminal=false
	Type=Application
	Categories=GNOME;Application;Development;
	StartupNotify=true

Thats it, you should be able to open the `Applications` menu from Gnome 3 and search for Sublime. It is also worth noting that there is a nice [github project][4] with an install guide for getting more plug-ins.

[1]: http://macromates.com/
[2]: http://www.sublimetext.com/2
[3]: http://www.tutology.net/category/editors/sublime-text-editor-linux
[4]: https://github.com/mrmartineau/SublimeTextSetup