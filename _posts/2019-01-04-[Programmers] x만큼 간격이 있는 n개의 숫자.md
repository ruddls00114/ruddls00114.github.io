---
layout:     post
title:      "[Programmers] x만큼 간격이 있는 n개의 숫자"
subtitle:   "프로그래머스 level1"
date:       2019-01-14 17:13:00
author:     "kyoungIn"
header-type: "text"
tags:
    - Algorithm
    - Programmers
---
# x만큼 간격이 있는 n개의 숫자

문제 링크 : (https://programmers.co.kr/learn/courses/30/lessons/12954)

## 풀이

```cpp
#include <string>
#include <vector>

using namespace std;

vector<long long> solution(int x, int n) {
    vector<long long> answer;
    int sum =x;
    for(int i=0;i<n;i++){
        answer.push_back(sum);
        sum+=x;
    }
    return answer;
}
```

