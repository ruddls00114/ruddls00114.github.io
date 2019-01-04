---
layout:     post
title:      "[Programmers] 서울에서 김서방 찾기"
subtitle:   "프로그래머스 level1"
date:       2019-01-04 19:49:00
author:     "kyoungIn"
header-type: "text"
tags:
    - Algorithm
    - Programmers
---
# 서울에서 김서방 찾기

문제 링크 : (https://programmers.co.kr/learn/courses/30/lessons/12919)

## 풀이

```cpp
#include <string>
#include <vector>

using namespace std;

string solution(vector<string> seoul) {
    string answer = "김서방은 ";
    for(int i=0;i<(int)seoul.size();i++){
        if(seoul[i]=="Kim"){
            answer +=to_string(i);
            }
    }
    return answer+"에 있다";
}
```

