---
layout:     post
title:      "[Programmers] 수박수박수박수박수박수?"
subtitle:   "프로그래머스 level1"
date:       2019-01-04 18:49:00
author:     "kyoungIn"
header-type: "text"
tags:
    - Algorithm
    - Programmers
---
# 수박수박수박수박수박수? 

문제 링크 : [수박수박수박수박수박수?](https://programmers.co.kr/learn/courses/30/lessons/12922)

## 풀이

```cpp
#include <string>
#include <vector>

using namespace std;

string solution(int n) {
    string answer = "";
    if(n==1){
        answer="수";
        return answer;
    }
    for(int i=0;i<n/2;i++)
        answer +="수박";
    if(n%2)
        answer+="수";
    return answer;
}
```

