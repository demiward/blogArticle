---
title: 斐波拉契数列的实现
date: 2017-05-04 11:25:22
categories: 算法
tags: 
    - C++
    - python
---

[摘要] 斐波拉契数列又称黄金分割数列，在著名的小说达芬奇密码中也有精彩的呈现，此文章主要提供两种语法：C++和python的斐波拉契数列的实现。

## C++

```C++
#include <iostream>
#include <iomanip>

using namespace std;

int fib(int max);

int main() {
	int max;
    cout << "please input a number: ";
    cin >> max;
    fib(max);
}

int fib(int max) {
	int n = 0, a = 0, b = 1;
	while (n < max) {
		cout << b << setw(4);
		int c = a;
		a = b;
		b = c + b;
		n++;
	}
	cout << endl;
	return 0;
}

```

## python

```python

def fib(max):
	n, a, b = 0, 0, 1
	while n < max:
		print(b)
		a, b = b, a + b
		n = n + 1
	return 'done'
	
f = fib(5)
print(f)

```

## 结果
![1](fib.png)