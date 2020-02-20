---
layout: post
title:      "Sinatra Portfolio Project using MVC"
date:       2020-02-14 21:52:59 -0500
permalink:  sinatra_portfolio_project_using_mvc
---


I was excited about building my first WebApp using ActiveRecord for my associations and Sinatra for my routes, Rack for my server, and, html and, Css for page structure, and styling. For this project we used a concept called MVC structure for Web Applications.  Keeping our code organized is crucial when developing complex applications. This concept is called separation of concerns and single responsibility. Each file in our application will have a different responsibility and we'll keep these responsibilities split up into reasonable chunks.  With MVC each folder ha a different responsibitlity. 

I decided to build a web app where folks can keep track of their travel goals. I used categories, travel experiences, and, countries as the three objects I am going to build my app around.

I drew out my tables and associations. Users have {Name, Email, Password}. A user has_many travel experiences and has_many categories through experiences. There is an experience class, which will belong_to a user and to a country. An experience also has_many categories. So my experience table needs to have {description, user id, country id}.
My country class has {name}, and a country has_many experiences.
category class also has {name}, and has_many experiences and many users through experiences
Since experiences can have many categories, and categories can have many experiences. I created a join table between catergories and experiences. I then created migrations to each table. Rake and, pry console were my best buddies in that process. Then i used the "M" in MVC to create my model classes. Each model and class inherited from `ActiveRecord::Base` and used belongs_to, has_many or has_many, through depending on the logic from the table creations earlier. 


An crucial aspect of my app is the ability for users to create an account to maintain their goals, log in and out of their account, and view other users Travel Goals to get inspiration (but not make changes). 

I first started with sessions. I aded enable :sessions to my ApplicationController, and this in turn enabled me to maintain a user's ID in the session hash. This enables verification whether the user is logged in or out.  Blocks a user from accessing other users pages, or editing/deleting their info It enables a user to create travel goals, and, edit their own goals if they are logged in. If they are not logged in, it redirects them to the login page. 

I created helper methods in the ApplicationController that the Experiences, Countries, Users and Categories controllers could reference.
I created helpermethods to include verification in my app. Such as if the user is logged in, and, if their user id, matches the user id they typed in.
1. #is_logged_in? checks to see if the session[:user_id] has been set and returns true if it has, indicating that a user is logged in
2. #current_user finds the User object based on the ID that has been set in session[:user_id] and is used to compare if the user that is currently logged in matched with an experience's user.

 I  utilized Sinatra to perform a universal route check to ensure that the user accessing the route is logged in. Now anytime an /experiences/ route was accessed, my app would first execute the code in the filter block. If the user was not logged in, it would redirect the user to the login page. If the user was logged in, it would continue on with the code in the route that they requested.

By repeating this filter in each of the controllers, I secured each page and ensured that they could not be accessed or changed by users unless they are logged in.

```
class ExperiencesController < ApplicationController
  before '/experiences/*' do
    if !is_logged_in?
      flash[:login] = "You need to be logged in to performance that action"
      redirect to '/login'
    end
  end
```
	
	
	
	
I used the name has_secure_password in my User model. I used bcrypt gem to securely store, and, verify a user's password. Bcrypt authenticates the users password. If the password did not match the one stored in the database, the user is returned to the login screen and asked to try again.If the password does match, the session's [:user_id] is set and the user is brought to their Travel Goals page. 

This is how the two files work. These files are under the "View" folder which is the V of the MVC model, under a file in View. Once logged in a user can add a New Experience (which is the create file create),edit an Experience (/edit), or Add a New Experience from Another User  (which is why we have the create_from_user file under).  

Finally, I did my styling using, CSS and, had a lot of fun with it. I used layout.erb to incorporate the DRY principle of "yield." 
In layout.erb, we need to add a yield wherever we want the other page content to be loaded in this case "index.erb." 

I had tons of fun doing this project and am excited to see what we have waiting on our rails project.

