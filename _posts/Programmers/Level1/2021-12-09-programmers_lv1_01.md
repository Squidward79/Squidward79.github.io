---
title:  "[C++] 로또의 최고 순위와 최저 순위"
excerpt: "프로그래머스 Level 1"

categories:
  - programmers
tags:
  - [Coding Test,C++]

date: 2021-12-09

breadcrumb: true
---

<small></small>

## < 로또의 최고 순위와 최저 순위 >

### 난이도 : 1   
### 언어: c++ 

#### [📂문제 보기](https://programmers.co.kr/learn/courses/30/lessons/77484)

***



```c++
#include <string>
#include <vector>

using namespace std;

vector<int> solution(vector<int> lottos, vector<int> win_nums) {
    vector<int> answer;
        
    int zero_count = 0;
    int correct = 0;

    int rank[7] = {6,6,5,4,3,2,1};


    for (int i = 0; i < lottos.size(); i++)
    {
        if(lottos[i] == 0)
            zero_count++;
        
        for(int j=0; j<lottos.size(); j++)
        {
            if(lottos[i] == win_nums[j])
                correct++;
        }
    }

    int low = rank[correct];
    int high = rank[correct + zero_count];

    answer.push_back(high);
    answer.push_back(low);

    return answer;
}

/*
0이 아닌 일치하는 갯수가 최저순위,
0이 전부 당첨일 경우가 최고순위.

*/
```


