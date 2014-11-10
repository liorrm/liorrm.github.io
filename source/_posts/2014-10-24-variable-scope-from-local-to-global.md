---
layout: post
title: "Variable Scope: From Local to Global"
date: 2014-10-24 15:35:42 -0800
comments: true
categories: [dev]
---
Ruby provides programmers with a range of variable types, all defined by their scope -- where they can be accessed. The variables, in order of increasing scope, are local variables, instance variables, class variables, constants, and global variables. Let's dive in to see the accessibility of each of the variable types.

First, let's start with local variables. As their name suggests, local variables have a local scope, limited to the method or block in which they are defined. They must start with a lower-case letter or underscore. Consider the following example:

```ruby
def local_method
  local_variable = "I'm a local variable"
  5.times do
    puts local_variable
  end
end

local_method #=>
              "I'm a local variable"
              "I'm a local variable"
              "I'm a local variable"
              "I'm a local variable"

local_variable => # NameError: undefined local variable or method `local_variable'
```

In this example, the variable `local_variable` is defined within the method. It can be accessed by the method itself, as we see it successfully executes the code block with the variable; but if we try to access it from outside the method, we get an error message that the variable is undefined. It's undefined because, as a local variable, its scope is limited to within the method itself. What if we were to define a local variable within block within a method?

```ruby
def local_method
  array = [1, 2, 3, 4, 5]
  array.each do |num|
    very_local_variable = "I'm a VERY local variable"
    puts "#{num}. #{very_local_variable}"
  end
  very_local_variable
end

local_method #=>
#                 1. I'm a VERY local variable
#                 2. I'm a VERY local variable
#                 3. I'm a VERY local variable
#                 4. I'm a VERY local variable
#                 5. I'm a VERY local variable
# NameError: undefined local variable or method `very_local_variable'
```

What just happened? In this example, `very_local_variable` is defined within a block that is within a method. When called, the method executed the block successfully, but then when `very_local_variable` was called outside of the block in which it was defined, ruby told us it was undefined! This example shows you just how limited in scope local variables are: if defined within a block within a method, the method won't even have access to it! Now let's move on to instance variables.

Instance variables are variables limited to one particular instance of a class. They must begin with a single "@" character. To illustrate the scope of instance variables, consider the following example:

```ruby
class Person
  attr_reader :first_name, :hair_color

  def initialize(first_name, hair_color)
    @first_name = first_name
    @hair_color = hair_color
  end
end

tom = Person.new("Tom", "brown")

tom.first_name #=> "Tom"
tom.hair_color #=> "brown"

muhammad = Person.new("Muhammad", "black")

muhammad.first_name #=> "Muhammad"
muhammad.hair_color #=> "black"
```

When we instantiate the Person class, we must give that instance a name and hair color. In the initialize method, these two parameters are turned into instance variables which can then be accessed by other methods in the class, but only on that single instance. For example, if we call `tom.first_name`, you can see that the program returns the input first name; same with the hair color. If we call these two methods on `muhammad` we see that we get different results. That is precisely because `@first_name` and `@hair_color` are instance variables, only to be used on a single instance of the class. In this case, tom and `muhammad` are two separate instances of the class Person. But Tom and Muhammad are both people, after all! What if we want them to share some characteristics? For that, we'll need class variables.

Class variables are those available to every instance of that class. What is one trait that all people have in common? Consider a similar example:

```ruby
class Person
  attr_reader :first_name, :hair_color

  def initialize(first_name, hair_color)
    @first_name = first_name
    @hair_color = hair_color
    @@species = "homo sapiens"
  end

  def species
    @@species
  end

end

tom = Person.new("Tom", "brown")

tom.first_name #=> "Tom"
tom.hair_color #=> "brown"
tom.species #=> "homo sapiens"

muhammad = Person.new("Muhammad", "black")

muhammad.first_name #=> "Muhammad"
muhammad.hair_color #=> "black"
muhammad.species #=> "homo sapiens"
```
As you can see, the `@@species` variable is not only available to Tom, but also to Muhammad, and every other instance of `Person`!

Now let's move on to constants and global variables. These two are similar in scope, but let's start with constants. Constants must be all-caps and, traditionally, are not to be changed. Technically, Ruby does allow the user to change them, but that runs counter to their whole point of being constant, unchanging variables. Like local variables, their scope is slightly fluid. If they are defined within a class, they are available anywhere in the context of that class. If they are defined outside a class, they have global scope, which means they are accessible from anywhere. To demonstrate these concepts, let's return again to our first example:

```ruby
def local_method
  local_variable = "I'm a local variable"
  5.times do
    puts local_variable
  end
end

local_method #=>
              # "I'm a local variable"
              # "I'm a local variable"
              # "I'm a local variable"
              # "I'm a local variable"

local_variable => # NameError: undefined local variable or method `local_variable'
```
What if we turned `local_variable` into a CONSTANT? We aren't allowed to define CONSTANTS within methods, because technically every time we run the method we'd be re-assigning the constant (even though to the same string value, it would still have a different object ID every time, which isn't allowed), so let's define it outside the method.

```ruby
CONSTANT_VARIABLE = "I am a CONSTANT variable"

def local_method
  5.times do
    puts CONSTANT_VARIABLE
  end
end

local_method #=>
              # "I'm a CONSTANT variable"
              # "I'm a CONSTANT variable"
              # "I'm a CONSTANT variable"
              # "I'm a CONSTANT variable"
              # "I'm a CONSTANT variable"
```

Look! the method has access to the constant even though it's defined outside of the method! The same goes for global variables, except they actually can be defined within methods:

```ruby
def local_method
  array = [1, 2, 3, 4, 5]
  array.each do |num|
    $global_variable = "I'm a global variable!"
    puts "#{num}. #{$global_variable}"
  end
  $global_variable
end

local_method #=>
                # 1. I'm a global variable!
                # 2. I'm a global variable!
                # 3. I'm a global variable!
                # 4. I'm a global variable!
                # 5. I'm a global variable!
                # "I'm a global variable!"


$global_variable #=> "I'm a global variable!"
```

In this example, `$global_variable` is accessible in the block in which it's defined, in the method itself (this is where a local variable would start giving us problems), and outside the block and method entirely!

I hope you found this little explanation useful; I'm off to learn more so I can write more next time! Thanks for reading! :)
