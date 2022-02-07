---
title: "게임으로 즐거움을 전하고 싶은"
layout: splash
permalink: /about/
date: 2022-02-06

header:
  overlay_color: "#000"
  overlay_filter: "0.3"
  overlay_image: /assets/images/games-gif.gif
  #  - label: "Learn More"
  #    url: "/terms/"
  #caption: "캡션달기"

excerpt: |
  Lee Homin 입니다.

intro: 
  - excerpt: |
    

feature_row:
  - image_path: /assets/images/alone_logo.png
    alt: "alone image"
    title: "Alone"
    excerpt: |
      PROJECT-A  
      2018 제작


    url: "/alone/"
    btn_label: "자세히 보기"
    btn_class: "btn--warning" 

  - image_path: /assets/images/thefins_logo.png
    alt: "thefins image"
    title: "The Fins"
    excerpt: |
      PROJECT-A  
      2019 제작
    url: "/thefins/"
    btn_label: "자세히 보기"
    btn_class: "btn--warning"

  - image_path: /assets/images/daydream_logo.png
    alt: "daydream Image"
    title: "DayDream"
    excerpt: |
      PROJECT-A  
      2020 제작
    url: "/daydream/"
    btn_label: "자세히 보기"
    btn_class: "btn--warning"

  - image_path: /assets/images/marvelron_logo.png
    alt: "marvelron Image"
    title: "마블론"
    excerpt: |
      PROJECT-A  
      2021 ~ 개발중!

  - image_path: https://user-images.githubusercontent.com/45874696/152754350-072f94c9-73c9-4d9a-a770-2513c994dfb0.png
    alt: "firegame image"
    title: "火炎焱燚"
    excerpt: |
      CAPCOM 인턴십 프로그램   
      2020 제작 

    url: "/firegame/"
    btn_label: "자세히 보기"
    btn_class: "btn--warning" 

  - image_path: /assets/images/a_logo.png
    alt: "more Image"
    title: "More Games"
    excerpt: |
      그 외 개발에 참여했던  
      게임들의 모음입니다.
    url: "/categories/gamedev/"
    btn_label: "자세히 보기"
    btn_class: "btn--warning"





feature_row2:
  - image_path: https://user-images.githubusercontent.com/45874696/152729024-aad5fe06-9293-46fb-ad3d-719bb857525f.png
    alt: "final project iamge"
    title: "졸업작품 프로젝트"
    excerpt: |
      혼합현실 환경에서 가상 MIDI악기를 연주하는 프로그램입니다.   
      Vive Pro를 사용하였으며 주변 공간을 인식하여 현실 기반의 Mesh를 생성합니다.
      악기를 연주를 하면 발생하는 파티클이 현실공간과 부딫혀 상호작용합니다. 모바일 어플리케이션과 합주도 가능합니다.   
    #url: "#test-link"
    #btn_label: "자세히 보기"
    #btn_class: "btn--warning"



feature_row3:
  - image_path: https://user-images.githubusercontent.com/45874696/67154377-50269480-f336-11e9-91c2-0dad29a50bc0.png
    alt: "raycasting image"
    title: "RayCasting 구현 프로그램"
    excerpt: |
      RayCasting으로 구현한, 단층촬영 이미지를 3D모델로 만드는 프로그램입니다.    
      3D모델의 투명도를 조절하여 피부와 그 내부의 뼈를 볼 수 있고, 모델을 회전시킬 수 있습니다.   
    url: /mini-project/raycasting-program/
    btn_label: "자세히 보기"
    btn_class: "btn--warning"

feature_row4:
  - image_path: https://user-images.githubusercontent.com/45874696/67154576-acd77e80-f339-11e9-819b-c423a81bdf43.png
    alt: "cuda image"
    title: "CUDA 병렬프로그래밍"
    excerpt: |
      GPU와 CPU의 영상처리 성능비교를 위해 GPU쪽은 CUDA로 프로그래밍한 프로젝트입니다.   
      주행 동영상의 차선검출 알고리즘으로 비교를 진행하였고 CPU에 비해 GPU를 사용할 경우 약 20배의 성능향상을 확인할 수 있었습니다. 
    url: https://github.com/Squidward79/Parallel-programming
    btn_label: "자세히 보기"
    btn_class: "btn--warning"
---

{% include feature_row id="intro" type="center" %}

<h1> GAME PROJECTS </h1>

{% include feature_row %}


<h1> MORE PROJECTS </h1>

{% include feature_row id="feature_row3" type="left" %}

{% include feature_row id="feature_row4" type="left" %}

{% include feature_row id="feature_row2" type="left" %}

