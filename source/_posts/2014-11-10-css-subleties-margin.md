---
layout: post
title: "CSS Subleties: Margin, Padding, and Border"
date: 2014-09-28 11:10:21 -0800
comments: true
categories: [dev]
---
After having immersed myself in the world of HTML and CSS through creating a fully functional website in a mere 36 hours, I came out of it with a great deal of knowledge (although admittedly an equally great deal of questions) about front-end web development and design. Today I will do my best to explain one such piece of knowledge of which I feel I have a pretty clear understanding: the difference between margins, padding, and borders. To understand these topics at all, I need to first explain the fundamental structure of almost all websites. When you load a website, you immediately notice that its content is organized in a certain way. You may have a header bar, one or several content areas, a navigation bar, a footer, etc. There is always a lot of thought (or there at least should be!) that goes into this design. When writing the code for the website, what allows the programmer to tell which material to go where? Well, odds are, the tool s/he used was the div. A div, which derives from the word "divide" is a part of the web page that you section off. Making divs is really easy in the HTML file (the content and framework part of the site), but the challenging part is bringing them to "life" using CSS (cascading style sheets). When you create a div in the HTML, it exists, but it has no idea where to go on the web page, so you give it instructions by using CSS properties like so:

```css
#div {
  height: 50%;
  width: 40%;
  float: right;
  position: absolute;
  background-color: blue;
  border-style: solid;
  border-color: black;
  border-width: 2px;
}
```

Now, what's the difference between padding, margins, and borders? First, let me explain padding and margins, as they are the most closely-related and confusable of the three. The margin of a div determines how much space the div has relative to other divs and the confines of the web page. If you set a div with all four margins set to 0, it will exist flush against other divs or the edges of the web page. There will be no breathing room. So the margin determines the space outside of the div itself relative to other elements of the web page.

The padding, on the other hand, is more inward-looking. It determines how close the div's content can get to the div's end. If you set all four sides to padding 0, the content will extend right up flush against the outer walls of the div. If you give the content more padding, it will stay away from the outer walls. You can compare the margin vs. padding issue to government, as margin is like foreign policy (how divs interact with the outside world), and padding is like domestic policy (how divs treat what's inside of them).

Finally, the border is simply that: the outermost part of the div. The border doesn't really determine anything about the div's relationship with other divs (margin) or its own inner content (padding). Rather, it is an almost purely stylistic feature. You can style the border in many ways, from a simple black solid line, to a dotted line, to even 3-D designs. Borders adds some character to the website and help compartmentalize the content. The one trick with the border is that if you make very large borders, they actually protrude outside of the div's territory (imagine an extremely thick border fence around a country that cuts into its neighboring country's territory). The programmer has to watch out for this, and sometimes has to compensate for large borders by changing around margins so that the border doesn't interfere with other content. Other than this case, borders don't really influence relationships between divs, and certainly not relationships between divs and their content.

So there you have it! I hope I helped clarify some confusion regarding these topics!