---
layout:     post
title:      "[Programmers] 문자열 내 p와 y의 개수"
subtitle:   "프로그래머스 level1"
date:       2019-01-14 17:13:00
author:     "kyoungIn"
header-type: "text"
tags:
    - Algorithm
    - Programmers
---
# 문자열 내 p와 y의 개수

문제 링크 : (https://programmers.co.kr/learn/courses/30/lessons/12916)

## 풀이

```cpp
#include <string>
#include <iostream>
using namespace std;

bool solution(string s)
{
    bool answer = true;
    int pcnt =0,ycnt =0;
    for(int i=0;i<(int)s.length();i++){
        if(s[i]=='p' || s[i]=='P')
            pcnt ++;
        else if(s[i]=='y' || s[i]=='Y')
            ycnt ++;
        else{}
    }
    if(pcnt == ycnt)ㄴ
        return true;
    else
        return false;
}
```

