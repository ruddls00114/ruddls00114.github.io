---
layout:     post
title:      "[Programmers] "프린터"
subtitle:   "프로그래머스 level2"
date:       2019-03-30 20:22:00
author:     "kyoungIn"
header-type: "text"
tags:
    - Algorithm
    - Programmers
---
# 프린터

문제 링크 : (https://programmers.co.kr/learn/courses/30/lessons/42587)

## 풀이



```cpp
#include <string>
#include <vector>
#include <iostream>
#include <utility>
#include <algorithm>
#include <functional>
using namespace std;
#define p pair<int,int>
int solution(vector<int> priorities, int location) {
    int answer = 0,len = priorities.size();
    vector<p> data(len);
    for(int i=0;i<len;i++)
        data[i]=p(priorities[i],i);
     sort(priorities.begin(),priorities.end(),greater<int>());
    int i=0;
   while(1){
        if(i==data.size())
            i=0;
        int val= data[i].first;
        int idx= data[i].second;
        if(val==priorities[0]){
           priorities.erase(priorities.begin());
           data.erase(data.begin()+i);
            cout <<data.size() <<endl;
            i--;
           ++answer;
           if(idx==location)
               break;
       }
        i++;
   }
    return answer;
}
```

