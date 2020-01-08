---
layout: post
title:      "Project #3: League of Champions - Rails"
date:       2020-01-08 02:01:34 -0500
permalink:  project_3_league_of_champions_-_rails
---


For the League of Champions application, I built it with HTML, CSS, and Ruby on Rails. For a while, I thought about what sort of project I'd want to make. It's always easier to create something that you're passionate about. With that in mind, I decided to go with a fantasy character creation application. Growing up, I played lots of RPG video games such as Final Fantasy, Everquest 2, and Diablo, among many others, so I've always had a penchant for fantasy games and watching movies like The Lord of the Rings. So transitioning those ideas and things I enjoy into something I can create, makes for a much easier process. 

For the most part I knew what I wanted to do and how to do it. But I did struggle with some Rails concepts, such as using the proper associations and understanding the join table, and setting up my nested form. I had a difficult time grasping the many to many relationship requirement of the project, and how to properly set up the associations between the Champion, Weapon, and the Inventory Items, like with which belonging to which and which has many of what. After a great deal of looking over my code and Googling, I discovered that my errors were coming from adding an unnecessary 's' to the models the Inventory was belonging to, making those models plural instead of singular. 

Another issue I had was understanding the join table and why it's necessary. The join table of Inventory Items allows for easy and smooth model object creations to have associations with one another. When a has_many through relationship exists, like a Champion has_many Weapons through Inventory Items, the champion_id and weapon_id of each object that is created together, is listed in that join table database, displaying a clear connection and association between the two models, which was made through the Inventory. 

Setting up my nested form took a long time. I had to get help on this because I was stuck on it for so long. I had to try multiple different options of how to set up my form and how to correctly structure my strong params on my Champion controller. I had to inspect the page to view the actual HTML to see that I had the wrong nested params in my strong params code. 

This Rails project presented many challenges, but thanks to collaborating with other classmates and my instructor, I was able to figure out all the kinks and errors to make a functional application. Lots of research and talking things out were necessary for my success. The satisfaction from creating a project is really great, and I'm looking forward to conquering more challenges and learning how to be a better engineer. 
