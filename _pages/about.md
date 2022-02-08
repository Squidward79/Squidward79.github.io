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

excerpt: |+
  프로그래머 Lee Homin 입니다.     
  .        
  제가 개발에 참여한 게임으로  
  사람들에게 즐거움을 전할 수 있다면  
  그것이 바로 저의 행복입니다.  
  .   
  제가 추구하는 가치는 세가지 입니다.    
  ◼ 경험:  
  - 모든 경험은 경험치가 됩니다.      
  ◼ 도전:     
  - 도전은 발전의 밑바탕이 됩니다.  
  ◼ 재미:   
  - 재미있는 일은 깊은 몰입의 원천입니다.     
  .   

  
intro: 
  - title: "경험과 도전은 언제나 의미있는 것이라 생각합니다."
    class: wide
    excerpt: |
      2017년부터 프로그래밍을 배우기 시작해 꾸준히 게임개발에 배운 것을 적용하려 노력 중입니다.  
      현재는 PROJECT-A라는 2인 게임개발팀으로 4년째 매년 여름 작은 게임 프로젝트를 진행하고 있습니다.  
      게임개발은 주로 Unity와 C#을 활용하였고, 엔진 위에서 간단한 개발툴을 만들어 활용하기도 하였습니다.  

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

  - image_path: /assets/images/firegame_logo.png
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
      현실과 가상공간이 섞인 혼합현실(Mixed Reality) 환경에서 MIDI악기인 런치패드를 가상으로 연주하는 프로그램입니다.   
      Vive Pro와 Unity, Android로 개발하였으며 크게 공간인식, 악기연주, 상호작용으로 구분됩니다.
      우선 Vive의 depth카메라를 통해 주변 공간을 인식하여 현실 기반의 Mesh를 생성합니다. 그런 다음 눈앞에 놓여진 가상의 악기를 컨트롤러를 이용해 연주하게 되면 발생하는 오디오 파형에 맞춰 공간에 파티클 이펙트가 발생합니다. 이 파티클 이펙트는 현실 기반으로 생성된 Mesh와 충돌하여 상호작용하여 실제 공간에 3D 파티클이 부딪히는 것처럼 느껴지게 됩니다. 
      포톤 서버를 이용하여 모바일 어플리케이션과 동시에 합주도 가능합니다.   

    #url: "#test-link"
    #btn_label: "자세히 보기"
    #btn_class: "btn--warning"



feature_row3:
  - image_path: https://user-images.githubusercontent.com/45874696/67154377-50269480-f336-11e9-91c2-0dad29a50bc0.png
    alt: "raycasting image"
    title: "RayCasting 구현 프로그램"
    excerpt: |
      RayCasting으로 구현한, 단층촬영 이미지를 3D모델로 만드는 프로그램입니다. C++와 OpenGL로 작성하였으며 이미지 렌더링을 위한 노말, 투명도, 컬러 계산 등을 구현하였습니다. 3D모델의 투명도를 조절하여 피부와 그 내부의 뼈를 볼 수 있고, 모델을 회전시키는 기능이 있습니다.   

    url: https://github.com/Squidward79/RayCasting_program
    btn_label: "자세히 보기"
    btn_class: "btn--warning"

feature_row4:
  - image_path: https://user-images.githubusercontent.com/45874696/67154576-acd77e80-f339-11e9-819b-c423a81bdf43.png
    alt: "cuda image"
    title: "CUDA 병렬프로그래밍"
    excerpt: |
      GPU와 CPU의 영상처리 성능비교를 위해 같은 알고리즘에 대하여 CPU와 병렬처리한 GPU의 처리속도를 비교하는 프로젝트입니다.   
      고속도로 주행 동영상의 차선검출 알고리즘으로 비교를 진행하였고 GPU의 병렬 프로그래밍은 NVIDIA사의 CUDA를 사용하였습니다.  
      그 결과 해당 알고리즘을 처리하는데에는 CPU에 비해 GPU가 약 20배의 성능차이를 보임을 확인할 수 있었습니다. 

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

