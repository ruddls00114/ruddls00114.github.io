---
layout:     post
title:      "[SW expert academy]농작물 수확하기"
subtitle:   ""
date:       2019-03-12 10:40:00
author:     "kyoungIn"
header-type: "text"
tags:
    - Algorithm
    - SW expert
---
# 농작물 수확하기-

## [링크](https://www.swexpertacademy.com/main/talk/solvingClub/problemView.do?contestProbId=AV7GLXqKAWYDFAXB&solveclubId=AV6kld8aisgDFASb&problemBoxTitle=%EC%82%BC%EC%84%B1%EC%8B%9C%ED%97%98%EB%8C%80%EB%B9%84+%EA%B8%B0%EB%B3%B8%EB%AC%B8%EC%A0%9C%EB%AA%A8%EC%9D%8C%28%EB%82%9C%EC%9D%B4%EB%8F%84+1~3%29&problemBoxCnt=15&probBoxId=AV6kld8aiskDFASb)

### 풀이 

```cpp
#include <iostream>

using namespace  std;

int main(){
    int t,idx; cin >> t;
    
    for(int idx=1;idx<=t;idx++){
        int i,j,s,result=0;
        scanf("%d",&s);
        int cnt=1,start=s/2;
        for(i=0;i<s;i++){
            int mm=start,c=1;
            for(j=0;j<s;j++){
                int temp;
                scanf("%1d",&temp);
                if(j==mm && c<=cnt){
                    result+=temp;
                    c++;
                    mm++;
                }
            }
            if(i>=s/2) {cnt-=2; start+=1; }
            else       {cnt+=2 ; start-=1; }
        }
        cout <<'#'<<idx<<' '<<result <<'\n';
    }
}

```


