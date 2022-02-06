---
title:  "[미니 프로젝트] 레이캐스팅 프로그램"
excerpt: "그래픽스 수업 과제 프로젝트"

categories:
  - mini-project 
tags:
  - [c++,mini-project]

breadcrumb: true

toc: true
toc_sticky: true

---


## 소스코드 
    
<h3><a href = "https://github.com/Squidward79/RayCasting_program/blob/master/RayCast.cpp"> Raycasting Program - Github 저장소 </a></h3>

## 프로그램 사진

<p align="center">
	<img src="https://user-images.githubusercontent.com/45874696/67154388-9bd93e00-f336-11e9-980f-8054df29ede0.png" alt="first" width="250"/>
  <img src="https://user-images.githubusercontent.com/45874696/67154374-3a18d400-f336-11e9-8ba8-f8bfafba780c.png" alt="second" width="250"/>
  <img src="https://user-images.githubusercontent.com/45874696/67154377-50269480-f336-11e9-91c2-0dad29a50bc0.png" alt="third" width="250"/>

</p>

### 사용한 툴
  Visual Studio / C++ / OpenGL
  
### 개요 
  C++과 OpenGL을 이용한 단층촬영 볼륨데이터의 시각화 프로그램 작성
  
### 설명

사람의 단층촬영 볼륨 데이터를 읽어들여 3D모델이미지로 보여주는 RayCasting 구현 프로그램입니다.  
RayCasting을 적용해 3D모델의 투명도를 조절하면, 피부에서 뼈까지 단계적으로 볼 수 있도록 구현하였습니다.  
키보드로 투명도 설정, 모델의 회전이 가능합니다. 조명모델은 Phong공식을 적용하였습니다.

학교 과제로 만든 프로젝트이며 단층데이터를 읽어오고 창을 띄우는 기본적 openGL코드는 교수님께 받은 뼈대 코드를 바탕으로 하였습니다.
**ComputeNormal**, 	**AssignOpacity**, **ComputeColor** , **CreateImage** 부분의 구현을 담당하였습니다.

### 배운 점
그래픽스 수업시간에 배운 렌더링파이프라인의 일부를 실제로 구현해보는 좋은 경험이었습니다.
수학공식들을 코드로 옮기고 적용하는건 시행착오도 많고 꽤 어려웠지만 끝까지 해내려고 노력하여 결과물을 만들어 내었습니다.


<small style ="color:gray;">(post-code: raycasting-program) </small> 
 {: .text-right}

[TOP](#){: .btn .btn--warning} 
{: .text-right}