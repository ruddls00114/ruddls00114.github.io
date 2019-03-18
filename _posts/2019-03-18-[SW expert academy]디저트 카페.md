---
layout:     post
title:      "[SW expert academy]디저트 카페"
subtitle:   ""
date:       2019-03-18 05:40:00
author:     "kyoungIn"
header-type: "text"
tags:
    - Algorithm
    - SW expert
---
# 디저트 카페

## [링크](https://www.swexpertacademy.com/main/talk/solvingClub/problemView.do?solveclubId=AV6kld8aisgDFASb&contestProbId=AV5VwAr6APYDFAWu&probBoxId=AV732SG66sEDFAW7&type=PROBLEM&problemBoxTitle=%EC%82%BC%EC%84%B1+%EC%8B%A0%EC%9E%85+%EB%AA%A8%EC%9D%98+sw+%EC%97%AD%EB%9F%89%ED%85%8C%EC%8A%A4%ED%8A%B8+%EB%AC%B8%EC%A0%9C%EB%AA%A8%EC%9D%8C&problemBoxCnt=10)

### 풀이 

벡터로 배열을 할당해주니 자꾸 시간초과가 떠서 , 그냥 전역변수로 선언하니 통과했다..

마름모를 만들어야 하니까 커브는 3번 또는 4번만 해야한다. 그 이상은 안됨

길이는 최소 4여야 한다.

예를 들어

9 8 9 8 
4 6 8 4
8 7 7 8
4 5 3 5

에서 시작점 (1,1) 6으로 들면 

  ->6 l=1,d=-1,c=0
6->8  l=2 ,d:2,c=1
8->5 l=3 d=3 c=2
5->7 l=4 d=1 c=3
7->4 l=5 d=1 c=3 //이동방향 같으니 커브 수 증가 안함
4->9 l=6 d=0 c=4
9->6  다음 좌표가 출발점이므로 맥스값 비교.

```cpp
#include <iostream>
#include <algorithm>
using namespace std;
#define IOFAST() ios_base::sync_with_stdio(false);cin.tie(NULL);cout.tie(NULL);
int dx[]={-1,1,-1,1};
int dy[]={-1,-1,1,1};
int maxEat ;
int n,sx,sy;
int map[21][21] ;
int arr[101];

void dfs(int y,int x, int l,int d,int c){//y,x,길이,방향,커브횟수
    if(c==5) return;
    arr[map[y][x]] =1;
    
    for(int i=0;i<4;i++){
        int ny= y+dy[i], nx=x+dx[i];
        if(ny==sy && nx==sx && l>=4 && c>=3){
            maxEat=max(maxEat,l);
            arr[map[y][x]]=0;
            return;
        }
        if(nx <0 || ny <0 || nx >=n || ny >=n || arr[map[ny][nx]] ==1) continue;
        dfs(ny,nx,l+1,i,i==d ? c:c+1);
    }
    arr[map[y][x]]=0;
    
}
int main(){
    IOFAST();
    int t; cin >> t;
    for(int T=1;T<=t;T++){
        cin >> n;
        for(int i=0;i<n;i++){
            for(int j=0;j<n;j++)
                cin >> map[i][j];
        }
        maxEat =-1;
        for(int i=0;i<n;i++){
            for(int j=0;j<n;j++){
                sx=j;   sy=i;
                dfs(i,j,1,-1,0);
            }
        }
        cout <<"#"<<T<<" " <<maxEat << '\n';
    }
}
```


