---
layout: post
title: 入门训练 Fibonacci数列
date: 2017-01-18 19:05:52
tags: [java,算法]
categories: 算法
comments: true
---

## 问题描述
Fibonacci数列的递推公式为：Fn=Fn-1+Fn-2，其中F1=F2=1。

当n比较大时，Fn也非常大，现在我们想知道，Fn除以10007的余数是多少。

## 输入格式
输入包含一个整数n。
## 输出格式
输出一行，包含一个整数，表示Fn除以10007的余数。
> 说明：在本题中，答案是要求Fn除以10007的余数，因此我们只要能算出这个余数即可，而不需要先计算出Fn的准确值，再将计算的结果除以10007取余数，直接计算余数往往比先算出原数再取余简单。

## 样例输入
`10`
## 样例输出
`55`
## 样例输入
`22`
## 样例输出
`7704`
## 数据规模与约定
`1 <= n <= 1,000,000`

提交序号	1209677  
提交时间	2017-01-18 19:05:30  
评测结果	正确  
得分	100  
CPU使用	250ms  
内存使用	21.17MB  
试题名称	入门训练 Fibonacci数列  
语言	JAVA  
源代码  
```java
import java.util.Scanner;

public class Main {
	public static void main(String[] args) {
		int a1,a2;  
	    a1=a2=1;  
	    int sum=0,temp;//sum是保存余数的变量 ，temp是为了方便交换数据   
	    long n;//因为n>=1 and n<=1000000   
	    long i;  
	    Scanner scanner = new Scanner(System.in);
		n = scanner.nextLong();
		for(i=1;i<=n;i++)  
	    {  
	        sum=a1 % 10007;  
	        temp=a2;  
	        a2=(a1+a2) % 10007;  
	        a1=temp;   
	    }
		System.out.println(sum);

	}
}
```
