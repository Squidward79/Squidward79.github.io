---
title: "PROJECT-A"
layout: archive
permalink: /categories/project-a/
author_profile: true
sidebar:
    nav: sidemenu
---

{% assign posts = site.categories["project"] %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} 
{% endfor %}