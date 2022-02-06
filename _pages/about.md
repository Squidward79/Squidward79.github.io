---
title: "About"
layout: splash
permalink: /about/
date: 2022-02-06

header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: /assets/images/projecta_logo.png
  actions:
    - label: "Learn More"
      url: "/terms/"
  caption: "캡션달기"

excerpt: "게임으로 즐거움을 주고싶은 개발자"

intro: 
  - excerpt: '포트폴리오 인트로 페이지를 위한 테스트 자막 '

feature_row:
  - image_path: /assets/images/alone_logo.png
    alt: "thefins image"
    title: "The Fins"
    excerpt: "PROJECT-A 첫번째 게임"
    url: "#daydream"
    btn_label: "자세히 보기"
    btn_class: "btn--warning" 

  - image_path: /assets/images/thefins_logo.png
    alt: "thefins image"
    title: "The Fins"
    excerpt: "PROJECT-A 두번째 게임"
    url: "#test-link"
    btn_label: "자세히 보기"
    btn_class: "btn--warning"

  - image_path: /assets/images/daydream_logo.png
    alt: "daydream Image"
    title: "DayDream"
    excerpt: "PROJECT-A 세번째 게임"
    url: "#daydream"
    btn_label: "자세히 보기"
    btn_class: "btn--warning"





feature_row2:
  - image_path: /assets/images/unsplash-gallery-image-2-th.jpg
    alt: "placeholder image 2"
    title: "Placeholder Image Left Aligned"
    excerpt: 'This is some sample content that goes here with **Markdown** formatting. Left aligned with `type="left"`'
    url: "#test-link"
    btn_label: "Read More"
    btn_class: "btn--warning"

feature_row3:
  - image_path: /assets/images/unsplash-gallery-image-2-th.jpg
    alt: "placeholder image 2"
    title: "Placeholder Image Right Aligned"
    excerpt: 'This is some sample content that goes here with **Markdown** formatting. Right aligned with `type="right"`'
    url: "#test-link"
    btn_label: "Read More"
    btn_class: "btn--warning"

feature_row4:
  - image_path: /assets/images/unsplash-gallery-image-2-th.jpg
    alt: "placeholder image 2"
    title: "Placeholder Image Center Aligned"
    excerpt: 'This is some sample content that goes here with **Markdown** formatting. Centered with `type="center"`'
    url: "#test-link"
    btn_label: "Read More"
    btn_class: "btn--warning"
---

{% include feature_row id="intro" type="center" %}

<h1> GAME PROJECTS </h1>

{% include feature_row %}


<h1> STUDY PROJECTS </h1>

{% include feature_row id="feature_row2" type="left" %}

{% include feature_row id="feature_row3" type="right" %}

{% include feature_row id="feature_row4" type="center" %}