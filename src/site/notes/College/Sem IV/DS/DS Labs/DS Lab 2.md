---
{"dg-publish":true,"permalink":"/college/sem-iv/ds/ds-labs/ds-lab-2/"}
---

**Name:** [Param Makwana](mailto:paramsinghmakwana@gmail.com)                                                                                                                                                     

**Roll No:** F004

**Batch:** F1

**Date:** 03-01-23

___

# Aim:  To study One-Dimensional Array

## Problem Statement:
Implement below problem statements using C++

1.  Write a program to insert a new element in a given array

```C++

#include <iostream>

using namespace std;

int main()

{

    int size;    

    int element;  

    int position;

    cout << "Enter the number of elements in the array: ";

    cin >> size;

    // creating a dynamically allocated array as the array needs to expand and using vector isn't an option_

    int *array = new int[size];

    for (int i = 0; i < size; i++)

    {

        cout << "Enter element at position [" << i + 1 << "] ";

        cin >> array[i];

    }

    cout << "Enter the element to be inserted: ";

    cin >> element;

    cout << "Enter the position to insert the element at (0-based index): ";

    cin >> position;

    for (int i = size; i > position; i--)

    {

        array[i] = array[i - 1];

    }

    array[position] = element;

    size++;

    cout << "Modified array: ";

    for (int i = 0; i < size; i++)

    {

        cout << array[i] << " ";

    }

    cout << endl;

    delete[] array;

    return 0;

}

```

___
2. Write a program to delete an element from an array

```C++

#include <iostream>

using namespace std;

const int MAX_SIZE = 100;

int main() {

  int array[MAX_SIZE];

  int size;

  int position;

  cout << "Enter the number of elements in the array: ";

  cin >> size;

  cout << "Enter the elements of the array: ";

  for (int i = 0; i < size; i++) {

    cout << "Enter element at position [" << i + 1 << "] ";

    cin >> array[i];

  }

  cout << "Enter the position of the element to be deleted (0-based index): ";

  cin >> position;

  for (int i = position; i < size - 1; i++) {

    array[i] = array[i + 1];

  }

  size--;

  cout << "Modified array: ";

  for (int i = 0; i < size; i++) {

    cout << array[i] << " ";

  }

  cout << endl;

  return 0;

}

```

___

3.  For both the programs, traverse the array before and after the operations

___
