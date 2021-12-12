---
title:  "[C++] 숫자 문자열과 영단어"
excerpt: "프로그래머스 Level 1"

categories:
  - programmers
tags:
  - [Coding Test,C++]

date: 2021-12-10

breadcrumb: true
---


## 숫자 문자열과 영단어

### 레벨 : 1
### 언어: c++ 

#### [📂문제 보기](https://programmers.co.kr/learn/courses/30/lessons/81301)

***

```c++
#include <string>
#include <vector>

using namespace std;

vector<string> number = {"zero","one","two","three","four","five","six","seven","eight","nine"};

string search(string s)
{
    string result = "-1";
    for(int i=0; i<number.size(); i++)
    {
        if(s == number.at(i))
            result = to_string(i);
    }
    return result;
}


int solution(string s) {
    int answer = 0;
    
    string result = "";
    
    string tmp = "";
    for(char& c : s)
    {
        if(c >= '0' && c<= '9') result+= c;
        
        else 
        {
            tmp += c;
            string t = search(tmp);
            if(t != "-1")
            {
                result.append(t);
                tmp.clear();
            }
        }
    }
    answer = stoi(result);
    return answer;
}
```


