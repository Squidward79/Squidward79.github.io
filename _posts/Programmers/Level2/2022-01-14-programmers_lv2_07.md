---
title:  "[C++풀이] 더 맵게"
excerpt: "프로그래머스 Level 2 / Heap"

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
 


 [📂문제 보기](https://programmers.co.kr/learn/courses/30/lessons/42626) 

##  🔶 풀이 과정 
Heap에 대한 기본 개념을 물어보는 문제같다.  
힙의 개념을 알고 있다면 쉽게 풀릴 문제인데, 종료조건과 예외처리에서 늘 실수가 나온다. 반복문을 돌린다면 종료조건을 꼭 잘 세워두자..

힙을 사용하기 위해 두가지 STL을 이용하여 두번 풀었다.  
1. 힙으로 구현된 우선순위 큐 
1. vector를 힙으로 만드는 make_heap() 

make_heap보다는 **우선순위큐** 를 사용하는게 덜 복잡하고 코드도 간편했다!

***
<br>



### ✔ 우선순위 큐를 사용한 풀이

```c++
#include <string>
#include <vector>
#include <queue>
using namespace std;

int solution(vector<int> scoville, int K) {
    int answer = 0;
    priority_queue<int,vector<int>,greater<>> pq(scoville.begin(),scoville.end());
    
    while(pq.top() < K)
    {
        if(pq.size() ==1) return -1;
        int first = pq.top();
        pq.pop();
        int second = pq.top();
        pq.pop();
        pq.push(first + (second*2));
        answer++;
    }
    return answer;
}
```

--- 

#### 👍 핵심 코드 
```c++
while(pq.top() < K)
{
    if(pq.size() ==1) return -1;
    int first = pq.top();
    pq.pop();

    int second = pq.top();
    pq.pop();

    pq.push(first + (second*2));
    answer++;
}
```
└ 종료조건을 조금 더 보기 쉽게 바꾸었다. 우선순위 큐를 사용해서 코드가 훨씬 간결해졌다. top노드가 K보다 큰지 확인 후 앞에 두개를 빼내서 믹스한 후 다시 큐에 넣어주는 방식이다.
남은 노드가 1개일 경우는 믹스할 노드가 없고, 1개 남을 때까지 K이하라면 만족하는 경우가 없으므로 -1을 반환한다.
  
---
<br>

### ✔ vector를 힙으로 만든 풀이

```c++
#include <string>
#include <vector>
#include <algorithm>
using namespace std;

int solution(vector<int> scoville, int K) {
    int answer = 0;
    
    //벡터를 힙으로 변환
    make_heap(scoville.begin(),scoville.end(), greater<>());
    while(!scoville.empty())
    {
        //조건이 만족할때 종료조건. 조금 지저분하다
        if(scoville.front() >= K) return answer;
        if(scoville.size() == 1) return -1;
            
        //처음 노드와
        pop_heap(scoville.begin(),scoville.end(), greater<>());
        int first = scoville.back();
        scoville.pop_back();

        //두번째 노드를 섞어서
        pop_heap(scoville.begin(),scoville.end(), greater<>());
        int second = scoville.back();
        scoville.pop_back();

        //힙에 다시 추가한다
        scoville.push_back(first + (second*2));
        push_heap(scoville.begin(),scoville.end(), greater<>());
        
        answer++;
    }

    return -1;
}
```

--- 
<br>



  <small style ="color:gray;">(post-code: programmers_lv2_07) </small> 
 {: .text-right}

[TOP](#){: .btn .btn--warning} 
{: .text-right}