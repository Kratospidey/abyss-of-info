---
{"dg-publish":true,"permalink":"/college/sem-iv/content/itl-lab-3/"}
---

**Name:** [Param Makwana](mailto:paramsinghmakwana@gmail.com)                                                                                                                                                     

**Roll No:** F004

**Batch:** F1

**Date:** 05-01-23

___
# Programs

## WAP to find Largest Element in 1 D Array in C

```C
// write a program in c to find the largest element in the array
#include <stdio.h>
int main()
{
    int i, n, large;
    printf("Enter the size of the array : ");
    scanf("%d", &n);
    int a[n];
    printf("Enter %d elements of  the array : ", n);
    for (i = 0; i < n; i++)
        scanf("%d", &a[i]);
    large = a[0];
    for (i = 1; i < n; i++)
    {
        if (large < a[i])
            large = a[i];
    }
    printf("Largest element in the array is : %d \n", large);
    return 0;
}
```

___
## WAP to Find Sum and average of 1 D Array Elements

```C
// Write a program to Find Sum and average of 1 D Array Elements
#include <stdio.h>
int main()
{
    int i, n, sum = 0;
    float avg;
    printf("Enter the size of the array : ");
    scanf("%d", &n);
    int a[n];
    printf("Enter %d elements of  the array : ", n);
    for (i = 0; i < n; i++)
        scanf("%d", &a[i]);
    for (i = 0; i < n; i++)
    {
        sum = sum + a[i];
    }
    printf("Sum of elements in the array is : %d \n", sum);
    avg = (float)sum / n;
    printf("Average of elements in the array is : %f \n", avg);
    return 0;
}
```

___
## WAP to take input in a 2-D Array and display the array in proper format

```C
// write a program to take input in a 2-D Array and display the array in proper format
#include <stdio.h>
int main()
{
    int i, j, m, n;
    printf("Enter the size of the array : ");
    scanf("%d %d", &m, &n);
    int a[m][n];
    printf("Enter %d elements of  the array : ", m * n);
    for (i = 0; i < m; i++)
        for (j = 0; j < n; j++)
            scanf("%d", &a[i][j]);
    printf("The array is : \n");
    for (i = 0; i < m; i++)
    {
        for (j = 0; j < n; j++)
            printf("%d ", a[i][j]);
        printf("\n");
    }
    return 0;
}
```

___
## WAP to add diagonal elements of a 2-D array

```C
// Write a program to add diagonal elements of a 2-D array
#include <stdio.h>
int main()
{
    int i, j, m, n, sum = 0;
    printf("Enter the size of the array : ");
    scanf("%d %d", &m, &n);
    int a[m][n];
    printf("Enter %d elements of  the array : ", m * n);
    for (i = 0; i < m; i++)
        for (j = 0; j < n; j++)
            scanf("%d", &a[i][j]);
    if (m == n)
    {
        for (i = 0; i < m; i++)
            for (j = 0; j < n; j++)
                if (i == j)
                    sum = sum + a[i][j];
        printf("Sum of diagonal elements in the array is : %d \n", sum);
    }
    else
        printf("Not a square matrix");
    return 0;
}
```

___
## WAP to find transpose of a matrix

```C
// Write a program to find transpose of a matrix

#include <stdio.h>
int main()
{
    int i, j, m, n;
    printf("Enter the size of the array : ");
    scanf("%d %d", &m, &n);
    int a[m][n];
    printf("Enter %d elements of  the array : ", m * n);
    for (i = 0; i < m; i++)
        for (j = 0; j < n; j++)
            scanf("%d", &a[i][j]);
    printf("The matrix is \n");
    for (i = 0; i < m; i++)
    {
        for (j = 0; j < n; j++)
            printf("%d ", a[i][j]);
        printf("\n");
    }
    printf("The transpose of the matrix is \n");
    for (i = 0; i < n; i++)
    {
        for (j = 0; j < m; j++)
            printf("%d ", a[j][i]);
        printf("\n");
    }
    return 0;
}
```

___

# Questions

## Explain the Linux interface

-  The Linux interface is the way that you interact with the Linux operating system. This can include the graphical user interface (GUI), which is the desktop environment that you see when you boot up your Linux machine, as well as the command-line interface (CLI), which is a way to interact with the operating system using text commands. 
-  The GUI is the most common way for users to interact with a Linux system. It includes elements such as icons, windows, and menus that you can use to open and run programs, access files and settings, and perform other tasks. The GUI is usually provided by a desktop environment, such as GNOME, KDE, or Xfce, which provides a consistent look and feel across different applications and programs. 
-  The CLI, on the other hand, is a more advanced way to interact with the Linux system. It allows you to enter commands directly into the terminal, which is a text-based interface that allows you to access the full power of the operating system. Using the CLI requires a certain amount of knowledge and experience, as you need to know the specific commands and options available to you. However, it can be a very powerful and efficient way to interact with the system, especially when you need to perform tasks that are not possible or easy to do using the GUI.

___

## Explain the meaning and working of cd ls and pwd commands

-  "pwd" stands for "print working directory." When you enter the "pwd" command, it will print the path of the current directory (folder) that you are in. For example, if you are currently in the "/home/user/documents" directory, running "pwd" will output "/home/user/documents".

-  "ls" stands for "list". When you enter the "ls" command, it will list the files and directories in the current directory. You can use various options with the "ls" command to modify its behavior. For example, "ls -l" will list the files and directories in a long format, showing additional information such as the file size, owner, and permissions.

-  "cd" stands for "change directory". When you enter the "cd" command followed by a directory name, it will change the current working directory to the directory specified. For example, "cd /home/user/documents" will change the current directory to the "documents" directory inside the "user" directory, which is inside the "home" directory.

Here are some examples of how you can use these commands:

```zsh
$ pwd
/home/user
$ ls
documents  downloads  music  pictures  videos
$ cd documents
$ pwd
/home/user/documents
$ ls
report.txt  presentation.pptx  budget.xlsx
```

In this example, "pwd" is used to show that the current directory is "/home/user", "ls" is used to list the contents of that directory, "cd documents" is used to change to the "documents" directory, and "pwd" and "ls" are used again to show that the current directory has been changed and to list its contents.

___
