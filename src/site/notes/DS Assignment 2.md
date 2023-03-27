---
{"dg-publish":true,"permalink":"/ds-assignment-2/"}
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
- Compare 8 and 3. Swap needed. New sequence: `4, 6, 3, 8, 9, -1, 5`
- Compare 8 and 9. No swap needed.
- Compare 9 and -1. Swap needed. New sequence: `4, 6, 3, 8, -1, 9, 5`
- Compare 9 and 5. Swap needed. New sequence: `4, 6, 3, 8, -1, 5, 9`

## Second Pass

- Compare 4 and 6. No swap needed.
- Compare 6 and 3. Swap needed. New sequence: `4, 3, 6, 8, -1, 5, 9`
- Compare 6 and 8. No swap needed.
- Compare 8 and -1. Swap needed. New sequence: `4, 3, 6, -1, 8, 5, 9`
- Compare 8 and 5. Swap needed. New sequence: `4, 3, 6, -1, 5, 8, 9`
- Compare 8 and 9. No swap needed.

## Third Pass
- Compare 4 and 3. Swap needed. New sequence: `3, 4, 6, -1, 5, 8, 9`
- Compare 4 and 6. No swap needed.
- Compare 6 and -1. Swap needed. New sequence: `3, 4, -1, 6, 5, 8, 9`
- Compare 6 and 5. Swap needed. New sequence: `3, 4, -1, 5, 6, 8, 9`
- Compare 6 and 8. No swap needed.
- Compare 8 and 9. No swap needed.

## Fourth Pass

- Compare 3 and 4. No swap needed.
- Compare 4 and -1. Swap needed. New sequence: `3, -1, 4, 5, 6, 8, 9`
- Compare 4 and 5. No swap needed.
- Compare 5 and 6. No swap needed.
- Compare 6 and 8. No swap needed.
- Compare 8 and 9. No swap needed.

## Fifth Pass

- Compare 3 and -1. Swap needed. New sequence: `-1, 3, 4, 5, 6, 8, 9`
- Compare 3 and 4. No swap needed.
- Compare 4 and 5. No swap needed.
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
