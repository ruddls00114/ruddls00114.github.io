---
layout:     post
title:      "[SWEA]N\-Queen"
subtitle:   "백트래킹, DFS"
date:       2019-03-19 17:30:00
author:     "kyoungIn
header-type: "text"
tags:
    - Algorithm
    - SWEA
---
# N-Queen

## [링크](https://www.swexpertacademy.com/main/talk/solvingClub/problemView.do?solveclubId=AV6kld8aisgDFASb&contestProbId=AV7GKs06AU0DFAXB&probBoxId=AV6kld8aiskDFASb&type=PROBLEM&problemBoxTitle=%EC%82%BC%EC%84%B1%EC%8B%9C%ED%97%98%EB%8C%80%EB%B9%84+%EA%B8%B0%EB%B3%B8%EB%AC%B8%EC%A0%9C%EB%AA%A8%EC%9D%8C%28%EB%82%9C%EC%9D%B4%EB%8F%84+1~3%29&problemBoxCnt=15)

### 풀이 

옛날에 시간초과로 못풀었던 문제인데 풀었다!!

```cpp
#include <iostream>
#include <math.h>
using namespace std;
int arr[11][11];
int n,ans=0;
void dfs(int y,int x){
    if(y==n-1){
        ++ans;
        return;
    }
    arr[y][x]=1;
    for(int i=y+1;i<n;i++){
        arr[i][x]-=1;
        for(int j=0;j<n;j++){
            if(abs(i-y)==abs(j-x))
                arr[i][j]-=1;
        }
    }
    for(int i=0;i<n;i++){
        if(arr[y+1][i] == 0)
            dfs(y+1,i);
    }
    
    for(int i=y+1;i<n;i++){
        arr[i][x]+=1;
        for(int j=0;j<n;j++){
            if(abs(i-y)==abs(j-x))
                arr[i][j]+=1;
        }
    }
    arr[y][x]=0;
}
int main(){
    int t; cin >> t;
    for(int T=1;T<=t;T++){
        cin >> n;
        ans=0;
        for(int i=0;i<n;i++)
            dfs(0,i);
        
        
        cout << "#"<<T<< " "<<ans <<'\n';
        
    }
}

```


