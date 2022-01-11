---
title:  "[C++] algorithm 라이브러리"
excerpt: "코딩테스트를 공부하면서 자주 쓰였던 것들 정리"

categories:
- cpp
tags:
  - [C++]


breadcrumb: true
toc: true
toc_sticky: true
---

#  sort
  - `#include<alghrithm>` 필요
  - 리스트를 정렬할 필요가 있을때 사용한다.
  ```c++
    sort(v.begin(), v.end());  //기본 오름차순 정렬
    sort(v.begin(), v.end(), greater()<> ); //기본 내림차순 정렬
    sort(v.begin(), v.end(), cmpFunction ); //비교함수가 있다면 원하는대로 정렬
  ```

# find
  - `#include<alghrithm>` 필요
  - 컨테이너 내에서 특정한 값을 찾아낼 때 사용한다.
  ```c++
    template <class InputIterator, class T>
    InputIterator find(InputIterator first, InputIterator last, const T& val);
  ```
  - `first`      탐색을 시작할 위치
  - `last`      탐색의 마지막 지점
  - `val`      탐색할 원소의 내용   

   - **return값**  
    `val`을 탐색하고, 존재하는 첫번째 값의 iterator를 반환한다. 없을 경우, last의 값을 반환한다.


# max_element
  - `#include<alghrithm>` 필요
  - 컨테이너 내에서 최댓값을 찾아낼 때 사용한다.
  - `max_element(v.begin(), v.end())` 꼴로 사용

  - **return값**
    리턴은 iterator를 반환하므로 실제 값을 찾아내려면 `*max_element(~~)` 형태로 써주면 된다!

# min_element
- `#include<alghrithm>` 필요
- 컨테이너 내에서 최솟값을 찾아낼 때 사용한다.
- `min_element(v.begin(), v.end())` 꼴로 사용

- **return값**
리턴은 iterator를 반환하므로 실제 값을 찾아내려면 `*min_element(~~)` 형태로 써주면 된다!



# transform
- `#include<alghrithm>` 필요
- 컨테이너들을 특정 방식으로 변환하는 함수이다. (ex. string 전체를 대,소문자로 변환)
  
```c++
transform(begin, end, d_begin, unary_op);
```
- `begin`    시작지점
- `end`    종료지점
- `d_begin`    변환 결과를 저장할 곳
- `unary_op`    변환 방식을 결정

  예시)
  ```c++
  transform(s.begin(),s.end(),s.begin(), ::tolower);
  ```
  s의 시작부터 끝까지, 소문자로 변환하여(::tolower) 처음 위치에 덮어쓴다.
  대문자로 변환할 경우 ::toupper

<br>
<small style ="color:gray;">(포스트번호: cpp_libraries) </small> 
 {: .text-right}

[TOP](#){: .btn .btn--warning} 
{: .text-right}