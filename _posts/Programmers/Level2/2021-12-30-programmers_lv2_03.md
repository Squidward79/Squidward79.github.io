---
title:  "[C++풀이] 네트워크"
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
 


 [📂문제 보기](https://programmers.co.kr/learn/courses/30/lessons/43162?language=cpp) 

##  🔶 풀이 과정 
하나의 컴퓨터에서 연결된 컴퓨터를 전부 방문한다. <u>무조건 컴퓨터 1대는 하나의 네트워크에 연결</u>되어 있기 때문에 네트워크의 갯수는 증가한다. <u>한번 방문한 컴퓨터는 이미 네트워크에 연결</u>되어 있는 것이 확인되어 있기 때문에, 다시 확인할 필요가 없다. 이 과정을 모든 컴퓨터에 대하여 처리한다.  

<small>
DFS함수를 만들고 방문처리를 하는 부분까지는 막힘없이 진행했지만, 언제 네트워크의 갯수를 증가처리 할지에 대해 고민하는데 시간이 좀 걸렸다. 풀어낸 후에는 불필요하게 조건검사하는 부분을 찾아내어 쳐냈다.
</small>

***
<br><br>

### ✔ 재귀를 이용한 DFS 풀이

```c++
#include <string>
#include <vector>

using namespace std;

vector<int> isvisit;
void dfs(vector<vector<int>>& computers, int index)
{
    isvisit[index] = 1;
    for(int i=0; i<computers.size(); i++)
    {
        if(computers[index][i] == 1 && isvisit[i] == 0)
            dfs(computers,i);
    }
}

int solution(int n, vector<vector<int>> computers) {
    isvisit = vector<int>(n,0);
    int answer =0;
    
    for(int i =0; i<n; i++)
    {
        if(isvisit[i] == 1) continue;
        dfs(computers,i);
        answer++;
    }
    return answer;
}
```

--- 
<br>

#### 👍 핵심 코드 
```c++
for(int i =0; i<n; i++)
{
    if(isvisit[i] == 1) continue;
    dfs(computers,i);
    answer++;
}
```
└ 각 컴퓨터에 대하여 dfs함수를 수행하는데, 이미 방문한적이 있다면 수행하지 않아도 이미 갯수에 포함한 네트워크에 연결되어 있는 컴퓨터로 본다. `처음 방문하는 컴퓨터라면 항상 네트워크에 연결`되어 있으므로 결과값을 1 증가시킨다.

```c++
for(int i=0; i<computers.size(); i++)
{
    if(computers[index][i] == 1 && isvisit[i] == 0)
        dfs(computers,i);
}
```
└ 컴퓨터에서 네트워크에 연결된 다른 컴퓨터가 있는지 체크한 후, 그 컴퓨터가 `아직 방문하지 않은 컴퓨터라면` 방문하여 다시 연결된 컴퓨터를 체크한다.

--- 
<br>


  <small style ="color:gray;">(post-code: programmers_lv2_03) </small> 
 {: .text-right}

[TOP](#){: .btn .btn--warning} 
{: .text-right}