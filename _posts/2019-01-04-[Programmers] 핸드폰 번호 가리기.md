---
layout:     post
title:      "[Programmers] 핸드폰 번호 가리기"
subtitle:   "프로그래머스 level1"
date:       2019-01-14 17:13:00
author:     "kyoungIn"
header-type: "text"
tags:
    - Algorithm
    - Programmers
---
# 핸드폰 번호 가리기

문제 링크 : (https://programmers.co.kr/learn/courses/30/lessons/12948)

## 풀이

```cpp
#include <string>
#include <vector>

using namespace std;

string solution(string phone_number) {
    string answer = "";
    for(int i=0;i<phone_number.length()-4;i++){
        answer +='*';
    }
    for(int i=phone_number.length()-4;i<phone_number.length();i++){
        answer +=phone_number[i];
    }
    return answer;
}
```

