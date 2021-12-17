---
title:  "[C++] 두 개 뽑아서 더하기"
excerpt: "프로그래머스 Level 1"

categories:
  - programmers
tags:
  - [Coding Test,C++]

date: 2021-12-17

breadcrumb: true
---

## < 두 개 뽑아서 더하기 >

### 레벨 : 1
### 언어: c++ 

#### [📂문제 링크](https://programmers.co.kr/learn/courses/30/lessons/68644)

<details>
<summary>문제접기/펼치기 버튼</summary>
<div markdown="1">
<br>

## 두 개 뽑아서 더하기

### 문제 설명
---
정수 배열 numbers가 주어집니다. numbers에서 서로 다른 인덱스에 있는 두 개의 수를 뽑아 더해서 만들 수 있는 모든 수를 배열에 오름차순으로 담아 return 하도록 solution 함수를 완성해주세요.

### 제한사항
---
numbers의 길이는 2 이상 100 이하입니다.
numbers의 모든 수는 0 이상 100 이하입니다.

---
### 입출력 예

| numbers     | result        |
| ----------- | ------------- |
| [2,1,3,4,1] | [2,3,4,5,6,7] |
| [5,0,2,7]   | [2,5,7,9,12]  |

---
### 입출력 예 설명

 - 입출력 예 #1

    2 = 1 + 1 입니다. (1이 numbers에 두 개 있습니다.)

    3 = 2 + 1 입니다.

    4 = 1 + 3 입니다.

    5 = 1 + 4 = 2 + 3 입니다.

    6 = 2 + 4 입니다.

    7 = 3 + 4 입니다.

    따라서 `[2,3,4,5,6,7]` 을 return 해야 합니다.

- 입출력 예 #2

    2 = 0 + 2 입니다.

    5 = 5 + 0 입니다.

    7 = 0 + 7 = 5 + 2 입니다.

    9 = 2 + 7 입니다.

    12 = 5 + 7 입니다.

    따라서 `[2,5,7,9,12]` 를 return 해야 합니다.
</div>
</details>

***
###  🔶 `나의 풀이법`

처음에는 순열조합을 이용해서 풀려고 했지만, 몇가지 테스트케이스에서 시간초과가 발생하는 문제가 있어서, 단순하게 생각하는 방식으로 돌아와 2중for문으로 풀었다.

```c++
#include <string>
#include <vector>
#include <algorithm>

using namespace std;

vector<int> solution(vector<int> numbers) {
    vector<int> answer;

    int sum;
    for(int i=0; i<numbers.size()-1; i++)
    {
        for(int j=i+1; j<numbers.size(); j++)
        {
            //두 수를 더한 수가 answer에 없을 경우에만 answer에 추가
            sum = numbers[i] + numbers[j];
            if(answer.end() == find(answer.begin(),answer.end(),sum))
                answer.push_back(sum);
        }
    }
    sort(answer.begin(),answer.end());

    return answer;
}

```
<br>
다른사람의 풀이를 봤더니, set을 이용하여 아주 깔끔하게 풀어낸 것이 있었다.<br>

`자동정렬`, `중복 비허용` 관련 문제는 set을 이용해도 아주 좋을듯!!


<br>