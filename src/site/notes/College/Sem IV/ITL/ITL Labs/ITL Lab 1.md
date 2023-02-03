---
{"dg-publish":true,"permalink":"/college/sem-iv/itl/itl-labs/itl-lab-1/"}
---

**Name:** [Param Makwana](mailto:paramsinghmakwana@gmail.com)                                                                                                                                                     

**Roll No:** F004

**Batch:** F1

**Date:** 15-12-22

___

# Programs

## Write a program for a simple calculator

```C

#include <iostream>
using namespace std;
int main (void)
{
int a, b, c;
char operate;
cout << "Enter number a: ";
cin >> a;
cout << "Enter number b: ";
cin >> b;
cout << "Enter an operator: ";
cin >> operate;
switch (operate)
{
	case '+':
	c = a + b;
	break;
	case '-':
	c = a - b;
	break;
	case '*':
	c = a * b;
	break;
	case '/':
	c = a / b;
	break;
	case '%':
	c = a % b;
	break;
	default:
	cout << "Invalid operator!" << endl;
	return 1;
	}
cout << "Answer: " << c << endl;
return 0
}

```

___

## Write a program to print prime numbers from 0 to 100

```C

#include <iostream>
using namespace std;
int main (void)
{
int a = 0;
cout << "PRIME NUMBERS FROM 0 to 100:" << endl << endl;
for (int i = 0; i <= 100; i++)
{
	for (int j = 2; j < i; j++)
	{
		if (i != 1 && i != 0)
		{
			if (i%j == 0)
			{
				break;
			}
			if (j == (i-1))
			{
			cout << i << endl;
			}
		}
	}
}
return 0;
}

```

___

## Write a program to check if entered year is a leap year or not

```C

#include <iostream>
using namespace std;
int main (void)
{
int year;
cout << "Enter a year: ";
cin >> year;
if (year%4 == 0)
{
	cout << year << " is a leap year" << endl;
}
else
{
	cout << year << " is not a leap year" << endl;
}
return 0;
}

```

___

## Write a program to check if string is palindrome or not

```C

#include <iostream>
#include <string>
#include <string.h>
#include <algorithm>
using namespace std;
int main (void)
{
char s[15];
char t[15];
int len, count = 0;
cout << "Enter a string: ";
cin >> s;
strcpy(t, s);
len = strlen(t);
for (int i = 0; i < len; i++)
{
	if (t[i] == s[len-i-1])
	{
	count++;
	}
}
if (count == len)
{
	cout << "The string is a palindrome." << endl;
}
else
{
	cout << "The string is not a palindrome." << endl;
}
return 0;
}

```

___

## Write a program to print Fibonacci series

```C

#include <iostream>
using namespace std;
int main (void)
{
int temp = 0, curr = 1, output, limit;
cout << "Enter number of times to print: ";
cin >> limit;
for (int i = 1; i <= limit; i++)
{
	output = curr + temp;
	cout << output << endl;
	temp = curr;
	curr = output;
}
return 0;
}

```

___

# Assignment

## What is the need and advantage of open source software?

Open source software is free to use and modify. It is often developed by a community of volunteers and can be more stable and reliable. It is also less expensive or even free compared to proprietary software. Open source software allows anyone to contribute and check the source code, leading to a more transparent development process. In summary, open source software offers many benefits including accessibility, reliability and cost-effectiveness

___
