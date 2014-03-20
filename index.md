---
layout: page
title: Hello World!
tagline: Supporting tagline
---
{% include JB/setup %}

Here's a sample "posts list".

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>

## To-Do

- [ ] clean up theme design
- [ ] add some images
- [ ] remove old jekyll bootstrap posts
- [ ] verify the comment integration
