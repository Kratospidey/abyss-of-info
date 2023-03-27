---
{"dg-publish":true,"permalink":"/college/sem-iv/ds/ds-assignment/ds-assignment-2/"}
---

**Name:** [Param Makwana](mailto:paramsinghmakwana@gmail.com)                                                                                                                                                     

**Roll No:** F004

**Batch:** F1

**Date:** 27-03-23

___

# Execute bubble sort on given sequence and show the output stepwise.
Sequence: ` 4, 6, 8, 3, 9, -1, 5, 2`

## First Pass

- Compare 4 and 6. No swap needed.
- Compare 6 and 8. No swap needed.
- Compare 8 and 3. Swap needed. New sequence: `4, 6, 3, 8, 9, -1, 5, 2`
- Compare 8 and 9. No swap needed.
- Compare 9 and -1. Swap needed. New sequence: `4, 6, 3, 8, -1, 9, 5, 2`
- Compare 9 and 5. Swap needed. New sequence: `4, 6, 3, 8, -1, 5, 9, 2`
- Compare 9 and 2. Swap needed. New sequence: `4, 6, 3, 8, -1, 5, 2, 9`

## Second Pass

- Compare 4 and 6. No swap needed.
- Compare 6 and 3. Swap needed. New sequence: `4, 3, 6, 8, -1, 5, 2, 9`
- Compare 6 and 8. No swap needed.
- Compare 8 and -1. Swap needed. New sequence: `4, 3, 6, -1, 8, 5, 2, 9`
- Compare 8 and 5. Swap needed. New sequence: `4, 3, 6, -1, 5, 8, 2, 9`
- Compare 8 and 2. Swap needed. New sequence: `4, 3, 6, -1, 5, 2, 8, 9`
- Compare 8 and 9. No swap needed.

## Third Pass
- Compare 4 and 3. Swap needed. New sequence: `3, 4, 6, -1, 5, 2, 8, 9`
- Compare 4 and 6. No swap needed.
- Compare 6 and -1. Swap needed. New sequence: `3, 4, -1, 6, 5, 2, 8, 9`
- Compare 6 and 5. Swap needed. New sequence: `3, 4, -1, 5, 6, 2, 8, 9`
- Compare 6 and 2. Swap needed. New sequence: `3, 4, -1, 5, 2, 6, 8, 9`
- Compare 6 and 8. No swap needed. 
- Compare 8 and 9. No swap needed.

## Fourth Pass

- Compare 3 and 4. No swap needed.
- Compare 4 and -1. Swap needed. New sequence: `3, -1, 4, 5, 2, 6, 8, 9`
- Compare 4 and 5. No swap needed.
- Compare 5 and 2. Swap needed. New sequence: `3, -1, 4, 2, 5, 6, 8, 9```
- Compare 5 and 6. No swap needed.
- Compare 6 and 8. No swap needed.
- Compare 8 and 9. No swap needed.

## Fifth Pass

- Compare 3 and -1. Swap needed. New sequence: `-1, 3, 4, 2, 5, 6, 8, 9`
- Compare 3 and 4. No swap needed.
- Compare 4 and 2. Swap needed. New sequence: `-1, 3, 2, 4, 5, 6, 8, 9`
- compare 4 and 5. No swap needed.
- Compare 5 and 6. No swap needed.
- Compare 6 and 8. No swap needed.
- Compare 8 and 9. No swap needed.

## Sixth Pass

- Compare -1 and 3. No swap needed
- Compare 3 and 2. Swap needed. New sequence: `-1, 2, 3, 4, 5, 6, 8, 9`
- Compare 3 and 4. No swap needed.
- Compare 5 and 6. No swap needed.
- Compare 6 and 8. No swap needed.
- Compare 8 and 9. No swap needed.

---

# Execute radix sort on given sequence and show the output stepwise
Sequence: `8, 101, 45,30, 543,233,321, 833,432, 9.`

1. Initialize the empty bucks
	- Bucket 0: []
	- Bucket 1: []
	- Bucket 2: []
	- Bucket 3: []
	- Bucket 4: []
	- Bucket 5: []
	- Bucket 6: []
	- Bucket 7: []
	- Bucket 8: []
	- Bucket 9: []
2. Find the maximum number in the sequence, which is 833. Count the number of digits in this number, so we get 3.
3. Pad each number in the sequence with leading zeroes to make the number of digits equal to the maximum number of digits (which is 3 in this case). The padded sequence is:  `008, 101, 045, 030, 543, 233, 321, 833, 432, 009`
4. Starting from the least significant digit, sort the numbers into the appropriate bucket based on that digit. The first pass will sort based on the ones digit:
	- Bucket 0: [030]
	- Bucket 1: [101, 321]
	- Bucket 2: [432]
	- Bucket 3: [543, 233, 833]
	- Bucket 4: []
	- Bucket 5: [045]
	- Bucket 6: []
	- Bucket 7: []
	- Bucket 8: [008]
	- Bucket 9: [009]
5. Join the buckets to get one sequence: [`030, 101, 321, 432, 543, 233, 833, 045, 008, 009`]
6. Repeat steps 4 and 5 for the next significant digit, which is the tens digit:
	- Bucket 0: [101,008,009]
	- Bucket 1: []
	- Bucket 2: [321]
	- Bucket 3: [030,432,233,833]
	- Bucket 4: [543,045]
	- Bucket 5: []
	- Bucket 6: []
	- Bucket 7: []
	- Bucket 8: []
	- Bucket 9: []
7. Join the buckets to get one sequence: [`101, 008, 009, 321, 030, 432, 233, 833, 543, 045`]
8. Repeat steps 4 and 5 for the next significant digit, which is the hundreds digit:
	- Bucket 0: [008,009,030,045]
	- Bucket 1: [101]
	- Bucket 2: [233]
	- Bucket 3: [321]
	- Bucket 4: [432]
	- Bucket 5: [543]
	- Bucket 6: []
	- Bucket 7: []
	- Bucket 8: [833]
	- Bucket 9: []
9. Join the buckets in order to get the final sorted sequence: [`008, 009, 030, 045, 101, 233, 321, 432, 543, 833`]

---

# Explain bucket sort with example

> [!info] What is Bubble Sort?
 Bucket sort is a sorting algorithm that works by distributing elements of an array into a number of buckets. Each bucket is then sorted individually using another sorting algorithm or recursively applying the bucket sort algorithm. Finally, the sorted buckets are concatenated to produce the final sorted array.

## Example

1. The array to be sorted is - [`0.78, 0.11, 0.39, 0.26, 0.72, 0.94, 0.21, 0.12, 0.23, 0.68`]
2. Initialize the empty buckets
	- Bucket 0: []
	- Bucket 1: []
	- Bucket 2: []
	- Bucket 3: []
	- Bucket 4: []
	- Bucket 5: []
	- Bucket 6: []
	- Bucket 7: []
	- Bucket 8: []
	- Bucket 9: []
3. sort the elements into their respective buckets
	- Bucket 0: []
	- Bucket 1: [`0.17, 0.12, NULL`]
	- Bucket 2: [`0.26, 0.21, 0.23, NULL`]
	- Bucket 3: [`0.39, NULL`]
	- Bucket 4: []
	- Bucket 5: []
	- Bucket 6: [`0.68, NULL`]
	- Bucket 7: [`0.78, 0.72, NULL`]
	- Bucket 8: []
	- Bucket 9: [`0.94, NULL`]
4. Sort the individual buckets themselves
	- Bucket 0: []
	- Bucket 1: [`0.12, 0.17, NULL`]
	- Bucket 2: [`0.21, 0.23, 0.26, NULL`]
	- Bucket 3: [`0.39, NULL`]
	- Bucket 4: []
	- Bucket 5: []
	- Bucket 6: [`0.68, NULL`]
	- Bucket 7: [`0.72, 0.78, NULL`]
	- Bucket 8: []
	- Bucket 9: [`0.94, NULL`]
5. Join the buckets in order to get the final sorted sequence: [`0.12, 0.17, 0.21, 0.23, 0.26, 0.39, 0.68, 0.72, 0.78, 0.94`]

---

# Execute quick sort on given sequence, with first element as pivot element. Show the output stepwise: 5, 3, 8, 1, 4, 6, 2, 7

1. 5, 3, 8, 1, 4, 6, 2, 7 [3 - l, 7 - r]
2. 5, 3, 8, 1, 4, 6, 2, 7 [8 - l, 2 - r]
3. 5, 3, 2, 1, 4, 6, 8, 7 [1 - l, 6- r]
4. 5, 3, 2, 1, 4, 6, 8, 7 [4- l, 4 - r]
5. $\therefore$ 3, 2, 1, 4, 5, 6, 8, 7
6. $\therefore$ 3, 2, 1, 4 [3 - pivot, 2 - l, 4 - r] | 5 | 6, 8, 7 [6 - pivot, 8 - l, 7 - r]
7. $\therefore$ 3, 2, 1, 4 [3 - pivot, 1 - l, 1 - r] | 5 | 6, 7, 8 [6 - pivot, 8 - l, 7 - r]
8. $\therefore$ The final sorted sequence using quick sort is - [`1, 2, 3, 4, 5, 6, 7, 8`]

---

# Show searching of element 8 and 80 in given array using binary search technique. 3, 7, 8, 9, 14, 16, 17, 22, 24.

## Searching for 8 using Binary Search

- Searching space by default is the whole array aka - [`3, 7, 8, 9, 14, 16, 17, 22, 24`]
- using the mid-point formula (*low + high / 2*) we get the mid-point as 14
- $\because 8 < 14$, we search in the left half of the array - [`3,7,8,9`]
- using the same formula we get the mid-point of the right half as 7 now
- $\because 8 > 7$, we search in the right half of the left half - [`8,9`]
- We get the target element `8` at index `2`

## Searching for 80 using Binary Search

- Searching space by default is the whole array aka - [`3, 7, 8, 9, 14, 16, 17, 22, 24`]
- using the mid-point formula (*low + high / 2*) we get the mid-point as 14
- $\because \space 80 > 14$, we search in the right half of the array - [`16, 17, 22, 24`]
- using the same formula we get the mid-point of the right half as 22 now
- $\because \space 80 > 22$, we search in the right half of the right half - [`24`]
- $\therefore$ 80 isn't present in the array $\because \space  80 \neq 24$ and 24 is the only remaining element