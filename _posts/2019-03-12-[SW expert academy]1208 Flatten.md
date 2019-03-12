---
layout:     post
title:      "[SW expert academy]1208 Flatten"
subtitle:   ""
date:       2019-03-12 12:55:00
author:     "kyoungIn"
header-type: "text"
tags:
    - Algorithm
    - SW expert
---


# 1208.[S/W 문제해결 기본] 1일차 - [Flatten](https://www.swexpertacademy.com/main/talk/solvingClub/problemView.do?solveclubId=AV6kld8aisgDFASb&contestProbId=AV139KOaABgCFAYh&probBoxId=AV6kld8aiskDFASb&type=PROBLEM&problemBoxTitle=%EC%82%BC%EC%84%B1%EC%8B%9C%ED%97%98%EB%8C%80%EB%B9%84+%EA%B8%B0%EB%B3%B8%EB%AC%B8%EC%A0%9C%EB%AA%A8%EC%9D%8C%28%EB%82%9C%EC%9D%B4%EB%8F%84+1~3%29&problemBoxCnt=15)

### 풀이 

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main(){
    for(int idx=1;idx<=10;idx++){
        int dump;
        cin >> dump;
        vector<int> v(101,0);
        for(int i=1;i<101;i++){
            int high; cin >> high;
            v[high]++;
        }
        int h=100,l=1;
        while(dump>0){
            for(int i=h;i>0;i--){
                if(v[i]==0) continue;
                else{
                    v[i]-=1;
                    v[i-1]+=1;
                    h= i;
                    break;
                }
            }
            for(int i=l;i<=100;i++){
                if(v[i]==0) continue;
                else {
                    v[i]-=1;
                    v[i+1]+=1;
                    l= i;
                    break;
                }
            }
            dump--;
        }
        
        for(int i=100;i>0;i--){
            if(v[i]==0) continue;
            else{
                h= i;
                break;
            }
        }
        for(int i=1;i<=100;i++){
            if(v[i]==0) continue;
            else {
                l= i;
                break;
            }
        }
        cout <<'#' << idx << ' ' <<h-l << '\n';

    }
}

```


