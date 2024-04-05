---
layout: post
title:  "matrixadd"
date:   2024-04-05 1:47
categories: PYTHON
permalink: /archivers/matrixadd
---

# 행열더하기

```ptchon
a1=[[1,2],[2,3]]
a2=[[4,6],[7,9]]

answer = []
for i in range(len(a1)):
    list=[]
    for j in range(len(a1[i])):
        list.append(a1[i][j]+a2[i][j])
    answer.append(list)
print(answer)
```    



실행결과
```
[[5, 8], [9, 12]]
```

