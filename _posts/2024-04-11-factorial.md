---
layout: post
title:  "factorial"
date:   2024-04-11 10:25
categories: PYTHON
permalink: /archivers/factorial
---
[문제]:https://www.acmicpc.net/problem/10872

# [문제]

0보다 크거나 같은 정수 N이 주어진다. 이때, N!을 출력하는 프로그램을 작성하시오.

>입력 : 10
>출력 : 3628800

팩토리얼을 구하는 방식은 입력받은 1부터 입력받은 수 까지 곱면 된다
`1*2*3*4*5*6*7*8*9*10 =3628800`

# 코드
```
num=int(input())
sum=1
for i in range(1,num+1):
    sum*=i
print(sum)
```
- `num` 에 입력받은수 `int`로 저장
-  팩토리얼 값을 저장할 변수 `sum`선언
- `for`문으로 1 부터 `num`값 까지 반복
- `sum`의 i값을 하나씩 곱한다.
