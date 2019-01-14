---
layout:     post
title:      "[Programmers] k번째수"
subtitle:   "프로그래머스 level1"
date:       2019-01-14 16:46:00
author:     "kyoungIn"
header-type: "text"
tags:
    - Algorithm
    - Programmers
---
# k번째수

문제 링크 : (https://programmers.co.kr/learn/courses/30/lessons/42748)

## 풀이

```cpp
#include <string>
#include <vector>
#include <algorithm>
#include <iostream>
using namespace std;

vector<int> solution(vector<int> array, vector<vector<int>> commands) {
    vector<int> answer,val;
    int num =(int)commands.size();
    for(int j=0;j<num;j++){
        val.clear();
    for(int i=commands[j][0]-1 ; i<commands[j][1];i++){
        val.push_back(array[i]);
    }
    sort(val.begin(),val.end());
        cout << commands[j][2]-1;
    answer.push_back(val[commands[j][2]-1]);
    
    } //for j
    return answer;
}
```

