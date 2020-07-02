---
layout: post
title:      "A Lesson In Preparation"
date:       2020-07-02 19:45:51 +0000
permalink:  a_lesson_in_preparation
---


> "It is not enough to be busy; so are the ants. The question is: What are we busy about?" -Henry David Thoreau

For the second project in the Flatiron curriculum, I used Sinatra to build a web app that lets users build and track bucket lists. To me, when I first started playing with the idea it seemed relatively simple. Honestly, it still does, but my process for getting through the code was anything but simple. The number one lesson I learned was that I undervalued planning things out ahead of time, particularly my models and relationships.

It’s easy to take for granted everything you’re given while going through the lessons and labs provided by Flatiron. The fully fleshed out tests, the pre-built codebase, the tips and hints in the lessons themselves, all of these things are crutches. That’s not to say Flatiron is doing anything wrong, the crutches are needed to speed up the process of learning, and they’re taken away at an appropriate time. Still, there was a sense of unease at times because I realized that there were little holes in my knowledge. There is so much material to each module that it’s difficult to know what you don’t know just by re-reading old notes or lessons. Digging in and building the code line by line, file by file, really helped me to solidify my knowledge.  

### Planning
I think the biggest lesson I learned was that a little extra planning early on is an excellent use of time. There is a great guide for what to build and when in the Sinatra Project Planning Resources. Unfortunately, for reasons I won't get into I did not see this until I was almost finished with my project.

According to the guide, the order should be something like: migrations and model classes => associations and validations => seed data => controllers and views. That structure makes a lot of sense and I wish I’d followed it, but hey, it’s a learning experience. I was kind of all over the board, jumping between models, views, controllers, migrations, and validations. Solving problems in the wrong order can create more problems, apparently. 

This all comes back to not planning ahead of time. Because I didn’t draw out my models, attributes, and relationships beforehand, I ended up constantly messing with my migrations, rolling them back, editing and deleting them, making revisions. Each time having to go back and adjust the MVC architecture and code to fit the new schema. Next time I am definitely going to use some tools for mapping out my models and relationships. https://lucidchart.com is just one of the sites that provide a free account and can help to visualize the desired structure.

### Git
Planning is great, and as stated, something I'll work more on in the future. That being said, I know that sometimes with code you just have to try some things out, whether just to see if they work or because doing so helps spur the creative process. I started really seeing the benefit of version control for this very purpose, but was unfamiliar with many common Git commands and processes. Sure I can fork, clone, and initiate pull requests for labs, but beyond that my knowledge was fuzzy. 

I did a lot of research and learned some great information, but just like most things code-related, I realized that there is a ton of depth to version control and that I would probably have to learn by doing. To help ease myself into the learning process, I downloaded a tool called GitKraken, which really helped simplify the processes that have been so confusing to me. It was nice to be able to easily create a new branch so that I could experiment without worrying about creating unintended bugs in code I already knew worked. I think going forward, with some extra planning and a better grasp on version control, my approach will feel more...controlled.
