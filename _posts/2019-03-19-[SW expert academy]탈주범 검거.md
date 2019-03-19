---
layout:     post
title:      "[SW expert academy]탈주범 검거"
subtitle:   "BFS"
date:       2019-03-19 12:50:00
author:     "kyoungIn"
header-type: "text"
tags:
    - Algorithm
    - SW expert
---
# 탈주범 검거

## [링크](https://swexpertacademy.com/main/talk/solvingClub/problemView.do?solveclubId=AV6kld8aisgDFASb&contestProbId=AV5PpLlKAQ4DFAUq&probBoxId=AV732SG66sEDFAW7&type=PROBLEM&problemBoxTitle=%EC%82%BC%EC%84%B1+%EC%8B%A0%EC%9E%85+%EB%AA%A8%EC%9D%98+sw+%EC%97%AD%EB%9F%89%ED%85%8C%EC%8A%A4%ED%8A%B8+%EB%AC%B8%EC%A0%9C%EB%AA%A8%EC%9D%8C&problemBoxCnt=10)

### 풀이 

1시간도 안걸렸다 신난다아

pipe[1]~pipe[7]까지 연결된 구멍을 1 , 아니면 0 으로 해서 값 넣고, Pipe[0]을 길이라고 생각하고 0,0,0,0을 넣어줬다.(갈 수없도록)

**이동 하지 못하는 경우**

1. 다음 갈 곳에 현재 파이프가 연결하지 못하는 경우
2. 범위를 넘어가는 경우
3. 이미 방문했을 경우
4. 파이프를 연결하지 못하는 경우

4번 경우를 확인하기 위해  방향에 따라 다음 파이프랑 연결 할 수 있는지 확인해야 함

만약 내가 1방향 (->)으로 갈건데 다음 파이프가 {1,0,1,0}이면 가선 안된다.(3방향(<-)이 0이니까)

```cpp

#include <iostream>
#include <queue>
#include <utility>
using namespace std;
#define p pair<int,int>
int arr[51][51],visit[51][51];
int X,Y,ans;
int dx[]={0,1,0,-1},dy[]={-1,0,1,0};
int pipe[8][4]={
    {0,0,0,0},{1,1,1,1},
    {1,0,1,0},{0,1,0,1},
    {1,1,0,0},{0,1,1,0},
    {0,0,1,1},{1,0,0,1}};
void bfs(int sy,int sx,int time){
    queue<p> q;
    
    q.push(p(sy,sx));
    visit[sy][sx]=1;
    ans=0;
    for(int idx=0;idx<time;idx++){
        int len=(int)q.size();
        for(int j=0;j<len;j++){
            int y=q.front().first, x=q.front().second,val=arr[y][x];
            q.pop();
            ++ans;
            for(int i=0;i<4;i++){
                if(pipe[val][i]==0) continue;
                int nx=x+dx[i],ny=y+dy[i], nval=arr[ny][nx];
              	if(nx<0 || ny <0 || nx>= X || ny >= Y) continue;
                int ni= i>=2 ? i-2 : i+2 ;	
                if(visit[ny][nx]==1 || pipe[nval][ni]==0) continue;
                else{
                    q.push(p(ny,nx));
                    visit[ny][nx]=1;
                }
                
            }
        }
    }
}
int main(){
    int T; cin >> T;
    for(int t=1;t<=T;t++){
        int r,c,time;
        cin >> Y >> X >> r >> c >> time ;
        for(int i=0;i<Y;i++){
            for(int j=0;j<X;j++){
                visit[i][j]=0;
                cin >>arr[i][j];
            }
        }
        
        bfs(r,c,time);
        cout << "#"<<t<< " "<<ans <<'\n';
    }
}

```


