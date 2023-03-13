---
{"dg-publish":true,"permalink":"/college/sem-iv/ds/ds-theory/sorting-algorithms/bubble-sort/"}
---

```C++
#include <iostream>

using namespace std;

int* Bubble(int *a, int n) {

	int temp, *arr = a;

	for (int i = 0; i < n; i++) {

		for (int j = 0; j < n - i; j++) {

			if (arr[j] > arr[j+1]) {

				temp = arr[j];

				arr[j] = arr[j+1];

				arr[j+1] = temp;

			}

		}

	}

	return arr;

}

  

int main() {

	int size;

	cout<<"Size of array: ";

	cin >> size;

	int arr[size];

	cout<<"Taking input for array:"<<endl;

	for (int i = 0; i < size; i++) {

		cout<<"Element "<<i+1<<": ";
		
		cin >> arr[i];

	}

	cout<<"Array: ";
	
	for (int i = 0; i < 10; i++) {
	
		cout<<arr[i]<<" ";
	
	}
	
	cout<<endl;
	
	int *new_array = Bubble(arr, size);
	
	cout<<"Sorted Array: ";
	
	for (int i = 0; i < 10; i++) {
	
		cout<<new_array[i]<<" ";
	
	}
	
	cout<<endl;
	
	return 0;

}
```