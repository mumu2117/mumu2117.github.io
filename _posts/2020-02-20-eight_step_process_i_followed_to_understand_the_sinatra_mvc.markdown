---
layout: post
title:      "Eight Step process I followed to understand the Sinatra MVC."
date:       2020-02-20 21:05:00 +0000
permalink:  eight_step_process_i_followed_to_understand_the_sinatra_mvc
---

I wrote down an 8 step process that I used to fix my Sinatra Bugs while building my App. I used a 8 step process to fix my errors. I wanted to share this with the cohort. I was determined to fix the errors and make my Travel Goals app work and, submitted my project by Saturday. This is the process i followed :  

1. User sends a HTTP request to the browser.  Sinatra Controller grabs the request and, matches it with a method action. 2. that action which is the code we set to talk to the models, reaches out to the Model class for data. 
3. Model through the associations we established through Active Record which is the ORM mapper, talks to the DB and, asks for that particular data 
4. DB responds with the data. 
5. Model after receiving the response from DB sends objects(data) back to the controller action item. 
6. The Controller action then talks to the view file and, asks it to render the objects or data. 
7. View then responds with beautiful HTML code and, embedded ruby incorporated into it. 
8. Controller sends back the HTML code in HTTP response to the browser. 
9. Viola! the user sees the beauty 
