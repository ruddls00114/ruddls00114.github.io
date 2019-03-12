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
# 농작물 수확하기 

[링크](https://www.swexpertacademy.com/main/talk/solvingClub/problemView.do?contestProbId=AV7GLXqKAWYDFAXB&solveclubId=AV6kld8aisgDFASb&problemBoxTitle=%EC%82%BC%EC%84%B1%EC%8B%9C%ED%97%98%EB%8C%80%EB%B9%84+%EA%B8%B0%EB%B3%B8%EB%AC%B8%EC%A0%9C%EB%AA%A8%EC%9D%8C%28%EB%82%9C%EC%9D%B4%EB%8F%84+1~3%29&problemBoxCnt=15&probBoxId=AV6kld8aiskDFASb)

N X N크기의 농장이 있다.

이 농장에는 이상한 규칙이 있다.

규칙은 다음과 같다.


   ① 농장은 크기는 항상 홀수이다. (1 X 1, 3 X 3 … 49 X 49)

   ② 수확은 항상 농장의 크기에 딱 맞는 정사각형 마름모 형태로만 가능하다.


![img](https://www.swexpertacademy.com/main/common/fileDownload.do?downloadType=CKEditorImages&fileId=AV7GNTWKAa4DFAXB)
                                         
1 X 1크기의 농장에서 자라는 농작물을 수확하여 얻을 수 있는 수익은 3이다.

3 X 3크기의 농장에서 자라는 농작물을 수확하여 얻을 수 있는 수익은 16 (3 + 2 + 5 + 4 + 2)이다.

5 X 5크기의 농장에서 자라는 농작물의 수확하여 얻을 수 있는 수익은 25 (3 + 2 + 1 + 1 + 2 + 5 + 1 + 1 + 3 + 3 + 2 + 1)이다.

농장의 크기 N와 농작물의 가치가 주어질 때, 규칙에 따라 얻을 수 있는 수익은 얼마인지 구하여라.


**[제약 사항]**

농장의 크기 N은 1 이상 49 이하의 홀수이다. (1 ≤ N ≤ 49)

농작물의 가치는 0~5이다.


**[입력]**

가장 첫 줄에는 테스트 케이스의 개수 T가 주어지고, 그 아래로 각 테스트 케이스가 주어진다.

각 테스트 케이스에는 농장의 크기 N과 농장 내 농작물의 가치가 주어진다.


**[출력]**

각 줄은 '#t'로 시작하고, 공백으로 농장의 규칙에 따라 얻을 수 있는 수익을 출력한다.

(t는 테스트 케이스의 번호를 의미하며 1부터 시작한다.)

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


