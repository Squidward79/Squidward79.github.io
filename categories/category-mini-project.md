---
title: "Mini Project"
layout: archive
permalink: /categories/mini-project/
author_profile: true
sidebar:
    nav: sidemenu
---

{% assign posts = site.categories["mini-project"] %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} 
{% endfor %}