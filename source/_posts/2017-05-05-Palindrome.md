---
title: 回文数的实现
date: 2017-05-05 14:42:44
categories: 算法
tags: 
    - C++
    - python
---
[摘要] ***

## C++

```C++
#include <iostream>
#include <iomanip>

using namespace std;

int palindrome(int min, int max);
bool is_palindrome(int x);

int main() {
	int min, max;
	cout << "please input two positive integers: ";
	cin >> min >> max;
	palindrome(min, max);
	return 0;
}

//回文数
int palindrome(int min, int max) {
	int temp;
	if(min > max) {
		temp = max;
		max = min;
		min = temp;
	}

	for(int i=min; i<= max; i++) {
		if(is_palindrome(i))
			cout << i << setw(4);
	}
	cout<< endl;
	return 0;
}

//判断一个数是否是回文数
bool is_palindrome(int origin) {

	int reverse = 0,      //倒序数
		rem = 0,          //余数
		temp = origin;    //临时存储数

	while(temp>0) {
		rem = temp % 10;
		reverse = reverse * 10 + rem;
		temp = temp / 10;
	}
	
	return origin == reverse;
}

```

## python

```python
def is_palindrome(n):
	if not isinstance(n, int):
		return False
	if n<0:
		return False
	li = []
	while n>0:
		li.append(n % 10)
		n //= 10               //强制地板数除法，n /= 10 在python3.5.2中会有问题
	li_origin = li[:]
	li_origin.reverse()
	return li_origin == li
	
output = filter(is_palindrome, range(0, 1000))   //输出0~999中的回文数
print(list(output))

```

is_palindrome函数部分也可以仿照C++这样写

```python
def is_palindrome(n):
	if not isinstance(n, int):
		return False
	if n<0:
		return False
	reverse = 0    #倒序数
	rem = 0        #余数
	temp = n       #临时存储数据
	while temp>0:
		rem = temp % 10
		reverse = reverse * 10 + rem
		temp //= 10
	return reverse == n

```

## 结果

C++

![1](palindrome_C++.png)

python

![2](palindrome_python.png)


