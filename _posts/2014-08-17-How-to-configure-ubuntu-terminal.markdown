---
layout: post
title: How to customize ubuntu terminal
date: 2014-08-17
categories: Configuration
---

Do you find your ubuntu terminal prompt weird with some unnecessary text? Do you find your terminal title irritating?  If you feel the same, you are at the right place. Here, I would like to give clarity on how to customize your terminal *prompt* and *title*

To customize terminal, you need to edit the _.bashrc_ file in our home directory. Before we proceed any further, lets create a backup for this file in case anything goes wrong. 
Please type the following command in your terminal in your home directory

	cp .bashrc .bashrc-backup

This command copies all the contents of _.bashrc_ to _.bashrc-backup_ 

## Bash Prompt ##
Now edit .bashrc file by typing the following command

	gedit .bashrc

Then locate this statement in the file

	PS1='${debian_chroot:+($debian_chroot)}\u@\h:\w\$ '

Replace that line with the follwing lines

	#PS1='${debian_chroot:+($debian_chroot)}\u@\h:\w\$ '
    PS1="[ ${debian_chroot:+($debian_chroot)}\u: \w ]\\$ "
    PS2="&gt; "

Now close your terminal and restart it. This will change your prompt to **[ username: ~ ]$**.

If you want to add some text to the bash you can add it this way

	PS1="[ ${debian_chroot:+($debian_chroot)}\u is awesome: \w ]\\$ "

Bash will now read as **[ username is awesome: ~ ]$**.

For detailed reference you can follow this [link](https://help.ubuntu.com/community/CustomizingBashPrompt)

## Terminal Title ##

Locate this code in .bashrc file

	case "$TERM" in
	xterm*|rxvt*)
      	PS1="\[\e]0;${debian_chroot:+($debian_chroot)}\u@\h: \w\a\]$PS1"
    	;;
	*)
    	;;
	esac

Add a # infront of PS1, then save the file. 
Go to Terminal -> Set Title and set your desired title. Now .bashrc will not be able to overwrite your title, everytime you open new terminal window. 

Now what if something goes wrong? 
All you need to do is revert back your changes. 
To do that just go back to your terminal and type the following 
	
	cp .bashrc-backup .bashrc

This will bring back your old terminal.