---
layout:     post
title:      "[Programmers] 가운데 글자 가져오기"
subtitle:   "프로그래머스 level1"
date:       2019-01-14 16:46:00
author:     "kyoungIn"
header-type: "text"
tags:
    - Algorithm
    - Programmers
---
# 가운데 글자 가져오기

문제 링크 : (https://programmers.co.kr/learn/courses/30/lessons/12903)

## 풀이

```cpp
#include <string>
#include <vector>
#include <iostream>
using namespace std;

string solution(string s) {
    string answer = "";
    int slen = (int)s.length();
    int center = slen/2;
    if(slen%2){ //홀수
        answer = s[center];
    }
    else{   //짝수
        answer =s[center-1];
        answer +=s[center];
    }
    return answer;
}
```

