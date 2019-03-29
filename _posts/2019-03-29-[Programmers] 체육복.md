---
layout:     post
title:      "[Programmers] 체육복"
subtitle:   "프로그래머스 level1"
date:       2019-03-29 04:42:00
author:     "kyoungIn"
header-type: "text"
tags:
    - Algorithm
    - Programmers
---
# 체육복

문제 링크 : (https://programmers.co.kr/learn/courses/30/lessons/42862)

## 풀이

문제에 처리하지못한 제한사항이 있어서 고생했다 ,,

```cpp
#include <string>
#include <vector>
#include <iostream>
#include <algorithm>
using namespace std;

int solution(int n, vector<int> lost, vector<int> reserve) {
    sort(lost.begin(),lost.end());
    sort(reserve.begin(),reserve.end());
    
    int arr[41]={0};
    for(int i=0;i<lost.size();i++)
        arr[lost[i]]=-1;
    int answer = n-lost.size();
    int len=reserve.size();
    for(int i=0;i<len;i++){
        if(arr[reserve[i]]==-1){
            ++answer;
            arr[reserve[i]]=0;
            reserve.erase(reserve.begin()+i);
            --i;
            --len;
        }       
    }

    for(int i=0;i<reserve.size();i++){
        int val= reserve[i];
        if(val-1>0 && arr[val-1]==-1){
            ++answer;
            arr[val-1]=0;
        }
        else if(val+1<=30 && arr[val+1]==-1){
            ++answer;
            arr[val+1]=0;
        }
    
    }
    return answer;
}
```

