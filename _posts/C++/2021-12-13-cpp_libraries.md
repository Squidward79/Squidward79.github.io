---
title:  "[C++] 자주 쓰이는 라이브러리와 함수들"
excerpt: "코딩테스트를 공부하면서 자주 쓰였던 것들 정리"

categories:
- cpp
tags:
  - [C++]

date: 2021-12-13
last_modified_at: 2021-12-21
breadcrumb: true
toc: true
toc_sticky: true
---


##  [vector]

- 기본적으로 가장 자주 쓰이는 멤버

|      멤버       |          설명           |          예시           |
| :-------------: | :---------------------: | :---------------------: |
|    .front()     | 가장 앞에 있는 원소반환 |      list.front()       |
|     .back()     | 가장 뒤에 있는 원소반환 |       list.back()       |
|     .size()     |  리스트 내 원소의 갯수  | if ( list.size() == 5 ) |
|    .empty()     | 빈 리스트라면 true반환  |   if( list.empty() )    |
| .push_back(sth) |    맨 뒤에 원소 추가    | list.push_back("abc");  |
|   .pop_back()   |     맨 뒤 원소 삭제     |    list.pop_back();     |


## [sort]
  - `#include<alghrithm>`이 필요하다. 
  - 리스트를 정렬할 필요가 있을때 사용한다.
  - ```c++
      sort(list.begin(),list.end());  //기본 오름차순 정렬
      sort(list.begin(),list.end(),greater()<>); //기본 내림차순 정렬
      sort(list.begin(),list.end(),cmpFunction); //비교함수가 있다면 원하는대로 정렬
    ```



## [순열과 조합]

## [비트연산]
