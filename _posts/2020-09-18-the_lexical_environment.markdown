---
layout: post
title:      "The Lexical Environment"
date:       2020-09-18 23:48:44 +0000
permalink:  the_lexical_environment
---


One of the most difficult things for me when switching from coding in Ruby/Rails to Javascript was handling variables and understanding the scope chain. Everything seems more scattershot and temporary in Javascript. It might just be the inherent difficulty in trying to learn a new language or paradigm; I can certainly see that it happens in Ruby too, but it threw me for a loop in JS. 

Variables can be declared in one of three ways in JS – using the keywords var, let, and const. When a variable is declared outside of a block, its scope is global, and it can be accessed and used anywhere. If a variable is declared inside of a block - between these guys {…} - the declared value is lexically scoped. It is only accessible inside those brackets. This is also true for variables declared inside conditionals and loops, the benefits of which are relatively obvious. 

In JS, functions and blocks have an internal object called the Lexical Environment, which I’ll refer to as LE. The LE’s purpose is to keep track of local variables in the inside the block or function, and to keep a reference to the code outside of the block or function. The way the LE accomplishes this is surprisingly simple. As stated, the LE is an object, and it stores the variables and other information as object properties. So, when you are declaring a variable, you are really just adding a property to the LE object. The same goes for editing and deleting variables. 

When a function is run, a new LE is created to store the local variables and parameters. I mentioned that the LE is really split into two parts, internal and external. When encountering a variable, the internal LE will be searched for a value, but if it’s not found there then the external LE will be searched to see if a value exists in an outer scope. The scope chain will be searched one layer at a time, until finally the global scope is reached, and if there is no value there an error will be thrown. 

Closures are functions that can access outer variables. Technically, in JS every function is a closure, which means they all have this ability. That’s why any function can use variables declared in the global scope. A hidden [[Environment]] property is created when a function declared, and using that property, the function always keeps a reference to where it was declared. This is what allows the ability to use variables higher up in the scope chain. I've heard that it's common for junior developers to be asked at least one question about closures in interviews, and knowing about the Lexical Environment and the key role it plays in Javascript in particular is sure to make those questions easier to answer. 
