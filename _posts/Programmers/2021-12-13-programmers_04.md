---
title:  "[C++] 실패율"
excerpt: "프로그래머스 Level 1"

categories:
  - programmers
tags:
  - [Coding Test,C++]

date: 2021-12-13

breadcrumb: true
---


## < 실패율 >

### 레벨 : 1
### 언어: c++ 

#### [📂문제 보기](https://programmers.co.kr/learn/courses/30/lessons/42889)

***
###  🔶 나의 풀이법


```c++
#include <string>
#include <vector>

using namespace std;

vector<int> solution(int N, vector<int> stages) {
    
    vector<int> answer;
    
    vector<int> delay(N+1,0); //스테이지별 멈춰있는 인원수
    vector<int> clear(N+1,0); //스테이지별 클리어 인원수
    vector<float> fail(N+1,0); //실패율 저장
    
    //인원을 돌며 delay 와 clear에 저장
    for(int i: stages)
    {
        if(i != N+1)    
            delay[i]++;
        
        for(int j=1; j<i; j++)
            clear[j]++;
    }
    
    //그 후 실패율을 계산, 분모가 0일 경우는 실패율 0
    for(int i=1; i<=N; i++)
    {
        if(delay[i] != 0)
           fail[i] = (float)delay[i]/(float)clear[i];
        else 
            fail[i] = 0;
    }   
    
    //fail 배열을 비교하며 가장 실패율이 높은 배열의 index를 answer에 저장
    //이미 들어간 index는 -1로 처리하여 배제
    for(int i=1; i<=fail.size(); i++)
    {
        int max =  1;
        for(int j=1; j<=N; j++)
        {
            if(fail[max] < fail[j])
                max = j;
        }
        
        if(fail[max] == -1) continue;
        
        answer.push_back(max);
        fail[max] = -1;
    }
    return answer;
}
```
<br>
이렇게 푸는데 이래저래 고민을 많이 하고 풀어낸 다음 다른 풀이를 봤는데..<br>
더 깔끔하고 sort를 이용해서 쉽게 푸는 방법이 있어 가져왔다!

<br>

### 🔶 다른 사람의 풀이
```c++
#include <string>
#include <vector>
#include <algorithm>

using namespace std;

//✅pair를 이용해서 스테이지 위치와 실패율을 동시에 저장한게 핵심인듯!
//fail을 정렬한 후 비교함수를 통해 쭉 뽑아내기..
bool cmp(const pair<double,int>&a, const pair<double,int>&b){
    if(a.first==b.first) return a.second<b.second;
    return a.first>b.first;
}

vector<int> solution(int N, vector<int> stages) {
    vector<int> answer;
    vector<pair<double,int>> fail;

    //ab이용해 1개 스테이지에 대해 delay와 clear를 저장
    for(int i=1;i<=N;i++){
        double a=0,b=0;
        for(int j=0;j<stages.size();j++){
            if(stages[j]==i) a+=1; 
            if(stages[j]>=i) b+=1;
        }
        if(b!=0)
            fail.push_back(make_pair(a/b,i)); //✅실패율을 바로 계산해 저장!!
        else if(b==0) //예외처리
            fail.push_back(make_pair(0,i));
    }

    //소팅한 후 앞부터 쭉 입력.fail은 스테이지에 대응되도록 저장되어있기 때문!
    //it->second로 스테이지 번호에 접근할수 있는게 좋은듯하다.
    //나는 실패율과 번호를 별개로 관리해서 애먹었는데 ㅠ
    sort(fail.begin(),fail.end(),cmp);
    auto it=fail.begin();
    for(it=fail.begin();it!=fail.end();it++)
        answer.push_back(it->second);

    return answer;
}
```


