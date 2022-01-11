---
title:  "[C++] 자주 쓰이는 라이브러리와 함수들"
excerpt: "코딩테스트를 공부하면서 자주 쓰였던 것들 정리"

categories:
- cpp
tags:
  - [C++]

last_modified_at: 2022-01-11

breadcrumb: true
toc: true
toc_sticky: true
---

# string
- `#include <string>` 필요
- tip: **숫자 1개를 int로 바꾸기**
  - `char형 숫자1개 - '0'` 을 해주면 해당하는 숫자가 int형으로 나온다!!


| 멤버           | 설명                    | 예시      |
| :------------- | :---------------------- | :-------- |
| stoi(string s) | string을 int형으로 변환 | stoi() |
| toupper(string s) | 전부 대문자로 변환 | toupper("ASDF") |
| tolower(string s) | 전부 소문자로 변환 | stoi() |



# vector
- `#include <vector>` 필요
- 기본적으로 가장 자주 쓰이는 멤버

| 멤버            | 설명                    | 예시                 |
| :-------------- | :---------------------- | :------------------- |
| .front()        | 가장 앞에 있는 원소반환 | v.front()            |
| .back()         | 가장 뒤에 있는 원소반환 | v.back()             |
| .size()         | 리스트 내 원소의 갯수   | if ( v.size() == 5 ) |
| .empty()        | 빈 리스트라면 true반환  | if( v.empty() )      |
| .push_back(sth) | 맨 뒤에 원소 추가       | v.push_back("abc");  |
| .pop_back()     | 맨 뒤 원소 삭제         | v.pop_back();        |

## - vector의 삭제 
- **`erase`**

    ```c++
    v.erase(position, first, last)
    ```
    - `position`  
      제거할 요소의 위치
    - `first`  
      제거되는 첫번째 요소의 위치
    - `last`  
      제거되는 <u>마지막 요소 바로 뒤의</u> 위치  

     - **return값**  
      제거한 요소 바로 다음을 가리키는 iterator, 요소가 없으면 .end()를 반환 
    
    예시)
    ```c++
     v.erase( v.begin( ) ); 
     //맨 앞 요소 제거 
     
     v.erase( v.begin( ) + 1, v.begin( ) + 3 ); 
     //2번째부터 그 뒤의 2개 제거
     ```
- **`중복요소 제거`**
  - erase와 unique를 동시에 사용한다. 
  - unique는 `algorithm`헤더에 포함 
  - unique의 사용법
    ```c++
      unique(v.begin(),v.end())
      //중복되는 원소들을 가장 뒤쪽으로 밀어버린다!
      //return값은 밀어버린 후 중복원소가 시작되는 첫 지점의 iterator
    ```
  - 따라서, 다음과 같이 코드를 작성하면 <u>중복원소가 싹 사라진다!</u>
    ```c++
      v.erase( unique(v.begin(),v.end()) , v.end());
    ```



# 순열과 조합

# 비트연산

# 홀수 찾기 
 ```c++
  int n;
  string str = n & 1 ? "Odd" : "Even";
  // & 1 연산으로 홀수를 찾아내는 스킬 아주 쓸만하다. 기억해두자.
 ```


   <small style ="color:gray;">(포스트번호: cpp_libraries) </small> 
 {: .text-right}

[TOP](#){: .btn .btn--warning} 
{: .text-right}