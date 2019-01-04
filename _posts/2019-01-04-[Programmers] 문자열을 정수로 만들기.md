---
layout:     post
title:      "[Programmers] 문자열을 정수로 만들기"
subtitle:   "프로그래머스 level1"
date:       2019-01-04 19:30:00
author:     "kyoungIn"
header-type: "text"
tags:
    - Algorithm
    - Programmers
---
# 문자열을 정수로 만들기

문제 링크 :[](https://programmers.co.kr/learn/courses/30/lessons/12925)

## 풀이

```cpp
#include <string>
#include <vector>
#include <math.h>
using namespace std;

int solution(string s) {
    int answer = 0;
    int sign = 1,start=0,val;
    if(s[0]=='-'){
        sign = -1;
        start =1;
    }
    else if(s[0]=='+'){
        sign = 1;
        start =1;
    }
    else{}
    val=(int)s.length() - 1;
    for(int i=start;i<s.length();i++){
        answer +=(s[i]-48)*pow(10,val-i);
    }
    answer *= sign ;
    return answer;
}
```

