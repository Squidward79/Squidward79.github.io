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


 | 난이도 | 언어 |
 | :------: | :----: |
 | 1      | C++  |


#### [📂문제 보기](https://programmers.co.kr/learn/courses/30/lessons/17681?language=cpp) 

***
##  🔶 풀이법

`비트연산`을 이용해서 풀수 있겠구나 생각은 했지만 어떻게 다루는지를 몰라서 처음엔 `string`을 이용하는 쪽으로 방향을 잡고 문제를 풀었다. 일단 풀어낸 후 비트연산 쪽을 다시 학습하여 비트연산으로 한번 더 풀었다! 

### ✔ 비트연산자를 이용한 풀이

```c++
//비트연산자를 이용한 풀이

#include <string>
#include <vector>

using namespace std;

vector<string> solution(int n, vector<int> arr1, vector<int> arr2) {
    vector<string> answer;
    for(int i =0; i<n; i++)
    {
        string result;
        int tmp = arr1[i] | arr2[i];
        for(int j=n-1; j>-1; j--)
        {
            if(tmp >> j & 1)
                result += "#";
            else 
                result += " ";
        }   
        answer.push_back(result);
    }
    return answer;
}
```
--- 
<br>

#### 👍 핵심 코드 

```c++
    int tmp = arr1[i] | arr2[i];
```
1.  입력값 `arr1`과 `arr2`를 or연산(`|`)으로 합치면, 동일 자리의 비트가 0-0이라면 0이, 그 외의 경우 1이 되므로 사실상 문제에서 주어진 두 지도가 `tmp`라는 숫자로 합쳐진 것을 의미한다.

```c++
  if(tmp >> j & 1)
        result += "#";
    else 
        result += " ";
```
2. 그런 다음 for문안에서 `tmp >> j&1` 를 하는데, 가장 왼쪽(`첫번째`) 비트부터 하나씩 1인지 0인지를 체크하기 위해서이다.
3. 예를들어 tmp가 9이고 n이 5라면, 비트로는 `01001`이 된다. 
4. for문으로 처음엔 4개의 비트를 오른쪽으로 shift(`>>`)하여 `0`으로 만들고, and연산(`&`)으로 비트가 1일 때에만 #을 결과값에 추가한다.
5. 이 때  `&1`인 이유는 1이 `00001`이기 때문에, **<u>가장 오른쪽의 비트 1개만</u>** 1인지 체크할 수 있기 때문이다!!


--- 
<br>

### ✔ string을 이용한 풀이

```c++

//string을 이용한 풀이

#include <string>
#include <vector>

using namespace std;

//길이가 n인 2진수를 만드는 함수.
//길이에 맞게 남는 자리에 0을 붙여준다.
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
        
        //입력값을 2진수 형태의 string으로 변환한 후, 역순으로 들어있는
        //정보를 거꾸로 읽어가며 값을 비교하여 결과에 추가하는 방식.
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


