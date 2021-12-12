---
title: "카테고리 테스트"
layout: archive
permalink: /categories/test/
author_profile: true
sidebar:
    nav: sidemenu
---

{% assign posts = site.categories["test"] %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} 
{% endfor %}