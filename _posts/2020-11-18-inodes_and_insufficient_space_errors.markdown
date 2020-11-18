---
layout: post
title:      "Inodes and Insufficient Space Errors"
date:       2020-11-18 21:21:25 +0000
permalink:  inodes_and_insufficient_space_errors
---


When I first started learning to code I was terrified of error messages. It didn’t help that I started out on a Windows machine. Using WSL and being very unfamiliar with Unix commands, there were definitely times when I had no clue what I was doing. That was fine for the most part, as long as learn open and learn submit worked, I didn’t have to worry or question much. As I moved through the program though I would feel the dread creep in on certain occasions when things didn’t go smoothly. A popup in VS Code related to my WSL plugin (everything seemed to work without the plugin, should I use it or not...wait...was I even using it before?), error messages trying to open or submit labs, issues connecting to GitHub, everything was confusing and scary. I was crazy jealous of my peers with Macs, who seemed to have a much easier time of things.

I know that Flatiron recommends using Macs for the exact reasons I’m talking about, but obviously the price is a hard pill to swallow. So, when I went shopping for a new laptop back in April I knew that I’d probably have to forego an Apple product, but I also knew that I didn’t want to keep having issues dealing with Windows. I’d heard of Linux for years, and after doing some research it sounded like the solution I’d been looking for – free, open-sourced, tons of variations (distros), safe, etc. I bought a Lenovo with much better specs than my last machine, which of course came with Windows installed. I wanted to keep Windows just in case I needed it for something in the future, so I did my research and decided to take steps to partition my hard drive in order to dual boot Windows and Linux. It took some time, but I chose a very stable distro called Cinnamon, and after some initial hiccups with internet connection and driver configurations it was pretty smooth sailing. 

It’s been about six months now, and I don’t think I’d ever go back to Windows. Similar to what I would hear about Macs, things just work on the Linux OS. It’s been really nice not having to worry about compatibility issues, virtual machines, or strange and confusing errors popping up out of the blue. Recently, though, I ran into a brand new problem I’d never heard of. I received an error that claimed there was no space left on my device...despite my partitions having plenty available memory for storage. Npm would start installing a package, but partway through I would start seeing the error messages cascade for dependency after dependency. I found out the error was related to inodes. 

Inodes contain information about files and directories. On the command line, if you run df -i, you will get a readout of  your filesystem and how many inodes are being used or are available for use on drives/partitions of your machine. Something to note, snap packages always show 100% usage of inodes, so if you see that just ignore it. If another drive looks close to 100% though, that’s likely the culprit. This command can be run to print out a list of files and directories present in a disk:
	
	`$ for I in /*; do echo $i; find $i |wc -l; done`

In the above command, I used /* to look in all directories, but you can narrow the search down further by specifying directories and placing the asterisk after to catch everything they contain. When looking around, try to find directories that have an unusually large number of files. Once you’re sure that it’s safe to delete the relevant junk, use the following command with your actual directory names to free up your space and get rid of those annoying error messages!
	
	`$ sudo rm -rf /home/userdir/junk`

