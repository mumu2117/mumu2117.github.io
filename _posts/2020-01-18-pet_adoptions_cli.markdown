---
layout: post
title:      "Pet Adoptions CLI"
date:       2020-01-18 12:10:08 -0500
permalink:  pet_adoptions_cli
---


This blog is about my thought process, struggles, and, challenges while building my command line interface (CLI).

I fell ill and, it took away some time off my hands. I initially planned 2 weeks for completion. I had  week to finish and, was still down sick. I kind of thought I was going to fail. Till now I was able to finish my labs and lessons well in advance. 
I decided to give it my all and, muster all the strength I could to get it done.  I decided to do something I love which is animal welfare. I am a huge proponent of animal adoption and, one day would love to start a shelter of my own that would be no kill and, would provide shelter to homeless animals. Having decided on it. I decided to base my CLI App on my favorite charity.

I began by first setting up the local environment.  I debated about doing a local environment setup on Windows but, decided againist it.. I thought its now or never. Ruby was already on my Mac, so, I went on to setup the other packages.
Once that was done. I started thinking of what files are needed in my file schema that I installed by using "Bundle gem Pet-Adoptions."  

I started thinking of the classes to include in my App. And decided on the following schema in my lib/pet_adptions folder:

1. CLI.rb which would include my CLI classes. 
2. Scraper.rb which would include the scraper classes responsible for scraping my website.
3. Animal classes for creating each animal object.
4. A class that would combine the scraping and, new object creation functionality.



This is how I visualized the program to work:

* User starts the App.
* The app would welcome the user and, showcasse all the animals.  
* The app would ask the user what animal they would want to check out. The choice would be in numerical format. 1. Dog, 2.cat etc.
* After the user chooses the animal they would be shown all the available animals for adoption scraped from the website.
* They would then be asked to choose the particular animal. When they do they get additonal details on the animal from the website.
* The user is then given info on how to go to the charity website to adopt hte animal with the charity URL.
* The user is then given a choice to go back to the list of all animals(main menu), or the list of the selected animal, or exit the program.

Now that I had an idea I started building the executable in Bin first. Then started coding my App starting with the CLI. 

CLI:  I used a Constant called "BUDDIES," and, named my objects exactly, how I wanted them to show up. I used iteration each_with_index(1) to iterate over this constant.  I provided two placeholders in the itirate method: Number, and, buddy (which refers to the BUDDIES constant.) This allowed me to pass those two placeholders into a string based on the input of the user and, list the correct number and the choice of animal the user chose from the Pet constant. 


***Scraper Class:*** I used OO Ruby to build classes and then class methods (class methods start with self dot) to scrape the animal website to get the list of animal the user choose (for instance if it is a dog it would go to the dogs list page) and, then it would scrape date of animals from information obatined from those pages. The first scrape would only pull the Name, Age, Breed as listed on the page for that particular animal. I scraped the website using ruby gems Nokigiri to extract data from the website, and used Open Uri as well as CSS selectors to extract the Div, span, class selectors. It really made scraping fun and easy. The Scraper class takes in an argument of the species name, which is appended to the end of the Best Friends website url("buddies")

The animals on the main adoption page were stored in a main Div class called rg-animal, so I itirated though the css selector using the each iteration method. I used a hash called "bud+features" to store the values scraped form the website such as age, breed,url, name from the main page of each animal. I then pushed the has value into an array which I stored in a variable called buds, which I could then call to give a list of the animal url and the features of that particular species of animal. Just to give you a birds eye view of how my first method in the scraper class flows.
I built a second scraper method to scrape additioanl details from the individual animal name the user picks for adoption. This page has more details such as color, size, sex, description of that particular animal. 


***Adoptapet class***: I used OO ruby to list all the animals in the parent class, and incorporated all the methods to create objects, and add additional attributes in this class. Then I created each species as a Child class and, they inherited from the Parent class which is Adoptapet class. Since, they all shared the same attributes I included all the method in the parent class. Then using the DRY principle which I could have the child classes inherit their methods, and attributes from the parent class. This minimized my coding. Used metaprogramming to make sure that any change of attributes would be accounted for. 


***Buddycount Class***: I created another animal class that would then bring together the scraper classes and the object creation classes to churn out the animals. In essence this was like the creator of the objects and, the ingredients were provided by the scraper class methods that scraped data from the website as well as the main animal class methods "adoptapet" that helped create the individual animal object based on this data. 







