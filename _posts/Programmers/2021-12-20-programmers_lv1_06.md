---
title:  "[C++풀이] [1차]비밀지도"
excerpt: "프로그래머스 Level 1"

categories:
  - programmers
tags:
  - [Coding Test,C++]

date: 2021-12-17

breadcrumb: true
---


##  < [1차] 비밀지도 >

 - 난이도 : 1 
 - 언어: c++ 


#### [📂문제 보기](https://programmers.co.kr/learn/courses/30/lessons/17681?language=cpp) 

***
###  🔶 `나의 풀이법`

```c++

//string을 이용한 풀이

#include <string>
#include <vector>

using namespace std;

string itobin(int n,int num)
{
    string result;
    int rest = 0;
    for(int i=num; i>=1; i =i/2)
        result += to_string( i%2);
    
    while(result.size() != n)
        result += "0";
    
    return result;
}

vector<string> solution(int n, vector<int> arr1, vector<int> arr2) {
    vector<string> answer;
    
    string bin1,bin2;
    for(int i=0; i<n; i++)
    {
        string result;
        bin1 = itobin(n,arr1[i]);
        bin2 = itobin(n,arr2[i]);
        
        for(int j=n-1; j>-1;j--)
        {
            if(bin1[j]=='1' || bin2[j]=='1')
                result += "#";
            else 
                result += " ";
        }
        answer.push_back(result);
    }
    return answer;
}
```
