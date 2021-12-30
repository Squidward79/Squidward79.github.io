---
title:  "[C++풀이] 타겟 넘버"
excerpt: "프로그래머스 Level 2 - DFS/BFS"

categories:
  - programmers
tags:
  - [Coding Test,C++]

date: 2021-12-30

breadcrumb: true

---

<div class="notice--warning" markdown=1>
 <span>📄 난이도 : 🟠🟠      </span>   
 <span>📄 언어 : C++  </span> 

 </div>
 


 [📂문제 보기](https://programmers.co.kr/learn/courses/30/lessons/43165) 

***
##  🔶 풀이 과정 
DFS를 공부하지 않은 채로 일단 들이박아서 어떻게든 풀어내보자, 하고 풀어낸 첫번째 방법은 조합을 이용한 것.    
조합을 이용한 풀이는 결과적으로 답은 맞았으나, 복잡도에서 상당히 손해를 봐서 풀어내면서도 비효율적이라 생각했다.  
이후에 다시 DFS를 학습한 후 재귀로 다시 풀었는데 아직 익숙치가 않아 그런지 꽤 버벅였다.  
\+ \- 두 가지로 나뉘는 갈래를 그래프 처럼 생각할 수 있다는 아이디어가 중요한 듯 하다.  
연습이 많이 필요할듯 ㅠㅠ
***
<br><br>

### ✔ 재귀를 이용한 DFS 풀이

```c++
#include <string>
#include <vector>

using namespace std;

int target;
int answer = 0;

void dfs(vector<int>& numbers,int depth, int sum)
{
    if(depth > numbers.size()-1)
    {
        if(sum == target)
            answer++;  
        return;
    }
    else
    {
        dfs(numbers,depth + 1, numbers[depth] + sum);
        dfs(numbers,depth + 1, -numbers[depth] + sum);
    }

}

int solution(vector<int> numbers, int _target) {
    target = _target;
    dfs(numbers, 1, numbers[0]);
    dfs(numbers, 1, -numbers[0]);
    return answer;
}
```

--- 
<br>

#### 👍 핵심 코드 
```c++
    dfs(numbers,depth + 1, numbers[depth] + sum);
    dfs(numbers,depth + 1, -numbers[depth] + sum);
```
└ dfs 재귀를 위한 코드. 갈래가 +1, -1 두 가지이기 때문에 두 개의 재귀를 사용한다. 

```c++
    if(depth > numbers.size()-1)
    {
        if(sum == target)
            answer++;  
        return;
    }
```
└ 최고 깊이에 도달하면, 재귀를 멈추고 현재까지 더하고 뺀 값이 target과 맞는지 체크하여 맞다면 결과값에 1을 더한다.

--- 
<br>

### ✔ 조합을 이용한 풀이

```c++
#include <string>
#include <vector>
#include <algorithm>
using namespace std;

int solution(vector<int> numbers, int target) {
    int answer = 0;
    vector<bool> tmp(numbers.size(),false);

    for(int i=0; i<numbers.size(); i++)
    {
        for(int n=0; n<tmp.size()-i; n++)
            tmp[i] = true;

        do{
            int sum = 0;
            for(int j = 0; j<numbers.size(); j++)
            {
                tmp[j] == true ? sum+= numbers[j] : sum-= numbers[j];
            }
            if(sum == target) answer++;

        }while(prev_permutation(tmp.begin(),tmp.end()));

    }
    return answer;
}
```
└ prev_permutation을 이용하여 모든 항을 더해나가다가 마지막 i개의 항만 빼주는 방식을 사용했다. 상당히 많은 반복이 발생하여 size가 클수록 처리시간이 길어졌다.

--- 
<br>


  <small style ="color:gray;">(post-code: programmers_lv2_02) </small> 
 {: .text-right}

[TOP](#){: .btn .btn--warning} 
{: .text-right}