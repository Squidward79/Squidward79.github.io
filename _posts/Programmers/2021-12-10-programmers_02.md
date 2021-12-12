---
title:  "[PROGRAMMERS] 신규 아이디 추천 C++"
excerpt: "2021 KAKAO BLIND RECRUITMENT - Level 1 "

categories:
  - coding test
tags:
  - [Coding Test,Level1,C++]

date: 2021-12-10

breadcrumb: true
---


## 신규 아이디 추천

### 레벨 : 1
### 언어: c++ 

#### [📂문제 보기](https://programmers.co.kr/learn/courses/30/lessons/72410)

***



```c++
#include <string>
#include <vector>

using namespace std;

string solution(string new_id) {
    string answer = new_id;
    
    //1단계 : 대문자를 소문자로 변환
    //문자 1개를 대문자,소문자로 바꿔주는 toupper(char) , tolower(char)를 사용
    //string 전체를 바꿔주기 위해 foreach로 전체를 돌려줌
    for(auto &c : answer)
        c = tolower(c);
    
    //2단계 : 특수문자 제거하기
    //string.erase(n번째문자부터 , 몇개의 문자를 삭제할지) 함수를 이용하여 특수문자 삭제
    string ban_char = "~!@#$%^&*()=+[{}]:?,<>/";
    for(int i=0; i<answer.size(); i++)
    {
        for(int j=0; j<ban_char.size(); j++)
        {
            if(answer.at(i) == ban_char.at(j))
            {
                answer.erase(i,1);
                i--;
                break;
            }
        }
    }
    
    //3단계 : 연속 마침표를 하나로 치환
    //두개를 비교하여 연속 .이면 하나 지움
    for(int i=0; i<answer.size()-1; i++)
    {
       if (answer.at(i) == '.' && answer.at(i+1)=='.')
       {
           answer.erase(i,1);
           i--;
       }
    }
    
    //4단계 : 처음이나 끝이 .이면 제거
    if(answer.front() == '.') answer.erase(0,1);
    if(answer.back() =='.') answer.pop_back();
    
    //5단계 : 빈 문자열이면 a 대입
    if(answer.empty()) answer = "a";
    
    //6단계 : 16자 이상이면 첫 15개문자만 표시
    //이후 맨 끝이 .이면 삭제
    if(answer.size() >= 16)
        answer.erase(15); //15개 이후 문자를 제거
    if(answer.back() == '.') answer.pop_back();

    
    //7단계 : 길이가 2 이하면 마지막 문자를 3이 될때까지 붙임
    if(answer.size() <= 2)
        answer.resize(3,answer.back());
    
    return answer;
}
```


