---
layout: post
title:      "Pry Pry Again"
date:       2020-07-28 22:24:54 +0000
permalink:  pry_pry_again
---


Pry is a really useful tool for debugging and testing pieces of your applications. I am still very much a beginner when it comes to writing code, and one of the hardest adjustments for me to make while learning has been finding ways to test my code. In the beginning, sure, it was relatively straightforward. Open up IRB or jump into a REPL somewhere online, write some methods and see if the results were as expected. Rinse. Repeat.

Eventually though, the development environment grew, the file structures became more complex, and the simple methods I was using to test my code could no longer meet my needs. For someone who can’t yet write their own tests with confidence, PRY can be a godsend. When I was first introduced to PRY it was solely through the binding.pry command. Insert the binding into the code, run the code, and experiment in the terminal to get a deeper understanding of what’s happening when the code is actually executed. Once I got a hang of how it works I recognized its value and started using it more often, but it wasn’t until I watched a RailsCast covering its features that I realized just how powerful it can be.

I came across a RailsCast a few months back that dove deeper into PRY and its various capabilities. Within the first minute or two it was clear that I did not have a good understanding of what it could be used for.

To use pry in the Rails console instead of IRB and give it access to the full Rails environment, run:
	pry -r ./config/environment

Due to the size of Rails, the length of time it has been around, and the devoted community that has come up around it, at times it can be tough to know if a particular tool or gem is the best one for the job. As a relative beginner, I see no clear way around that problem, so I naturally fall back to using the tools I hear about from people who know a lot more than me.

**USEFUL COMMANDS**
cd - changes current scope.
	ex. cd Article

ls - lists all the variables and methods. Some PRY commands support flags, and you can get a list of them by passing the -h flag.

nesting - will tell you where you’ve been while using PRY.

show-doc - will show you the documentation. For instance, there is a method you can call on the Array class called in_groups_of, and you can use show-doc to get the documentation for that method.
	ex. show-doc Array#in_groups_of

Important Note: if you were in something like an Article class, you could use the all method to give you the array of Articles and call the show-doc for in_groups_of to see the documentation. The Railscast said you can see the documentation through the Article object or scope or something, need to play with it probably.
	ex. show-doc all.in_groups_of

show-source - will show the contents of a method. Lets you see the source code.
	ex. show-method Array#in_groups_of

edit-method – will open the file in the editor to the line where the method starts.

. - lets you run shell commands. For instance, if you just use ls inside of pry, it will give you a list of variables and methods, but if you run .ls you will get a directory listing.

_ - Last eval. Saves the return value of the last line evaluated (is this correct?), which can then be accessed through the underscore. Useful if you didn’t save the return value to a variable.

gist – lets you extract code to a specified Github url.

amend-line – allows you to amend lines you typed into Pry.
