---
layout:     post
title:      "[Programmers] 전화번호 목록"
subtitle:   "프로그래머스 level2"
date:       2019-03-30 16:42:00
author:     "kyoungIn"
header-type: "text"
tags:
    - Algorithm
    - Programmers
---
# 전화번호 목록

문제 링크 : (https://programmers.co.kr/learn/courses/30/lessons/42577)

## 풀이

문자열 처리 함수를 몇개 외워두는 편이 좋을것같다!

```cpp
#include <string.h>
#include <vector>
#include <iostream>
#include <algorithm>
using namespace std;
bool comp(string a,string b){
    return a.length() < b.length();
}
bool solution(vector<string> phone_book) {
    bool answer = true;
    sort(phone_book.begin(),phone_book.end(),comp);
    for(int i=0;i<phone_book.size();i++)
        cout << phone_book[i]<< ' ';
    
    for(int i=0;i<phone_book.size()-1;i++){
        for(int j=i+1;j<phone_book.size();j++){
            string temp=phone_book[j].substr(0,phone_book[i].length());
            if(temp==phone_book[i])
                return false;
        }
    }
    return answer;
}
```

