---
{"dg-publish":true,"permalink":"/college/sem-iv/content/ds-lab-1/"}
---

**Name:** [Param Makwana](mailto:paramsinghmakwana@gmail.com)                                                                                                                                                     

**Roll No:** F004

**Batch:** F1

**Date:** 03-01-23

___
# Aim: To study One-Dimensional Array

## Problem Statement:
Implement below problem statements using C++

1.  Write a program to find minimum element from an array
```C++

#include <iostream>

using namespace std;

int main()

{

    int n;

    cout << "Enter the number of elements in the array ";

    cin >> n;

    int arr[n];

    for (int i = 0; i < n; i++)

    {

        cout << "Enter element at position [" << i + 1 << "] ";

        cin >> arr[i];

    }

    int min = arr[0];

    for (int i = 0; i < n; i++)

    {

        if (arr[i] < min)

        {

            min = arr[i];

        }

    }

    cout << "The smallest element in the array is " << min << endl;

    return 0;

}

```

___

2. Write a program to find mean of the array elements. Then find the count and the elements which are lesser, greater, and equal to the mean
```Cpp

#include <iostream>

using namespace std;

int main()

{

    int n, mean = 0, gtm = 0, ltm = 0, etm = 0;

    cout << "Enter the number of elements in the array ";

    cin >> n;

    int arr[n];

    for (int i = 0; i < n; i++)

    {

        cout << "Enter element at position [" << i + 1 << "] ";

        cin >> arr[i];

        mean += arr[i];

    }

    mean = mean / n;

    cout << "The mean of the elements in the array is: " << mean << endl;

    for (int i = 0; i < n; i++)

    {

        if (arr[i] > mean)

        {

            gtm++;

        }

        else if (arr[i] < mean)

        {

            ltm++;

        }

        else

        {

            etm++;

        }

    }

    cout << "Number of elements that are less than mean: " << ltm << endl;

    cout << "Elements that are less than mean:" << endl;

    for (int i = 0; i < n; i++)

    {

        if (arr[i] < mean)

        {

            cout << arr[i] << " ";

        }

    }

    cout << endl;

    cout << "Number of elements that are greater than mean: " << gtm << endl;

    cout << "Greater than mean:" << endl;

    for (int i = 0; i < n; i++)

    {

        if (arr[i] > mean)

        {

            cout << arr[i] << " ";

        }

    }

    cout << endl;

    cout << "Number of elements that are equal to mean: " << etm << endl;

    cout << "Equal to mean:" << endl;

    for (int i = 0; i < n; i++)

    {

        if (arr[i] == mean)

        {

            cout << arr[i] << " ";

        }

    }

    cout << endl;

    return 0;

}

```

___

3. Write a program to find count of even and odd elements from an array

```C++

#include <iostream>

using namespace std;

int main()

{

    int n, even = 0, odd = 0;

    cout << "Enter the number of elements in the array ";

    cin >> n;

    int arr[n];

    for (int i = 0; i < n; i++)

    {

        cout << "Enter element at position [" << i + 1 << "] ";

        cin >> arr[i];

    }

    for (int i = 0; i < n; i++)

    {

        if (arr[i] % 2 == 0)

        {

            even++;

        }

        else

        {

            odd++;

        }

    }

    cout << "The number of even elements in the array is " << even << endl;

    cout << "The number of odd elements in the array is " << odd << endl;

    return 0;

}


```

___
