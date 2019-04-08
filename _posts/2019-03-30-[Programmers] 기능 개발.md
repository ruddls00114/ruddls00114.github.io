---
layout:     post
title:      "[Programmers] 기능 개발"
subtitle:   "프로그래머스 level2"
date:       2019-03-30 19:22:00
author:     "kyoungIn"
header-type: "text"
tags:
    - Algorithm
    - Programmers
---
# 기능 개발

문제 링크 : (https://programmers.co.kr/learn/courses/30/lessons/42586)

## 풀이



```cpp
#include <string>
#include <vector>
#include <iostream>
#include <math.h>
using namespace std;

vector<int> solution(vector<int> progresses, vector<int> speeds) {
    vector<int> answers,days;
    int len= progresses.size();
    int val,day;
    for(int i=0;i<len;i++){
        val=100 - progresses[i];
        day = ceil((double)val/speeds[i]);
        cout << day<<endl;
        days.push_back(day);
    }
    for(int i=0;i<len;i++){
        if(i==0){ answers.push_back(1); continue;}
        if (days[i-1]  >= days[i]){
            days[i]=days[i-1];
            ++answers[answers.size()-1];
        }
        else{
            answers.push_back(1);
        }
    }
    return answers;
}
```

