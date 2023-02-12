---
emoji: 👨🏻‍💻
title: 백준 1629번 - 곱셈
date: '2023-02-12 00:00:00'
author: 허인
tags: 백준 자료구조 알고리즘 분할정복
categories: 알고리즘
---

### 문제
자연수 A를 B번 곱한 수를 알고 싶다. 단 구하려는 수가 매우 커질 수 있으므로 이를 C로 나눈 나머지를 구하는 프로그램을 작성하시오.<br><br>

### 입력
첫째 줄에 A, B, C가 빈 칸을 사이에 두고 순서대로 주어진다. A, B, C는 모두 2,147,483,647 이하의 자연수이다.<br><br>

### 출력
첫째 줄에 A를 B번 곱한 수를 C로 나눈 나머지를 출력한다.<br><br>

### 예제 입력
10 11 12<br><br>

### 예제 출력
4<br><br>

-------------------------------------
```
a,b,c = map(int,input().split(' '))
print(a**b%c)
```


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
