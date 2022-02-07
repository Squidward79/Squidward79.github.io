---
title: "About"
layout: splash
permalink: /about/
date: 2022-02-06

header:
  overlay_color: "#333"
  #overlay_filter: "0.5"
  #overlay_image: /assets/images/projecta_logo.png
  actions:
    - label: "Learn More"
      url: "/terms/"
  #caption: "캡션달기"

excerpt: "게임으로 즐거움을 주고싶은 개발자"

intro: 
  - excerpt: '포트폴리오 인트로 페이지를 위한 테스트 자막 '

feature_row:
  - image_path: /assets/images/alone_logo.png
    alt: "alone image"
    title: "Alone"
    excerpt: "PROJECT-A 첫번째 게임 
     기획 및 개발 "
    url: "/alone/"
    btn_label: "자세히 보기"
    btn_class: "btn--warning" 

  - image_path: /assets/images/thefins_logo.png
    alt: "thefins image"
    title: "The Fins"
    excerpt: "PROJECT-A 두번째 게임"
    url: "/thefins/"
    btn_label: "자세히 보기"
    btn_class: "btn--warning"

  - image_path: /assets/images/daydream_logo.png
    alt: "daydream Image"
    title: "DayDream"
    excerpt: "PROJECT-A 세번째 게임"
    url: "/daydream/"
    btn_label: "자세히 보기"
    btn_class: "btn--warning"

  - image_path: /assets/images/marvelron_logo.jpg
    alt: "marvelron Image"
    title: "마블론 - 던전과 용병들"
    excerpt: |
      PROJECT-A 네번째 게임  
      현재 개발중..!!

  - image_path: /assets/images/a_logo.jpg
    alt: "projecta image"
    title: "More Game"
    excerpt: "그 외의 다른 게임 프로젝트들"
    url: "/gamedev/"
    btn_label: "자세히 보기"
    btn_class: "btn--warning" 





feature_row2:
  - image_path: https://user-images.githubusercontent.com/45874696/152729024-aad5fe06-9293-46fb-ad3d-719bb857525f.png
    alt: "final project iamge"
    title: "졸업작품 프로젝트"
    excerpt: |
      "혼합현실 환경에서 가상 MIDI악기를 연주하는 프로그램입니다. 
      Vive Pro를 사용하였으며 주변 공간을 인식하여 현실 기반의 Mesh를 생성합니다. 
      악기를 연주를 하면 발생하는 파티클이 현실공간과 부딫혀 상호작용합니다. 모바일 어플리케이션과 합주도 가능합니다."
    #url: "#test-link"
    #btn_label: "자세히 보기"
    #btn_class: "btn--warning"

feature_row3:
  - image_path: https://user-images.githubusercontent.com/45874696/67154395-ce833680-f336-11e9-8548-ac0d983bfce1.png
    alt: "raycasting image"
    title: "RayCasting 구현 프로그램"
    excerpt: |
      "RayCasting으로 구현한, 단층촬영 이미지를 3D모델로 만드는 프로그램입니다. 
      3D모델의 투명도를 조절하여 피부와 그 내부의 뼈를 볼 수 있고, 모델을 회전시킬 수 있습니다."
    url: /mini-project/raycasting-program/
    btn_label: "자세히 보기"
    btn_class: "btn--warning"
---

{% include feature_row id="intro" type="center" %}

<h1> GAME PROJECTS </h1>

{% include feature_row %}




<h1> MORE PROJECTS </h1>

{% include feature_row id="feature_row2" type="left" %}

{% include feature_row id="feature_row3" type="left" %}