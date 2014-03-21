---
layout : page
title : Welcome!
tagline : I hope we both learn something
---
{% include JB/setup %}

Here's a sample "posts list".

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>

### Hello, and welcome to my humble blog. 

#### Goals

There are a number of things I hope to accomplish with this blog, let me list them here:

1. Put things in writing so I am more likely to remember them.
2. Deposit some code examples, and such to help others learn from my follies.
3. Give my opinions on various tools, suites, languages, etc.
4. Expand my horizons, and learn new things.
5. Have a place to deposit Statisical, Mathematical, and Data thoughts, and findings.

#### Requisites

I hope that my knowledge and experiences here will help anyone who read this to become 
better aquainted with the tools, methods, and things I do. That said I don't intend to 
give full lectures or offer much in the way of support, I just don't have the time. So
I suggest that I list requisites for each post, page, blog, what have you. with the 
understanding that you might need to do some leg work from time to time.


## To-Do

- [ ] clean up theme design
- [ ] add some images
- [ ] remove old jekyll bootstrap posts
- [ ] verify the comment integration
