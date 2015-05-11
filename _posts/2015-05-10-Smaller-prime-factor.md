---
layout: post
title: Smaller prime factor of N
description: "prime"
modified: 2015-05-10
tags: [prime, algorithms, cpp]
---

Example: N = 5 -> the prime number is smaller than 5 is 3


>Input:<br>
1<br>
2<br>
3<br>
4<br>
5

>Output:<br>
0<br>
1<br>
2<br>
1<br>
3

My solution:

{% highlight cpp %}
#include <stdio.h>
const int N = 1000000;
int prime[N];
int IsPrime[N];
int cnt = 0;

void init()
{
	int i, j ;
	for (i = 1 ; i <= 1000000 ; i++) IsPrime[i] = 1 ;
	for (i = 2 ; i <= 1000 ; i++)
		if (IsPrime[i])
		{
			for (j = i * i ; j <= 1000000 ; j += i)
				IsPrime[j] = 0 ;
		}
	for (i = 1 ; i <= 1000000 ; i++)
		if (IsPrime[i])
		{
			IsPrime[i] = cnt ;
			prime[cnt++] = i ;
		}
}

int calc(int n)
{
	int i, lim = sqrt(n) + 1, rtn = 0 ;
	for (i = 1 ; prime[i] <= lim && n != 1; i++)
	{
		while (n % prime[i] == 0)
		{
			n /= prime[i] ;
			rtn = i ;
		}
	}
	if (n == 1) return rtn ;
	return IsPrime[n] ;
}

int main()
{
	int n;
	init();
	while (~scanf("%d", &n))
	{
		printf("%d\n", calc(n));
	}
	return 0;
}
{% endhighlight %}
