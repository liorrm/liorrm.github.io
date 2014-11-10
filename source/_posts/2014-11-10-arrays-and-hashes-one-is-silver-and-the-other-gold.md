---
layout: post
title: "Arrays &amp; Hashes: One is Silver and the Other Gold"
date: 2014-11-10 11:22:53 -0800
comments: true
categories: [dev]
---
Now almost a third of the way through Phase 0 of Dev Bootcamp, we've finally moved on from git, HTML, and CSS to the true heart and soul of programming: scripting -- the part that actually makes your web site do stuff rather than just display it. For the first blog topic, we'll discuss arrays and hashes, which are two ways of storing data. Arrays and hashes are each their own classes in the Ruby programming language, meaning they come with their own set of rules that govern how they can be used, and methods than can manipulate the data within them. First let's talk about arrays, since they're simpler, and understanding hashes is easier once you understand arrays.

An array is a series of elements grouped and stored together, separated by commas. They are encapsulated by a pair of brackets on both ends of the series of elements. The elements can be of various types, including strings, numbers, symbols, etc, such as the example below illustrates:

```ruby
example_array = ["string", :symbol, 5, ["this", "is", "crazy"]]
```
Yes, you actually can store an array inside of an array (an array within an array is called a nested array). In addition to the element itself, the array knows where the element "lives" (its position) inside of it, something called the *index*. The index begins at zero, so the first element of the array can be called like so:

```ruby
example_array[0] #=> "string"
```

How would you call the second element of the nested array?

```ruby
example_array[3][1] #=> "is"
```

Good. Now that we have an understanding of arrays, we can delve into the world of hashes. Hashes are similar to arrays in that they are also a means of storing a series of elements, but they don't just stop there. Hashes store relationships between its elements in what are called key-value pairs. Whereas an array could store a list of cities:

```ruby
city_array = [:New_York, :Los_Angeles, :Chicago, :Houston]
```

the hash could store them AND tell you their populations (or whatever corresponding piece of data), where the city names are the "keys" and the populations are the "values":

```ruby
city_hash = { New_York:    8300000,
              Los_Angeles: 3900000,
              Chicago:    2800000,
              Houston:    2200000  }
```

 You can access a key's corresponding value like so:

 ```ruby
 city_hash[New_York] #=> 8300000
 ```

 As you can see, hashes allow for relationships between values, compared to arrays which just list them in a series. Both are incredibly useful and are fundamental to just about any large-scale project.


