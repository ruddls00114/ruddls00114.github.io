---
layout:     post
title:      "[Programmers] 나누어 떨어지는 숫자 배열"
subtitle:   "프로그래머스 level1"
date:       2019-01-14 17:13:00
author:     "kyoungIn"
header-type: "text"
tags:
    - Algorithm
    - Programmers
---
# 나누어 떨어지는 숫자 배열

문제 링크 : (https://programmers.co.kr/learn/courses/30/lessons/12910)

## 풀이

```cpp
#include <string>
#include <vector>
#include <algorithm>
using namespace std;

vector<int> solution(vector<int> arr, int divisor) {
    vector<int> answer;
    int i, alen =(int)arr.size();
    for(i=0;i<alen;i++){
        if(arr[i]%divisor == 0)
            answer.push_back(arr[i]);
    }
    
    if(answer.size() == 0)
        answer.push_back(-1);
    else
        sort(answer.begin(),answer.end());
    
    return answer;
}
```

