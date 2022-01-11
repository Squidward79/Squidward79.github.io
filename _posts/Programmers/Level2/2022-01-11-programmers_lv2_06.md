---
title:  "[C++풀이] [1차]캐시"
excerpt: "프로그래머스 Level 2"

categories:
  - programmers
tags:
  - [Coding Test,C++]

breadcrumb: true
toc: true
toc_sticky: true

---

<div class="notice--warning" markdown=1>
 <span>📄 난이도 : 🟠🟠      </span>   
 <span>📄 언어 : C++  </span> 

 </div>
 


 [📂문제 보기](https://programmers.co.kr/learn/courses/30/lessons/17680) 

##  🔶 풀이 과정 
<u>페이지 교체 알고리즘</u>중 `LRU` (Least Recently Used) 알고리즘을 사용하는 문제였다.  LRU알고리즘이 뭔지 몰라서 테스트케이스만 가지고 분석해서 코드를 짰다가 정확한 알고리즘이 아니라서 채점에서 번번히 틀리는 케이스가 있었다. 만약 실전에서 이 문제를 마주쳤으면 좋은 점수는 못받았을듯..😥  

LRU 알고리즘은 제한된 크기의 캐시에 저장된 데이터 중 가장 오래 사용하지 않았던 데이터부터 대체하여 새로운 데이터로 갱신하는 알고리즘이다. 보통 가장 마지막으로 접근한 시간데이터를 함께 기록하거나, 접근한 기존데이터를 가장 최근에 들어온 위치로 옮긴다거나 하는 식으로 구현한다. 

나는 벡터를 사용하여 기존 데이터에 다시 접근한 경우 해당 요소를 지운 뒤 다시 추가해서 갱신하는 방법을 사용하였다.

***
<br><br>

### ✔ 벡터를 이용한 풀이 

```c++
#include <string>
#include <vector>
#include <algorithm>

using namespace std;

int solution(int cacheSize, vector<string> cities) {
    int answer = 0;
    vector<string> cache;

    //cacheSize가 0일 경우 예외처리
    if(cacheSize == 0) 
        return 5 * cities.size();

    for(int i=0; i<cities.size(); i++)
    {
        //전부 소문자로 바꾼다
        transform(cities[i].begin(), cities[i].end(),cities[i].begin(), ::tolower);
        auto iter = find(cache.begin(),cache.end(),cities[i]);
        if(cache.end() == iter)
        {
            answer += 5;

            // 1
            if(cache.size() < cacheSize)
                cache.push_back(cities[i]);
            else
            {
                cache.erase(cache.begin());
                cache.push_back(cities[i]);
            }
        }   

        // 2
        else 
        {
            answer += 1;       
            cache.erase(iter,iter+1);
            cache.push_back(cities[i]);
        }
    }

    return answer;
}
```

--- 
<br>

#### 👍 핵심 코드 
```c++
// 1

if(cache.size() < cacheSize)
    cache.push_back(cities[i]);
else
{
    cache.erase(cache.begin());
    cache.push_back(cities[i]);
}
```
└ 캐시에 존재하지 않는 데이터고, 캐시에 여유공간이 있으면 캐시에 추가한다. 만약 여유공간이 없다면 가장 앞의 데이터(가장 오래 사용하지 않은 데이터)를 삭제하고 맨 뒤에 추가한다.
  

```c++
// 2

else 
{
    answer += 1;       
    cache.erase(iter,iter+1);
    cache.push_back(cities[i]);
}
```
└ 만약 캐시에 이미 존재하는 데이터라면, 해당하는 데이터를 지운 뒤 맨 뒤에 같은 데이터를 추가한다. 캐시 내에서 뒤쪽에 존재하는 것일수록 최근에 접근한 데이터이므로, 맨 뒤에 추가한다는 것은 즉 접근 시기를 가장 최근으로 갱신하는 것이 된다.

--- 
<br>


  <small style ="color:gray;">(post-code: programmers_lv2_06) </small> 
 {: .text-right}

[TOP](#){: .btn .btn--warning} 
{: .text-right}