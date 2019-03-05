---
layout: default
title: Home
---

# TBD

Hi :)  This website isn't complete yet.  One day it will go
live... when I have time to learn how to design it the way I want it to work.

For now, it just serves as a redirect for projects where I'm
hosting documentation via GitHub Pages.  Thanks GitHub! <3

----------------------------------------------------------------------------------------

<dl>
{% for item in site.data.gh_projects %}
  <dt><a href="{{ item.link }}">{{ item.name }}</a></dt>
  <dd>{{ item.description | markdownify }}</dd>
  {% if item.repo %}
    {% capture repo %}{{ item.repo }}{% endcapture %}
  {% else %}
    {% capture repo %}{{ item.name }}{% endcapture %}
  {% endif %}
  {% capture gh_url %}https://github.com/{{ site.gh_username }}/{{ repo }}{% endcapture %}
  <dd>Code: <a href="{{ gh_url }}">{{ gh_url }}</a></dd>
{% endfor %}
</dl>
