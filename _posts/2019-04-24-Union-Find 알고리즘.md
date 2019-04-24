---
layout:     post
title:      "Union-Find 알고리즘"
subtitle:   ""
date:       2019-04-24 15:40:00
author:     "kyoungIn"
header-type: "text"
tags:
    - 알고리즘
    - 취준

---



# Union-Find 자료구조

- 찾고 합치는 과정
- 트리의 집합이 있을때, 각 트리의 부모값을 찾아(Find) 부모가 같지않으면 Union(merge) 해주는 알고리즘
- 서로소 집합(Disjoint Set) 그리고 병합 찾기 집합(Merge Find Set)이라고도 불림
-  여러 서로소 집합의 정보를 저장하고 있는 자료구조를 의미

## 예시

![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory&fname=http%3A%2F%2Fcfile25.uf.tistory.com%2Fimage%2F9970C3415A4633EF019D93)

parent 배열을 통해서 비교할 노드가 연결되어있는 노드인지, 연결해야할 노드인지 검사할 수 있다.

1. #### 깊이 상관없이 합치기

```cpp
//초기에는 parent[i]를 자기 자신으로 정한다.    
for (int i = 1; i <= n; i++)
    {
        parent[i] = i;
    }
```



```cpp
//find () : 부모찾기
int Find(int x){

    // Root인 경우 x를 반환
    if(x == parent[x]){
        return x;
    }
    else{
        // 아니면 Root를 찾아감
        int p = Find(parent[x]);
        parent[x] = p;	//메모이제이션과정,경로압축 -> 재귀함수를 줄일 수 있다. 
        return p;
    }
}
```

 

```cpp
// Union() : 합치기
void Merge(int x, int y){
    x = Find(x);
    y = Find(y);

    // 루트가 이미 같다면 같은 트리이다.
    if(x == y) 
        return ;
  
    // 루트가 같지 않다면 
    parent[y] = x; 
    //parent[x] = y;
}
```

노드의 깊이에 따라서 x를 y에 합칠지, y를 x에 합칠지 정할 수 있다.

2. #### 깊이에 따라 합치기

1. #### 

```cpp
//초기에는 parent[i]를 자기 자신으로 정한다.    
for (int i = 1; i <= n; i++)
    {
        parent[i] = i;
  			level[i] =1;
    }
```



```cpp
//find () : 부모찾기
int Find(int x){

    // Root인 경우 x를 반환
    if(x == parent[x]){
        return x;
    }
    else{
        // 아니면 Root를 찾아감
       return  parent[x] = Find(parent[x]);	//메모이제이션,경로압축 -> 재귀함수를 줄일 수 있다. 
    }
}
```

 

```cpp
// Union() : 합치기
void Merge(int x, int y){
    x = Find(x);
    y = Find(y);

    // 루트가 이미 같다면 같은 트리이다.
    if(x == y) 
        return ;
  
  	// x가 y보다 더 깊은 트리라면 swap
   if (level[x] > level[y])
        swap(x, y); // 항상 x가 더 작은 트리가 되도록 한다. 
 
    // x의 루트가 y가 되도록
    parent[x] = y;
 
    // x와 y의 깊이가 같을 때 루트노드 y의 깊이를 늘려준다.
    if (level[x] == level[y])
        ++level[y];
}
```



![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory&fname=http%3A%2F%2Fcfile23.uf.tistory.com%2Fimage%2F22363B4D58D2A7661A7564)

```
// x가 y보다 더 깊은 트리라면 swap
   if (level[x] > level[y])
        swap(x, y); // 항상 x가 더 작은 트리가 되도록 한다. 
```

과정을 통 아래와 같이 각 트리의 루트의 값이 바뀌게 된다.

![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory&fname=http%3A%2F%2Fcfile3.uf.tistory.com%2Fimage%2F227C584C58D2A9ED4A3D3A)

이후  합치면 아래 처럼 됨을 알 수 있다.

![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory&fname=http%3A%2F%2Fcfile30.uf.tistory.com%2Fimage%2F213FB14A58D2AAC0120362)



## 시간 복잡도

유니온 파인드(Union Find) 자료구조는 매우 간단하면서 매우 좋은 효율을 자랑한다.

시간 복잡도 측면을 생각해보자.

일단 경로 압축을 통해 우리는 트리를 압축시켰다.

따라서 find의 시간 복잡도는 다음과 같게 변한다.

**find :: O(lgN)**

그다음 union의 시간 복잡도를 보자.

union도 자세히 보면 find에 지배 받음을 알 수 있다.

결국 union의 시간 복잡도도 다음과 같아진다.

사실 유니온파인드 의 연산 수행시간은 분석하기 아주 어렵습니다. 왜냐하면 **Find** 연산을 호출 할 때마다 수행시간이 달라지기 때문입니다. ( 트리의 높이 변화에 의해 )

**실제 시간 복잡도는 O(α(N))**이라고 한다. **α는 애커만 함수**라고 하는데 N이  2^65536일때 애커만 함수 값이 5가 된다.

<u>따라서 그냥 상수라고 봐도 무방하다.</u>





------

#### 참고

https://www.crocus.co.kr/683   [Crocus]

https://goodgid.github.io/Union-Find-Algorithm