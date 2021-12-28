---
title:  "[C++풀이] N개의 최소공배수"
excerpt: "프로그래머스 Level 2"

categories:
  - programmers
tags:
  - [Coding Test,C++]

date: 2021-12-29

breadcrumb: true

---

<div class="notice--warning" markdown=1>
 <span>📄 난이도 : 🟠🟠      </span>   
 <span>📄 언어 : C++  </span> 

 </div>
 


 [📂문제 보기](https://programmers.co.kr/learn/courses/30/lessons/12953?language=cpp) 

***
##  🔶 풀이법
두 가지 방법으로 풀어보았는데, 첫번째는 최대값의 배수로 다른 수들을 나누었을 때 나누어 떨어진다면 그 수가 최소공배수임을 이용하였다. 이렇게 풀고 다른 풀이를 보니 `유클리드 호제법`을 이용해서 신기하게 푸는게 있어서 학습 후 다시 풀어봤다.      

이에 대해서 더 정리한 것을 보려면 [최소공배수와 최대공약수](https://squidward79.github.io/algorithm/algorithm_01/) 링크를 참조! 

***
<br><br>

### ✔ 유클리드 호제법을 이용한 풀이

```c++
#include <string>
#include <vector>

using namespace std;

int gcd(int a, int b)
{
    return b == 0? a :gcd(b, a % b);
}

int solution(vector<int> arr) {
    int lcm = arr[0];
    for(int i=1; i<arr.size(); i++)
    {
        lcm = lcm * arr[i] / gcd(lcm,arr[i]);
    }
    return lcm;
}
```
--- 
<br>

#### 👍 핵심 코드 
최소공배수를 구하는 공식   
$lcm(a,b) = a * b / gcd(a,b)$ 
---
를 사용하기 위해 우선 최대공약수를 구하는 함수를 작성한다.

```c++
int gcd(int a, int b)
{
    return b == 0? a :gcd(b, a % b);
}
```
그런 다음, arr의 값을 순회하며 두 수씩 최대공배수를 구해낸다.
```c++
  lcm = lcm * arr[i] / gcd(lcm,arr[i]);
```
순회가 끝나면 최종적으로 모든 수의 최소공배수가 나온다.

--- 
<br><br>

### ✔ 최대값의 배수를 이용한 풀이 

```c++
#include <string>
#include <vector>
#include <algorithm>

using namespace std;

//가장 큰 수의 배수로 나머지 항들을 나눠본다. 
//처음 모든 수가 나누어 떨어지는 그 수가 바로 최소공배수

int solution(vector<int> arr) {
    int max = *max_element(arr.begin(),arr.end());
    int gcd = max;
    while(true)
    {
        bool is_gcd = true;    
        for(int i=0; i<arr.size(); i++)
        {
            if(gcd % arr[i] != 0)
            {
                is_gcd = false;
                break;
            }
        }
        if(is_gcd == false )gcd += max;
        else break;
    }
    return gcd;
}
```
--- 
<br>


  <small style ="color:gray;">(post-code: programmers_lv2_01) </small> 
 {: .text-right}

[TOP](#){: .btn .btn--warning} 
{: .text-right}