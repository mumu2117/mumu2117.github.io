---
layout: post
title:      "Pet Adoptions CLI"
date:       2020-01-18 17:10:07 +0000
permalink:  pet_adoptions_cli
---


This blog is about my thought process, struggles, and, challenges while building my command line interface (CLI).

I fell ill and, it took away some time off my hands. I initially planned 2 weeks for completion. I had  week to finish and, was still down sick. I kind of thought I was going to fail. Till now I was able to finish my labs and lessons well in advance. 
I decided to give it my all and, muster all the strength I could to get it done. 


I began byfirst setting up the local environment. It wasn't as easy breezy as I thought. I decided to do it on my Mac which I don't usually use, which also made it a challege since, I had to simultaneously getused to the Mac. While I was used to Linux terminal thanks to my AWS cloud certifications coursework and using EC2 instances which were mostly setup with LInux, but, I still had to get used to it. I debated on doin ga windows setup, but, decided against it.. I thought its now or never. Ruby was already on my Mac, so, I went on to setup the others:During the installation we have to install Ruby if it is not already on our computer.
1. Gems: Learn, nokogirietc
2. setup bundle
3. homebrew
4. postgresql
5. git
6. ssh key to connect  to github (I messed up my key but, then corrected it eventually)
7. node
8. . a bunch of other stuff

After I tested to make sure they were installed well. When I opened VSCode editor it looked strange at first. So, I had to get used to it first. It was so convenient and, easy to do just the code and, hit learn, and learn submit on the learn IDE. This was out of our current comfort zone. But, I think one of the things we as programmers need to constantly do is get out of our comfort zone, which is something I have done all through my life. I took risks and, got our of comfort zones several times over. Sure, it is stressful but, at the end it is worth it.

Ok back to VSCode. As I was getting familiar with it, I decided to download the file Schema using Bundler. So, typed "Bundle Gem Pet_Adoptions," and Viola there was my file schema. I let out a "woohoo," beat my chest like King Kong. Once I was done with my short feeling of excitement I realized there was a lot to be done. One thing I liked about VSCode was the fact that I do not have to type my Git commands. Well, I am lazy what can I say. lol! Normally i would have practiced it, but, we are running out of time here. It is called Source control Icon and, when you click on it, you can stage, commit, push, pull (did not see clone)etc to github. Still in the process of learning. It took awhile to get it to work though because I messed up the SSH key. Our Cohort lead Howard Devenish helped me figure out how to rectify that problem.

Whoa! I was able to commit a blank schema of my ruby gem files to Git for the first time. I had 5 days left and the clock was ticking.  I decided to code first. Started with my Bin executable of course. I typed the usual shebang at the top:
"#!/usr/bin/env ruby" followed by the line that grabs thefiles in my lib folder where all my actual code sits.  Folowed by a call to the CLI method and, class and, starts the app  (this is what would show up on the front end when you guys run my fabulous CLI gem.

Ok I promise to shutup and, get back to explaining the technical stuff. 

Scraping time Baby: Now the challenge was to decide what to do. I decided on animal adoptions, since, that was always my passion. I scraped a couple of websites and, decided on one. After deciding now, I need to scrape it. I used nokogiri before and, decided to do the same.  On the page I right clicked and selected "inspect." which opened the developer tools for me. This is where you can view the source code. I went to the adoption page, then clicked on teh little tiny mouse like button on the top left corner in the developer pane. It helps us link the code to the images, text on the page and, vice versa. For instance, I could hover over the code and, on the page it will highlight the text or image or headline the code relates too. Wowza! Beautiful. Ok I will shut up again. This requried some precision and, concentration, but, I could grab the span/dive classes that I was going to pinpoint to in my code using this technique.


Coding time: Her comes the future coding chick. lol! Ok I am goign to get serious now. I debated using the Config folder which I usually saw in my Learn IDE versus putting my environment file in the Lib folder. I decided to go with the Big Boss Avi's example in the video and, made an environment file in the Lib folder where all my code goes as I previously explained. This  is where the real magic happens ladies and, gentlemen. We were supposed to show our expertise on OO ruby.  Which is what I did. I loved the inheritance method in OO Ruby, saw an opportunity to use it to list all the animals, so, I created an class I called "buddies," and, inputed all my methods such as Getters and setters for all the attributes, Used the Attr accessor macro, and, luckily for me all my attributes could be coded using this macro. Then I of course used my other favorite which is to use mass assignment to  metaprogram  a ruby class. which is  a way to abstract away our User class' dependency on specific attributes. If only there were a way for us to tell our User to get ready to accept some unspecified number and type of attributes.This is how it works: We define our initialize method to take in some unspecified attributes object. Then, we iterate over each key/value pair in the attributes hash. The name of the key becomes the name of a setter method and the value associated with the key is the name of the value you want to pass to that method. The ruby .send method then calls the method name that is the key’s name, with an argument of the value.  Then I defined some methods in the same class such as creating new objects(buddies you want to adopt,) then giving them attributes etc.

Then I created the specific animal classes: dogs, cats etc. and used the inheritance concept in ruby so, I could refer to the main class "buddies" that I created where they would inherit all th attributes, and methods etc. 

CLI interface: Now I need to create another file in the Lib directory and, then created the CLI class and, methods in there.  This the the Class and method I was calling from my bin folder.  This is where you will  see that I have my welcome messages, messages guiding the users how to interact with the app so, they could pull data they wanted to see. I used a numerical scheme for this. So, that the user doesn't have to work too hard. The Cli methods.  refers to the scraper file I created with its own methods to scrape data off the website, and displays that data.  I created some methods which refers to other methods in both scraper and, other files. 

Scraper file: This is where I code everything that makes the data grabbling magic happen. The website does have licensing requirements so, I cannot technically publish this gem until I get permission from them. I am planning to contact them for permission.

Getting the App working: After everything was done. Close sesame time. I ran the program and, it gave me a bunch of errors. They wer easy to fix. I was very good (come on who else is going to blow my own horn,) at reading file errors by now. So, I could run the file and fix teh errors myself. I need a little guidance in the beginning from the Boss man Enoch who was our lead instructor and, kaboom, I went off to fix little errors such as syntax, speling errors etc by myself. Since, I was new to VSCode I also needed some help fixing the file structure errors. stuff like environment shoudl be in lib folder but, was showing up under another folder. I used the mv command to move it back under the lib. Now, that everything was pointing to the right direction I was ready to run my app and, Viola! it worked. 

End of story. Hope you guys enjoyed my blog. 

