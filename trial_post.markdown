---
title: trial posts
permalink: /trial-post/
layout: page
---

<ul class="posts noList">
          {% for post in site.posts %}
            <li>
                <span class="date">{{ post.date | date: '%B %d, %Y' }}</span>
                <h3><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h3>
                <p class="description">{% if post.description %}{{ post.description  | strip_html | strip_newlines | truncate: 250 }}{% else %}{{ post.content | strip_html | strip_newlines | truncate: 250 }}{% endif %}</p>
            </li>
          {% endfor %}
        </ul>
<!-- Pagination links -->
<div class="pagination">
{% if site.previous_page %}
<a href="{{ site.baseurl }}{{ site.previous_page_path }}" class="previous button__outline">Newer Posts</a>  
{% endif %}
{% if site.next_page %}
<a href="{{ site.url }}{{ site.next_page_path }}" class="next button__outline">Older Posts</a>
{% endif %}
</div>
