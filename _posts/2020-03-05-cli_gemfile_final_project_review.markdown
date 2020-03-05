---
layout: post
title:      "CLI Gemfile Final Project Review"
date:       2020-03-05 21:46:33 +0000
permalink:  cli_gemfile_final_project_review
---


I can't say enough about how valuable the experience of creating my first CLI project was. At first, I was really lost with all of the steps needed before going into the coding aspect. All I did up until now was learn how to code, specifically procedural Ruby and Object Oriented programming. I was always wondering about the functionality of the other files that weren't ruby files like Gemfile, rspec, gemspec, and how they work together to create something.

What helped me tremendously to understand the project was looking at the example they gave with the World's Best Restaurants CLI project. What derailed me in the beginning of the project was understanding the communication between files.   Analyzing all of the files of the World's Best Restaurant app led to me understand all of it. I was also able to figure out how to scrape websites, create new objects with them, and much more.

I was able to pick up a lot of material that I did not understand before, like the "has many" and "belongs to" relationship when working on this project. This lead me to understand that no matter how tough or initmidiating something is, if you are persistent enough, you will eventually push through. 

With some testing, I found out that it takes a considerable amount of time to create new objects. They aren't created instantly. My first attempt to create new objects for each fighter was to pass 174 fighters to the new_fighter method that creates new objects. It would take more than 20 minutes to create 174 new objects, so I decided to just create new objects based on what the user picks in my program. 

My project was about asking the user which UFC ranking they wanted to look at. If they would pick Heavyweight, then a countdown will start from 15 to 0. These days, people don't want to wait for things to load without seeing anything on the screen; they will probably think that the program isn't working. So I came up with a loading countdown for the user to look at while they are waiting for a specific division of fighters to load. For every number that goes down, a new object (fighter) from that division is created. The added features after that were asking the user if they wanted info on a fighter from a list they have previously seen, or play a game where the user has to guess the nickname of a fighter that is selected at random.

The main functionalities of my program were the ruby files of Scraper, Roster_Info, and CLI. Scraper was responsible for scraping the urls and passing them into the Roster_Info file to create new objects from them. The CLI ruby file was responsible for displaying the Rankings and collecting the new fighters from Roster_Info. 

Working on this project has been an invaluable experience for me. This has been my first CLI gemfile project, and one that I will never forget.
