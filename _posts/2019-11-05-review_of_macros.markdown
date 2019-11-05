---
layout: post
title:      "Review of Macros"
date:       2019-11-05 05:11:03 +0000
permalink:  review_of_macros
---


Metaprogramming is an extremely useful tool once code starts to become repetitious with more and more complicated requirements and as things become more complex. It is the practice of writing code that writes code for us. It is like hidden, behind the scenes code that makes life easier for coders. Examples of metaprogramming are found in macros, such as ActiveRecord object relationships/associations or mass assignment. 

One of these relationships, a has_many relationship, comes from ActiveRecord. It's common knowledge that ActiveRecord already takes care of repititious work for a coder. The macros that come with this ORM framework are most notably the associations between models. A few of these associations are has_many, belongs_to, and has_many_through, just to name a few. 

The has_many association is likely one of most popular associations that is implemented. It's common for real world circumstances, such as if all these songs belong to an artist, that means that the artist has many songs. The associations work inversely, but connected to one another. 

When that song object is created, that instance of a Song must be assigned to an Artist (because someone had to write and produce it). This macro also takes care of creating the setter and getter methods, which are used to access instance variables of a class, outside the class using the object of the class. 

The use of macros and metaprogramming are very convenient, because it allows for less repititious, cleaner code. It also helps avoid careless errors in the early stages of a project. I had a really difficult time trying to understand what all goes into these macros, but it is of utmost importance for an early coder to learn. Understanding the fundamentals is far more important than being a fast coder. 
