---
#
# You can use Markdown in the editable content below the three dashes (---)
#
# Editable - Title and Description display on the page and in HTML meta tags
#
title: Announcements
#
# Don't edit items below - they control the page layout
#
return-top: no
layout: page
page-type: subpage
page-description: yes
permalink: /announcements
#
---


<section>
  <div>
  {% for post in site.posts %}
    <ul>
      <a href="{{ site.url }}{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>
    </ul>
  {% endfor %}
  </div>
</section>
