---
{"dg-publish":true,"permalink":"/college/sem-iv/ds/ds-tee-qb/linked-list/ll-theory/"}
---


# Dynamic Data Structures
They grow and shrink one element at a time, normally without some of the inefficiencies of arrays, as opposed to a static container such as an array


# Linked list vs. Arrays
## Arrays are suitable for:
- Inserting/deleting an element at the end
- Randomly accessing any element
- Searching the list for a particular value
## Linked lists are suitable for:
- Inserting an element
- Deleting an element
- Applications where sequential access is required
- In situations where the number of elements cannot be predicted beforehand

# Operations on Linked list:
- Insertion:
	- Insertion at beginning of linked list
	- Insertion at the end of linked list
	- Insertion at the middle of linked list

- Deletion:
	- Deletion from the beginning
	- Deletion from the end of the list
	- Deletion of the data that you want

- Traversal
- Searching

# Types of Linked list
Depending on the way in which the links are used to maintain adjacency, different types of linked lists are possible.
1. Linear singly-linked list (or simply linear list)

2. Circular Linked List 
	- The pointer from the last element in the list points back to the first element.

3. Doubly linked list
	- Pointers exist between adjacent nodes in both directions.
	- The list can be traversed either forward or backward.
	- Usually two pointers are maintained to keep track of the list, head and tail.

# Singly Linked List
- A singly linked list is a concrete data structure consisting of a sequence of nodes.
- Each node stores:
	- One or more elements
	- Link to the next node

# Doubly Linked List ADT
- Insertion
	- Insert at front
	- Insert at end
	- Insert before a certain node
	- Insert after a certain node
- Deletion
- Traversal
	- Forward
	- Backward
# Applications of Linked lists (Any 2 -Ex: Evaluation of Polynomials, in implementation of Stack data structure)
## Stack using Singly Linked List
- We can implement a stack with a singly linked list
- A pointer variable "top" points to the start of the list
- The first element of the linked list is considered as the stack top

## Queue using a Singly Linked List
- Basic Idea
	- Create a Linked List to which items would be added to one end and deleted from other end
- Have 2 pointers to keep track of front and rear elements:
	- One pointing to the beginning of the list (point from where elements will be deleted) (front pointer)
	- One pointing to the end of the list (point from where new elements will be added) (rear pointer)

## Polynomial Addition / Multiplication
- Let p and q be two polynomials represented by the linked list
1. While p and q are not null, repeat step 2
2. 
	- If powers of the two terms are equal, then insert the sum of the terms into the result polynomial, then advance to the next node in p and q to get the next terms
	- Else if the power of first polynomial > power of second, then insert the term of first polynomial into result polynomial, then advance to the next term in the first polynomial
	- Else, then insert the term of second polynomial into result polynomial, then advance to the next term in the second polynomial
3. Copy the remaining terms from the non-empty polynomial into the sum polynomial

## Sort (Radix/Bucket) (Only name mentioned)
## Multi-list (Course Registration) (Only name mentioned)