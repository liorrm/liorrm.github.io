---
layout: post
title: "Ruby v. JS: The Big Players of Web Development"
date: 2014-10-31 14:20:36 -0800
comments: true
categories: [dev]
---

Delving into the completely different world of JavaScript after having spent over a month getting cozy with Ruby was a bit of a rude awakening. Suddenly my comfort and fluency was out the window -- I felt like I was starting from scratch! What had become second nature in Ruby I now had to research in JavaScript - nooooo! But after spending some hours reading and studying, I feel like I'm finally getting my bearings.

JavaScript and Ruby are both powerful object-oriented languages, but they are designed for two completely different purposes. Ruby is a server-side back-end language whose processes don't really have a visual component. Ruby processes and manipulates data and makes calls to the server's database. JavaScript, on the other hand, although it can be used as a server-side language (Google node.js!), is primarily a client-side language that runs in the web browser and is responsible for making websites dynamic and interactive. That's why, despite being a very capable scripting language, JavaScript is typically considered to be a front-end language.

There are many other differences between these two languages as well, the most obvious of which is syntax. Ruby's defining characteristic is the use of the keyword end. You must use end to signal the end of a method definition, class definition, loop, or block. JavaScript, on the other hand, is distinguished by the presence of curly braces and semicolons. Let's compare the following two methods (one written in Ruby, the other in JavaScript) that do the same thing; see if you can figure out which is which!

1.
```javascript
var sum = function(array) {
  var total = 0;
  for (var i = 0; i < array.length; i++) {
    total += array[i];
  }
  return total
}

console.log(sum([1, 2, 3, 4, 5])) // => 15
```

2.
```ruby
def sum(array)
  total = 0
  array.each do |number|
    total += number
  end
  return total
end

sum([1, 2, 3, 4, 5]) #=> 15
```

Well? It's pretty obvious, isn't it? You can definitely see the similarities and figure out that each function is doing the same thing, but there are several key differences. For one, the JavaScript loop is completely different-looking from Ruby's `#each` method. JavaScript also requires (in most cases, though not all) a semicolon at the end of each executable statement, whereas Ruby does not. Ruby determines the extent of methods, loops, and blocks with the end keyword, while JavaScript relies on the meat of a method or loop to be wrapped in curly braces. JavaScript also requires you to use the keyword `var` at the beginning of each variable assignment.

If I had to pick a favorite, I'd choose Ruby hands-down... I'm biased, of course, by my lack of experience as a developer and my familiarity with Ruby. Both languages are incredibly powerful and integral the world of software development, and I'm sure my appreciation for JavaScript will increase as I continue to work with it and see its true potential.

