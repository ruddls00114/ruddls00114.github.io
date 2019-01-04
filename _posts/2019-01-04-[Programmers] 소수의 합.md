---
layout:     post
title:      "[Programmers] 소수의 합"
subtitle:   "프로그래머스 level1"
date:       2019-01-04 19:49:00
author:     "kyoungIn"
header-type: "text"
tags:
    - Algorithm
    - Programmers
---
# 서울에서 김서방 찾기

문제 링크 : (https://programmers.co.kr/learn/courses/30/lessons/14406)

## 풀이

```cpp
#include <vector>
#include <cstring>
#include <math.h>
using namespace std;
bool prime[20000000];
void Prime(int n) {
    memset(prime,true,sizeof(prime)); //초기화 모두 소수
    prime[1]=0;
    int answer = 0;
    for(int i=2;i<sqrt(10000000);i++){
        if(prime[i] ==0)
            continue;
        for(int j=2;j*i<=n;j++){
            prime[i*j]=0;
        }
    }
    
}
long long solution(int N) {
    long long answer = 0;
    Prime(N);
    for(int i=2;i<=N;i++){
        if(prime[i]==true){
            answer+=i;
        }
    }
    return answer;
}
```

