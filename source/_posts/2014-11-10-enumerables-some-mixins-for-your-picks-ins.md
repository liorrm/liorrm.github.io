---
layout: post
title: "Enumerables: Some Mixins for your Picks-ins"
date: 2014-10-08 18:05:09 -0800
comments: true
categories: [dev]
---
Now almost done with Week 4 of Phase 0, we are plumbing the depths of Ruby and its amazing abilities. For this blog post, I will introduce you to one of Ruby's built-in Enumerable methods. Enumerable is a "mixin" module in Ruby, meaning that its methods are borrowed from various other class methods. Therefore, you can apply Enumerable methods to various classes, namely arrays and hashes. The method I'll focus in on is the :map method, which can be used on both arrays and hashes. I am going to assume that you have some sense of what the :each method does --- basically, it iterates over an array, calling the given block (the code between braces or after a 'do' statement) once for each element in the array; it passes each array element as a parameter to the block. But it doesn't have the power to actually modify the element. You can use the array's elements to create new data, but not to change the elements themselves, as the following example demonstrates:

```ruby
numbers = [1, 2, 3]

def total(array)
  sum = 0
  array.each do |num|
    sum += num
  end
  sum
end

total(numbers) #=> 6

numbers = [1, 2, 3]
```

Here, :each is used to add up the elements of the array, and store them in a separate variable. If you were to return the array afterwards, it would be identical. Here's an analogy: the :each method "visits" each element and can get to know them well, but it can't change them. That's where map comes in. To demonstrate the :map method's differences, let's compare the following two snippets of code:

```ruby
##### using #each #####

numbers =  [1, 2, 3, 4, 5]

numbers.each do |num|
  num * 2
end

#=> [1, 2, 3, 4, 5]

##### using #map #####

array #=> [1, 2, 3, 4, 5]

array.map do |num|
  num * 2
end

#=> [2, 4, 6, 8, 10]

numbers #=> [1, 2, 3, 4, 5]
```

:each does nothing, while :map successfully executes the block and modifies each element of the array. But does it really change the array? Not exactly. It shows you a modified version of that array with the code block executed, but you can think of that as a temporary glimpse into what it would do it if actually did modify it. As you can see in the above example, if you call the array after calling the code block on it, it remains unchanged. For a true, permanent change, we need the "!" at the end, or we could save the modified array to a new variable. The exclamation point at the end of a method indicates that the method is what is called a "dangerous" or "destructive" method (or colloquially, a "bang" method) because it permanently changes the composition of the array, as the example below demonstrates:

```ruby
numbers = [1, 2, 3, 4, 5]

numbers.map! do |num|
  num * 2
end

#=> [2, 4, 6, 8, 10]

numbers #=> [2, 4, 6, 8, 10]
```

:map and :map! are very useful methods to make real changes to various data structures. For example, if you had an array of data containing both strings and numbers and wanted to convert all the numbers to strings, you could use :map or :map!, depending on whether you want to make a modified "copy" of the array for immediate use, or change it permanently.

Here is another example that uses the map method to convert array elements into strings:

```ruby
i_want_pets = ["I", "want", 3, "pets", "but", "only", "have", 2]

def my_array_sorting_method(source)
  source.map {|element| element.to_s}
end

#=> ["I", "want", "3", "pets", "but", "only", "have", "2"]
```

And there you have a little introduction to Ruby's Enumerable module! Be sure to check out the [Ruby Documentation ](http://at ruby-doc.org) for more information and to see other Enumerable methods.
