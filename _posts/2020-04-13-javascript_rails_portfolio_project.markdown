---
layout: post
title:      "Javascript/Rails Portfolio Project"
date:       2020-04-13 22:00:39 +0000
permalink:  javascript_rails_portfolio_project
---



Having completed my Rails Portfolio Project which was pretty elaborate and, intensive, I was expecting another marathon. To our surprise The JS project was pretty easy.  As far as the backend goes we were allowed this time to use the infamous "Rails g scaffold." We were not allowed to use the scaffold generator previously.  We were still however allowed to use the resource generator which basically creates the controllers, routes, models, and, migrations and skips views. Which actually made sense to me since, I used bootstrap to style and, it was way more awesome than coffeescript which the scaffold  generator gives with the views. 

With the JS project it  was different since, we had to style  with CSS. So for our front end it was HTML, CSS, and Javascript(I will usethe shortuct JS throughout this blog.) Having gotten teh basics of OO Ruby moving to JS made it quite easy. There was a  ton of repetitive stuff with the variables as well as the OO JS concepts. Fetch was very intersting. Basically it was an easy breezy project.
 
 
 Initial thought was to do a notes app but, after my cohort colleague picked the same app I decided to do something girly this time. I loved cooking since I was a kid, and wanted to build a recipe app. Something everyone could post to, and refer to. Kinda like a universal recipe book.  After laying it out on paper and, chalking out everything I saw that it was a great fit. It does not require user login or authentiation sinc, it is an unviersal recipes holder.  So, I decided to include only the Create and, Read parts of the CRUD action. 
 
 The back-end of the app was pretty straightforward. I used the 'rails new' command with the --api flag to get the basic files going. Then I used the Rails g scaffold to scaffold out everything. And since, rails in api mode has no views this worked perfectly.
 
Overall the JS wasn't as bad as I thought it would be.  I hope moving forward react would be as easy as this. I started building out my front-end by adding an index.html page, an index.js page, and a styles folder with a CSS file. I initially wrote all of my Javascript in the one file and re-organized it into a Recipe class and Ingredient class, however I wasn't very happy with this level of organization. Even though the recipe class had methods that somewhat had to do with recipes, some methods made calls to the API, while others rendered content to the page. I eventually decided to re-organize my code into more classes and files 
 
 
