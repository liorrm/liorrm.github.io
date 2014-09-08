---
layout: post
title: "Request-Response"
date: 2014-09-07 15:12:29 -0700
comments: true
categories: [dev]
---

Request-Response is the fundamental building block of the Internet and computer networking. The systems works likes so:

A personal computer, the *client*, is used to access a web page stored on a remote database. The database is linked to a computer that acts as the *server*, which can access the database and provide the requested information to the client. Using a web browser, the client requests the web page from the server, and the server responds to the client with the requested information by accessing the database. It's no coincidence that the words *client* and *server* are used for this system, as it's very analogous to a restaurant. The client, or customer, orders the food by telling the server, or waiter, what he/she wants ("Hi, I'll have a google burger please"). The waiter then goes to the kitchen, the database, gets the order, and serves it to the "client"/customer. Now it all makes sense why sometimes, when a server experiences higher-than-normal requests, it wont be able to respond to all of them, and will temporarily shut down. This is akin to how a restaurant will often make customers wait during peak hours, because they simple can't handle all those orders at once!

##  HTTP ##

The "language" used in this process is called the Hypertext Transper Protocol, and includes request "methods", the most oft used being GET, HEAD, POST, and DELETE.

* GET is, as you could guess, is the request for retrieving data.Going to google.com, for example, would use the GET http method.Because it does not modify anything on the server-side, it is considered a "safe" method.

* HEAD is the same as GET, except that the server only returns *metainformation*, that is, information about the entity rather than the entity itself. This is typically used in testing whether links are valid or have recently been modified. Because no modification occurs, it is also a safe method.


* POST is the request that the server accept a new piece of information enclosed in the request; a typical example of this is a blog or forum, where clients are adding posts that change the state of the server, or have other side effects (like transferring money or sending an email). Because something is being changed with the POST method, it is not considered a safe
>method.


* DELETE is the request that a given piece of information or resource be deleted by the server, like deleting an email. Again, because the state of the server is being changed, it is not considered a safe method.


During the early years of the Internet, the web was dominated by static websites that, when requested by the client, were generated and didn't change unless another request was made for the most up-to-date version. Today, however, there are a plethora of technologies that allow for dynamic web pages, where there is a constant flow of communication between the client and the server, allowing content to change from moment to moment. The main technology that made these dynamic web pages a reality is AJAX, which is behind almost all of the asynchronous, dynamic web applications that dominate today's Internet. AJAX allows for this *asynchronization*, where a request can be made in the back-end without having to wait for a response to make another request, thus not being synchronized. These asynchronous requests and responses can happen without having to reload the web page, which is how we see content changing on the website without the website's core structure changing.