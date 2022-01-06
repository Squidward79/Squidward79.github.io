---
title:  "[C++풀이] 카카오프렌즈 컬러링북"
excerpt: "프로그래머스 Level 2 - DFS/BFS"

categories:
  - programmers
tags:
  - [Coding Test,C++]

breadcrumb: true

---

<div class="notice--warning" markdown=1>
 <span>📄 난이도 : 🟠🟠      </span>   
 <span>📄 언어 : C++  </span> 

 </div>
 


 [📂문제 보기](https://programmers.co.kr/learn/courses/30/lessons/1829?language=cpp) 

##  🔶 풀이 과정 
DFS로 풀면 되겠다는 판단이 선 이후부터는 꽤 수월하게 작성했다. 조건이 상하좌우 4개뿐이라 4개의 if문을 사용했었다. 풀어낸 이후 다른 풀이를 참고하니 4개의 칸을 방문하기 위해서 필터처럼 값을 미리 지정한 뒤 배열의 index를 찾아가게 하는 코드가 인상깊어서 해당 코드를 적용하여 다시 풀었다. 조건이 4개라서 수행시간에 큰 차이는 없었지만, 조건이 더 늘어나거나 복잡해질 경우 if문의 나열보다는 이같은 방법이 코드를 깔끔하게 작성하는데 도움이 될 것 같다. 

테스트케이스는 쉽게 통과했으나 채점과정에서 계속 실패해서 골머리를 앓았는데 dfs내부 조건문에 0을 포함시키지 않아서였다..😥 조건문 작성시 조금 더 주의해서 봐야겠다.

***
<br><br>

### ✔ 재귀를 이용한 DFS 풀이

```c++
#include <vector>

using namespace std;

const int fx[4] = {0,0,1,-1};
const int fy[4] = {1,-1,0,0};
int dfs(int c, int r, int& m, int& n, vector<vector<int>>& p, vector<vector<bool>>& v)
{
    if(v[c][r] == true || p[c][r] == 0) return 0;
    
    v[c][r] = true;
    int cur_size = 1;
    
    for(int i=0; i<4; i++)
    {
        int nc = c + fx[i];
        int nr = r + fy[i];
        if(nc < m && nc >= 0 && nr <n && nr >=0 && p[c][r] == p[nc][nr])
            cur_size += dfs(nc,nr,m,n,p,v);
    }

    return cur_size;
}

// 전역 변수를 정의할 경우 함수 내에 초기화 코드를 꼭 작성해주세요.
vector<int> solution(int m, int n, vector<vector<int>> picture) {
    int number_of_area = 0;
    int max_size_of_one_area = 0;
    vector<vector<bool>> visited(m,vector<bool>(n,false)); 

    for(int i=0; i<m; i++)
    {
        for(int j=0; j<n; j++)
        {
            int cur_size = dfs(i,j,m,n,picture,visited);
            if(cur_size > max_size_of_one_area) 
                max_size_of_one_area = cur_size;
            if(cur_size != 0) 
                number_of_area++;
        }
    }

    vector<int> answer(2);
    answer[0] = number_of_area;
    answer[1] = max_size_of_one_area;
    return answer;
}
```

--- 
<br>

#### 👍 핵심 코드 
```c++
int cur_size = dfs(i,j,m,n,picture,visited);
if(cur_size > max_size_of_one_area) 
    max_size_of_one_area = cur_size;
if(cur_size != 0) 
    number_of_area++;
```
└ dfs함수는 방문한 노드의 갯수를 리턴하는데, 이게 곧 하나의 색상 영역을 의미한다. 하나의 색상영역의 사이즈를 체크하고, 최대값이라면 갱신한다. 또 0이 아닐경우 즉 하나라도 유요한 색상영역이 존재한다면 영역의 갯수를 증가시킨다.  

dfs 함수 내에서 방문했다면 즉시 리턴하기 때문에 전체 배열을 다 for문으로 돌려도 이미 방문한 노드에서는 dfs를 수행하지 않는다.
  

```c++
if(v[c][r] == true || p[c][r] == 0) return 0;
```
└ dfs의 종료조건. 배열의 색상값이 0이거나 이미 방문한 노드라면 건너뛴다.

```c++
for(int i=0; i<4; i++)
{
    int nc = c + fx[i];
    int nr = r + fy[i];
    if(nc < m && nc >= 0 && nr <n && nr >=0 && p[c][r] == p[nc][nr])
        cur_size += dfs(nc,nr,m,n,p,v);
}

    
return cur_size;
```
└ dfs에서는 미리 작성해둔 4방향에 접근하기 위한 fx,fy 배열에 현재 index값을 더한다. 이후 네 방향에 대한 예외조건을 if문으로 걸고 예외가 아니라면 그 지점에서 다시 dfs를 수행한다.

하나의 dfs로 파생되어 방문한 노드를 방문할 때마다 size값을 1씩 증가시킨 후 리턴하여 최종적으로 방문한 노드의 갯수를 리턴하도록 하였다.

--- 
<br>


  <small style ="color:gray;">(post-code: programmers_lv2_05) </small> 
 {: .text-right}

[TOP](#){: .btn .btn--warning} 
{: .text-right}