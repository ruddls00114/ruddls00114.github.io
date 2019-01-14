---
layout:     post
title:      "[Programmers] 완주하지 못한 선수"
subtitle:   "프로그래머스 level1"
date:       2019-01-14 16:26:00
author:     "kyoungIn"
header-type: "text"
tags:
    - Algorithm
    - Programmers
---
# 완주하지 못한 선수 

문제 링크 : (https://programmers.co.kr/learn/courses/30/lessons/42576)

## 풀이

```cpp
#include <string>
#include <vector>
#include <iostream>
#include <algorithm>
using namespace std;

string solution(vector<string> participant, vector<string> completion) {
    int csize =(int)completion.size();
    int psize =(int)participant.size();
    
    sort(participant.begin(),participant.end());
    sort(completion.begin(),completion.end());
    
    while(1){
        if(participant[--psize] == completion[--csize])
            continue;
        else{
            return participant[psize];
        }
    }
}
```

