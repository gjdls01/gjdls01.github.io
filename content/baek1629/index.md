---
emoji: 👨🏻‍💻
title: 백준 1629번 - 곱셈
date: '2023-02-12 00:00:00'
author: 허인
tags: 백준 자료구조 알고리즘 분할정복
categories: 알고리즘
---

자연수 A를 B번 곱한 수를 알고 싶다. 단 구하려는 수가 매우 커질 수 있으므로 이를 C로 나눈 나머지를 구하는 프로그램을 작성하는 문제이다.

-------------------------------------
```
a,b,c = map(int,input().split(' '))
print(a**b%c)
```
위와 같이 작성할 경우, 결과는 올바르게 출력이 되지만, 시간 제한이라는 문제가 발생한다.<br>
이에,


```
import sys

a,b,c = map(int,sys.stdin.readline().split( ))

def func(a,b):
    if b == 1:
        return a%c
    else:
        tmp = func(a, b // 2) ** 2
        if b % 2 == 0:
            return tmp % c
        else:
            return (tmp * a) % c

print(func(a,b))
```
