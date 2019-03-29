---
layout:     post
title:      "[Programmers] 문자열 내 마음대로 정렬하기"
subtitle:   "프로그래머스 level1"
date:       2019-03-29 10:33:00
author:     "kyoungIn"
header-type: "text"
tags:
    - Algorithm
    - Programmers
---
# 문자열 내 마음대로 정렬하기

문제 링크 : (https://programmers.co.kr/learn/courses/30/lessons/12915)

## 풀이

```cpp
#include <string>
#include <vector>
#include <algorithm>
#include <iostream>
using namespace std;
int val;
bool comp(string a,string b){
    if(a[val]==b[val])
       return a<b;
    return a[val]<b[val];
}
vector<string> solution(vector<string> strings, int n) {
    vector<string> answer;
    val=n;
  
    sort(strings.begin(),strings.end(),comp);
    
    for(int i=0;i<strings.size();i++)
        cout << strings[i] << ' ';
    return strings;
}

```

