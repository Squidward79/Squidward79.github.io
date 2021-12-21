---
title:  "[C++풀이] [1차]다트 게임"
excerpt: "프로그래머스 Level 1"

categories:
  - programmers
tags:
  - [Coding Test,C++]

date: 2021-12-20

breadcrumb: true
---

<div class="notice--warning" markdown=1>
 <span>📄 난이도 : 1      </span> 
 <span>📄 언어 : C++  </span> 
  {: .text-left}
 </div>
 
 [📂문제 보기](https://programmers.co.kr/learn/courses/30/lessons/17682?language=cpp) 

***
##  🔶 풀이법
처음 접근은, 다트 하나의 기록인 숫자/영단어/특수문자 를 동시에 잘라와서 처리하는 것을 생각했다. 
숫자가 10이 존재할수도 있기 때문에, 공통적인 규칙을 찾기 어려워서 한글자씩 읽어 케이스 바이 케이스로 처리하는쪽으로 선회했다.
기본적으로 string은 한글자씩 읽어서 처리하는걸 먼저 생각해봐야겠다.   

숫자 부분을 int형으로 바꾸기 위해 `stoi()`함수를 썼는데, 다른 풀이에서는 `dartResult[i] - '0'`으로 숫자를 구할 수도 있다는걸 배웠다.

### ✔ 풀이

```c++
#include <string>
#include <vector>

using namespace std;

int solution(string dartResult) {
    int answer = 0;
    string s;
    vector<int> result;
    for(int i=0; i<dartResult.size(); i++)
    {
        if(dartResult[i] >= '0' && dartResult[i] <= '9')
            s+=dartResult[i];

        else if(dartResult[i] >= 'A' && dartResult[i] <= 'Z')
        {
            int num = stoi(s);
            if(dartResult[i] == 'D')
                num *= num;
            else if(dartResult[i] == 'T')
                num *= num * num;
            
            result.push_back(num);
            s = "";
        }
        else if(dartResult[i] == '#')
            result[result.size()-1] *= -1;
            //result.size()-1 은 result.back() 과 같다!

        else if( dartResult[i] == '*')
        {
            result[result.size()-1] *= 2;
            if(result.size() > 1) result[result.size()-2] *=2;
        }
    }
    
    for(int i : result)
        answer += i;
    
    return answer;
}

```
--- 
<br>


  <small style ="color:gray;">(문제번호: 06) </small> 
 {: .text-right}

[TOP](#){: .btn .btn--warning} 
{: .text-right}