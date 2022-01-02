---
title:  "[C++풀이] 단어 변환"
excerpt: "프로그래머스 Level 2 - DFS/BFS"

categories:
  - programmers
tags:
  - [Coding Test,C++]

date: 2022-01-01

breadcrumb: true

---

<div class="notice--warning" markdown=1>
 <span>📄 난이도 : 🟠🟠      </span>   
 <span>📄 언어 : C++  </span> 

 </div>
 


 [📂문제 보기](https://programmers.co.kr/learn/courses/30/lessons/43163) 

##  🔶 풀이 과정 
재귀 DFS로 풀어내려고 했고, 접근 자체는 빠르게 했으나 예외처리과정에서 시간을 꽤 많이 썼다.
   1. 전체 string중에서 하나씩 비교하며, 아직 방문하지 않았고, 한글자만 다른 값을 찾아 방문한다.
   2. target과 같은 글자에 방문하면, depth를 체크하여 최소 깊이라면 저장한다.
   3. 전체를 다 방문해도 target이 없다면 그냥 return 한다.
   4. 모든 탐색이 끝난 뒤 최소깊이가 초기값이 아니라면 해당 값을 리턴한다.
   5. 초기값이 그대로 남아있을 경우, target으로 변환이 불가능한 경우이므로 0을 return 한다.

***
<br><br>

### ✔ 재귀를 이용한 DFS 풀이

```c++
#include <string>
#include <vector>
using namespace std;

int min_depth = 10000;
void dfs(string& b, string& t, vector<string>& w, int depth, vector<bool> visited)
{
    if( b == t &&  depth < min_depth) min_depth = depth;
    if(depth == w.size()) return;
    
    for(int i=0; i<w.size(); i++)
    {
        int count = 0;
        if(b == w[i] || visited[i] == true) continue;
        
        for(int j=0; j<b.size(); j++)
            if (b[j] != w[i][j]) count++;
        
        if( count == 1)
        {
            visited[i]= true;
            dfs(w[i],t,w,depth+1,visited);
        }
    }
}

int solution(string begin, string target, vector<string> words) {
    vector<bool> visited(words.size());
    dfs(begin,target,words,0,visited);
    
    return min_depth == 10000? 0 : min_depth;
}
```

--- 
<br>

#### 👍 핵심 코드 
```c++
for(int j=0; j<b.size(); j++)
    if (b[j] != w[i][j]) count++;

if( count == 1)
{
    visited[i]= true;
    dfs(w[i],t,w,depth+1,visited);
}
```
└ 미방문한 값 중에 string의 char를 비교하여 같은지 다른지를 체크한 뒤, `단 한글자만 다를 경우` 해당 string에 방문하고 깊이를 1 증가시킨다. 

```c++
    if( b == t &&  depth < min_depth) min_depth = depth;
    if(depth == w.size()) return;
```
└ dfs의 종료조건 및 최소깊이를 구하는 부분. 이번에 방문한 `string이 target과 동일한지 확인`하고, `현재 깊이가 이미 기록된 최소깊이보다 작을 경우`에 최소깊이를 갱신한다. 두번째 if는 target이 끝까지 변환 불가능할 경우 dfs를 탈출하는 코드이다.

--- 
<br>


  <small style ="color:gray;">(post-code: programmers_lv2_04) </small> 
 {: .text-right}

[TOP](#){: .btn .btn--warning} 
{: .text-right}