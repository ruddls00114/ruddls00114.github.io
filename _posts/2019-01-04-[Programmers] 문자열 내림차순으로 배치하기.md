---
layout:     post
title:      "[Programmers] 문자열 내림차순으로 배치하기"
subtitle:   "프로그래머스 level1"
date:       2019-01-14 18:13:00
author:     "kyoungIn"
header-type: "text"
tags:
    - Algorithm
    - Programmers
---
# 문자열 내림차순으로 배치하기

문제 링크 : (https://programmers.co.kr/learn/courses/30/lessons/12917#)

## 풀이

```cpp
#include <string>
#include <vector>
#include <algorithm>
#include <iostream>
using namespace std;

string solution(string s) {
    string answer = "";
    sort(s.begin(),s.end());
    for(int i=s.length()-1;i>=0;i--){
        answer +=s[i];
    }
    cout << answer;
    return answer;
}
```

