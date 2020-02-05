---
layout: post
title:      "Data Structures"
date:       2020-02-05 16:40:22 +0000
permalink:  data_structures
---


#Data Structures

#There are four different variables. They are Local, Instance, Class and Global. I will cover the first three below.

#A local variable is only available to the method it exists in. An example of a local variable would be:


	variable = dog
	puts variable


An instance variable starts with a single “@“. An instance variable’s value is unique to an object and is available across all instance methods in the class(not class methods though). Below I want to show you how instance variable can be set inside a instace method. I am using two methods Setter method which sets the instance variable, and the second instance method is the get method which "gets" or displays the instance variable when called. You notice that the instance variable can be called outside of the first instance method. 

def name(name=)
@name= name
end

def name
  @name
	
	end.


A class variable starts with “@@“. Unlike instance variables, a class variable is available across all objects within the class.  Below I created a class called Dogs. We used a class variable to push all dog objects created into a class variable called @@Dogs as soon as they were instantiated, then we created a class method called self.all  (class methods start with a self) and, we called the array of class variable called Dogs to display all the dogs created in the class. 

class Dog

  @@dogs= []
	
  def initialize(name)
	
    @name= name
    @@dogs << self
		
  end
	
	
  def self.all
    @@dogs
  end
end


