---
layout:     post
title:      "[Programmers] "다리를 지나는 트럭"
subtitle:   "프로그래머스 level2"
date:       2019-03-30 21:22:00
author:     "kyoungIn"
header-type: "text"
tags:
    - Algorithm
    - Programmers
---
# 다리를 지나는 트럭

문제 링크 : (https://programmers.co.kr/learn/courses/30/lessons/42583)

## 풀이



```cpp
#include <string>
#include <vector>
#include <iostream>
#include <queue>
#include <utility>
using namespace std;
#define p pair<int,int>
int solution(int bridge_length, int weight, vector<int> truck_weights) {
    int answer = 0,len=truck_weights.size();
    vector<p> truck;
    for(int i=0;i<len;i++)
        truck.push_back(p(truck_weights[i],0)); // 트럭 시간,
    queue<p> q;
    int w=0,i=0,pop_cnt=0;
    while(1){
        ++answer;
        if(q.front().second+bridge_length==answer){
            w-=q.front().first;
            cout <<"pop truck:"<< q.front().first <<"  time:"<<answer<<endl;
            q.pop();
            pop_cnt++;
        }
        if(i!=len &&q.size()<bridge_length && w+truck[i].first <=weight){//올라갈수있어
            w+=truck[i].first;
            q.push(p(truck[i].first,answer));
            truck[i].second=answer;
            // cout <<"push truck:"<< truck[i].first <<"  time:"<<answer<<endl;
            i++;
        }
        
        if(pop_cnt==len)
            break;
   }
    return answer;
}
```

