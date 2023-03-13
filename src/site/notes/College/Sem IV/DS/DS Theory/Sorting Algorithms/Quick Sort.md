---
{"dg-publish":true,"permalink":"/college/sem-iv/ds/ds-theory/sorting-algorithms/quick-sort/"}
---

```C++
#include <iostream>

using namespace std;

  

void swap(int* a, int* b) {

	int t = *a;
	
	*a = *b;
	
	*b = t;

}

  

int partition(int arr[], int l, int r) {

	int pivot = arr[r];
	
	int i = (l - 1);
	
	for (int j = l; j <= r - 1; j++) {
	
		if (arr[j] < pivot) {
		
			i++;
			
			swap(&arr[i], &arr[j]);
		
		}
	
	}
	
	swap(&arr[i + 1], &arr[r]);
	
	return (i + 1);

}

  

void quickSort(int arr[], int l, int r) {

	if (l < r) {
	
		int p = partition(arr, l, r);
		
		quickSort(arr, l, p - 1);
		
		quickSort(arr, p + 1, r);
	
	}

}

  

int main() {

	cout<<"Size of array: ";
	
	int size;
	
	cin >> size;
	
	int arr[size];
	
	cout<<"Taking input for array"<<endl;
	
	for (int i = 0; i < size; i++) {
	
		cout<<"Element "<<i+1<<": ";
		
		cin >> arr[i];
	
	}
	
	quickSort(arr, 0, size - 1);
	
	cout << "Sorted array: \n";
	
	for (int i = 0; i < size; i++)
	
		cout << arr[i] << " ";
	
	cout << endl;
	
	return 0;

}
```