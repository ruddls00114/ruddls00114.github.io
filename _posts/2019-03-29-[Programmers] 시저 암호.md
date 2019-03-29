---
layout:     post
title:      "[Programmers] 시저 암호"
subtitle:   "프로그래머스 level1"
date:       2019-03-29 11:44:00
author:     "kyoungIn"
header-type: "text"
tags:
    - Algorithm
    - Programmers
---
# 시저 암호

문제 링크 : (https://programmers.co.kr/learn/courses/30/lessons/12926)

## 풀이

```cpp
#include <string>
#include <vector>
#include <iostream>
using namespace std;

string solution(string s, int n) {
    string answer = "";
    int flag,data; 
    for(int i=0;i<s.length();i++){
        flag=0,data=0;
        if(s[i]==' ')continue;
        if(s[i]>='a' && s[i]<='z') flag=1;//소문자
        data=s[i]+n;
        if(flag == 1 && data>'z')
            data-=26;
        else if(flag == 0 && data >'Z')
            data-=26;
        s[i]=data;
    }
    return s;
}
```

