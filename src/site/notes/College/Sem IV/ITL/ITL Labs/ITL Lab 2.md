---
{"dg-publish":true,"permalink":"/college/sem-iv/itl/itl-labs/itl-lab-2/"}
---

**Name:** [Param Makwana](mailto:paramsinghmakwana@gmail.com)                                                                                                                                                     

**Roll No:** F004

**Batch:** F1

**Date:** 23-12-22

___

# Programs

## Write a program to find the largest of three numbers

```C

#include <stdio.h>
int main (void)
{
	int a, b, c;
	
	printf("Enter a: ");
	scanf("%i", &a);
	
	printf("Enter b: ");
	scanf("%i", &b);
	
	printf("Enter c: ");
	scanf("%i", &c);
	
	int max;
	
	max = a;
	
	if (max < b)
	{
		max = b;
	}
	if (max < c)
	{
		max = c;
	}
	
	printf("Largest number: %i\n", max);
	
	return 0
}

```

___

## Write a program to check whether number is even or odd

```C

#include <stdio.h>
int main (void)
{
	int num;
	
	printf("Enter number: ");
	scanf("%i", &num);
	
	if (num % 2 == 0)
	{
		printf("Number is even\n");
	}
	else
	{
		printf("Number is odd\n");
	}
	
	return 0;
}

```

___

## Write a program to print even numbers till a certain limit

```C

#include <stdio.h>
int main (void)
{
	int limit, count = 1;
	
	printf("Enter limit: ");
	scanf("%i", &limit);
	
	for (int i = 1; count <= limit; i++)
	{
		if (i % 2 == 0)
		{
			printf("%i\n", i);
			count++;
		}
	}
	
	return 0;
	
}

```

___

## Write a program to print a multiplication table of a number entered by the user.

```C

include <stdio.h>
int main (void)
{
	int number;
	
	printf("Enter number: ");
	scanf("%i", &number);
	
	for (int i = 1; i <= 12; i++)
	{
		printf("%i * %i = %i\n", number, i, number*i);
	}
	
	return 0;
}

```

___

## Write a program to print the following pattern

```C

#include <stdio.h>
int main (void)
{
	int rows;
	
	printf("Enter rows: ");
	scanf("%i", &rows);
	
	for (int i = 0; i < rows; i++)
	{
		for (int j = 0; j <= i; j++)
		{
			printf("*");
		}
		printf("\n");
	}
	return 0;
}

```

___

# Assignment

## What is the Linux Kernel? Is it Legal to edit Linux Kernel?

-  The Linux kernel is the core of the Linux operating system and is responsible for managing the hardware and software resources of a computer. It is written in C and is an open source project, meaning that its source code is freely available for anyone to view, modify, and distribute

-  The kernel is the first program that starts when a computer is turned on and remains running until the computer is shut down, managing tasks such as input/output operations and memory management.

-  Yes, it is legal to edit the Linux kernel as it is licensed under the GNU General Public License (GPL), a free software license that allows users to view, modify, and distribute the source code as long as they follow the terms of the GPL. However, users must not use the kernel for any illegal or unethical purposes.

___
## What are the basic components of Linux?

The basic components of a Linux operating system are:

1. The Linux kernel 
2. System libraries 
3. System utilities
4. The shell 
5. System configuration files 
6. System administration tools 
7. Graphical User Interface (GUI)

These components work together to provide a functional operating system that can be used to run a wide variety of programs and perform various tasks.

___
