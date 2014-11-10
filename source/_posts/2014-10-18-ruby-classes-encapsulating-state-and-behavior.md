---
layout: post
title: "Ruby Classes: Encapsulating State and Behavior"
date: 2014-10-18 12:55:20 -0800
comments: true
categories: [dev]
---
In Ruby, a class is an encapsulation of state and behavior. As we know, Ruby is an object-oriented programming language, so (almost) everything in Ruby is an object. Furthermore, all objects belong to a class, which you can loosely think of as a "species" of objects. Each class has its own set of characteristics. For example, according to the Ruby docs, the Array class is defined as "ordered, integer-indexed collections of any object." The class comes with methods that can be called upon an instance, or example, of that class. Ruby allows users to create classes and to modify existing ones. To better demonstrate the concept of classes, I'll create a class called Person:

```ruby
class Person
  attr_reader :sex, :age, :height, :town, :religion, :occupation

  def initialize(name, sex, age, height, town, religion, occupation)
    @name = name
    @sex = sex
    @age = age
    @height = height
    @town = town
    @religion = religion
    @occupation = occupation
  end

  def sex_change
    if @sex == "male"
      @sex = "female"
    elsif @sex == "female"
      @sex = "male"
    end
  end

  def get_old
    @age += 1
  end

  def grow(new_height)
    @height = new_height
  end

  def move(new_town)
    @town = new_town
  end

  def convert(new_religion)
    @religion = new_religion
  end

  def change_career(new_job)
    @occupation = new_job
  end
end
```

To begin, you need to initialize a new instance of that class. Basically, you need to create an individual person from the theoretical class Person. As you can see in the initialize function, I have created a few characteristics each person should have: sex, age, height, town, religion, and occupation. Of course there are many others I could include, but these were the ones that immediately came to mind. When you initialize a new instance of person, you must pass in the above seven arguments; so for example, you would type in:

```ruby
Liorr = Person.new("Liorr", "male", 20, "6'1", "San Francisco", "Agnostic", "Programmer")
```

Now that we've initialized it, Liorr is an instance of the class Person. In the Person class, I have created several attr_readers (attribute readers), which allow the user to access information about Liorr. To see this information, simply type Liorr.sex, Liorr.age, Liorr.height, etc. into the command line, and the values with be returned. I specifically made all these attr_readers rather than attr_accessors because I want to limit the user to changing this information by using only the instance methods I created. As you can see, I had a some fun creating the method names. You can call `Liorr.sex_change` to change my sex to female, `Liorr.get_old` to add one year to my age, `Liorr.grow(new_height)` to change my height to a new input height, `Liorr.move(new_town)` to change my town to a new input town, `Liorr.convert(new_religion)` to change my religion to a new input religion, and `Liorr.change_career(new_job)` to change my occupation to a new input occupation.

Classes are defined by their state and behavior. All of these characteristics -- age, sex, height, religion, etc. -- give the class Person its state, stored in instance variables, while the instance methods -- #grow, #move, #convert, etc. -- give its behavior. I used the Person class as an example because it is easy to demonstrate state and behavior with something so familiar and tangible - people do have all these states and behaviors in the real world! Now all you have to do is think of each class as a different species of object, each endowed with a set of character traits. Arrays and hashes, given the overlap in their states and behaviors, are two closely related classes. To draw another comparison to the real world, you could consider arrays and hashes as you would consider humans and chimpanzees -- very closely related, but ultimately a different species.
