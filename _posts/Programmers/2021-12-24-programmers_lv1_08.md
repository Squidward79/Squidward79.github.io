---
title:  "[C++풀이] 문자열 내 마음대로 정렬하기"  
excerpt: "프로그래머스 Level 1 연습문제"

categories:
  - programmers
tags:
  - [Coding Test,C++]

date: 2021-12-25

breadcrumb: true
---

<div class="notice--warning" markdown=1>
 <span>📄 난이도 : 1   </span> &nbsp &nbsp &nbsp &nbsp
 <span>📄 언어 : C++  </span> 
 </div>
 
 [📂문제 보기](https://programmers.co.kr/learn/courses/30/lessons/12915) 

***
##  🔶 풀이법
정렬을 해야하는데 조건이 두개.
1. n번째 글자를 기준으로 할 것
2. n번째 글자가 같다면 기존 사전식 정렬을 할것

algorithm의 sort를 사용하고, 비교함수를 직접 작성하여 풀었다.   
2번조건을 우선 검사하여, 글자가 같을 경우엔 일반적인 string sort 하듯이 했고, 그 외에는 n번째를 기준으로 정렬시켰다.

### ✔ 풀이 코드 

```c++
#include <string>
#include <vector>
#include <algorithm>

using namespace std;

int num;
bool cmp(const string& a, const string& b)
{
    int tmp = num;
    if(a[tmp] == b[tmp])
        return a<b;
    return a[tmp] < b[tmp];     
}

vector<string> solution(vector<string> strings, int n) {
    num = n;
    sort(strings.begin(),strings.end(),cmp);
    return strings;
}
```
--- 
<br>


  <small style ="color:gray;">(문제번호: 08) </small> 
 {: .text-right}

[TOP](#){: .btn .btn--warning} 
{: .text-right}