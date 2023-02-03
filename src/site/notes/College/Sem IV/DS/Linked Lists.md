---
{"dg-publish":true,"permalink":"/college/sem-iv/ds/linked-lists/"}
---

# What is a Linked List

- A linked list is a linear data structure in which elements are stored in nodes, and each node has a reference, or a link, to the next node in the list. 
- The first node in a linked list is called the head, and the last node is called the tail. 
- Linked lists can be used to implement many different data structures, such as stacks, queues, and symbol tables. 
- One of the main advantages of linked lists is that they allow for efficient insertion and deletion of elements, since elements can be added or removed by updating the links between the nodes. 
- However, linked lists are not as efficient as arrays for accessing elements by their index, since elements in a linked list must be accessed sequentially starting from the head of the list.
- There are two main types of linked lists: singly linked lists and doubly linked lists. In a singly linked list, each node has a link to the next node in the list, but not to the previous node. 
- In a doubly linked list, each node has a link to both the next node and the previous node.
- There are also several variations of linked lists, such as circular linked lists and threaded linked lists. In a circular linked list, the tail node of the list has a link to the head node, forming a loop. 
- In a threaded linked list, nodes may have a link to the next node in the list, as well as a link to the successor in a particular order (such as in-order or pre-order traversal of a tree).
- Linked lists have several applications, including being used as the underlying data structure for implementing dynamic arrays, which can grow and shrink as needed. 
- They are also commonly used to implement graphs, which consist of nodes and edges connecting them.

Overall, linked lists are a flexible and efficient data structure that is useful in a wide range of applications.

___

# ADT of a Linked List

The abstract data type (ADT) of a linked list is a linear collection of data elements, in which each element (also called a node) stores a reference to the next element in the list. A linked list ADT can support the following operations:

1.  `Insert()`: Add a new element to the list.
2.  `Delete()`: Remove an element from the list.
3.  `Find()`: Search for an element in the list and return its position.
4.  `Retrieve()`: Return the element at a given position in the list.
5.  `Length()`: Return the number of elements in the list.

In addition to these basic operations, a linked list ADT may also support additional operations, such as concatenation (joining two lists together), reversal (reversing the order of the elements in the list), and sorting (arranging the elements in the list in a particular order).

The linked list ADT is often implemented using a class or structure that includes fields for the head and tail of the list, as well as a field for the current position in the list. The class or structure may also include methods for performing the various operations on the list.


# Implementation and Usage of a Linked List in C++


## Singly linked lists

```C++
#include <iostream>
using namespace std;

// Define a Node class that stores an integer value and a reference to the next node.
class Node {
public:
    int data;
    Node* next;

    // Constructor to create a new node with a given value and no next node.
    Node(int value) {
        data = value;
        next = nullptr;
    }
};

// Define a LinkedList class that stores a reference to the head of the list.
class LinkedList {
public:
    Node* head;

    // Constructor to create an empty linked list.
    LinkedList() {
        head = nullptr;
    }

    // Function to insert a new node with a given value at the front of the list.
    void insertAtFront(int value) {
        // Create a new node.
        Node* newNode = new Node(value);
        // Set the next field of the new node to the current head of the list.
        newNode->next = head;
        // Set the head of the list to the new node.
        head = newNode;
    }

    // Function to delete the node at the front of the list.
    void deleteAtFront() {
        // If the list is empty, do nothing.
        if (head == nullptr) {
            return;
        }
        // Save a reference to the head of the list.
        Node* temp = head;
        // Set the head of the list to the next node in the list.
        head = head->next;
        // Delete the old head of the list.
        delete temp;
    }

    // Function to print the values of all the nodes in the list.
    void print() {
        // Start at the head of the list.
        Node* current = head;
        // Print the value of each node until we reach the end of the list.
        while (current != nullptr) {
            std::cout << current->data << " ";
            current = current->next;
        }
        std::cout << std::endl;
    }
};

int main() {
    // Create a new linked list.
    LinkedList list;

    // Insert some values at the front of the list.
    list.insertAtFront(3);
    list.insertAtFront(2);
    list.insertAtFront(1);

    // Print the values in the list.
    list.print(); // Output: 1 2 3

    // Delete the first node in the list.
    list.deleteAtFront();

    // Print the values in the list again.
    list.print(); // Output: 2 3

    return 0;
}

```


## Doubly Linked Lists

```C++

#include <iostream>

// Define a Node class that stores an integer value and references to the next and previous nodes.
class Node {
public:
    int data;
    Node* next;
    Node* prev;

    // Constructor to create a new node with a given value and no next or previous nodes.
    Node(int value) {
        data = value;
        next = nullptr;
        prev = nullptr;
    }
};

// Define a LinkedList class that stores a reference to the head and tail of the list.
class LinkedList {
public:
    Node* head;
    Node* tail;

    // Constructor to create an empty linked list.
    LinkedList() {
        head = nullptr;
        tail = nullptr;
    }

    // Function to insert a new node with a given value at the front of the list.
    void insertAtFront(int value) {
        // Create a new node.
        Node* newNode = new Node(value);
        // Set the next field of the new node to the current head of the list.
        newNode->next = head;
        // Set the previous field of the new node to null.
        newNode->prev = nullptr;
        // If the list is not empty, set the previous field of the current head of the list to the new node.
        if (head != nullptr) {
            head->prev = newNode;
        }
        // Set the head of the list to the new node.
        head = newNode;
        // If the list was previously empty, set the tail of the list to the new node.
        if (tail == nullptr) {
            tail = newNode;
        }
    }

		// Function to delete the node at the front of the list.
	void deleteAtFront() {
	    // If the list is empty, do nothing.
	    if (head == nullptr) {
	        return;
	    }
	    // Save a reference to the head of the list.
	    Node* temp = head;
	    // Set the head of the list to the next node in the list.
	    head = head->next;
	    // If the list is not now empty, set the previous field of the new head of the list to null.
	    if (head != nullptr) {
	        head->prev = nullptr;
	    }
	    // If the list is now empty, set the tail of the list to null.
	    if (head == nullptr) {
	        tail = nullptr;
	    }
	    // Delete the old head of the list.
	    delete temp;
	}
	
	// Function to insert a new node with a given value at the end of the list.
	void insertAtEnd(int value) {
	    // Create a new node.
	    Node* newNode = new Node(value);
	    // Set the previous field of the new node to the current tail of the list.
	    newNode->prev = tail;
	    // Set the next field of the new node to null.
	    newNode->next = nullptr;
	    // If the list is not empty, set the next field of the current tail of the list to the new node.
	    if (tail != nullptr) {
	        tail->next = newNode;
	    }
	    // Set the tail of the list to the new node.
	    tail = newNode;
	    // If the list was previously empty, set the head of the list to the new node.
	    if (head == nullptr) {
	        head = newNode;
	    }
	}
	
	// Function to delete the node at the end of the list.
	void deleteAtEnd() {
	    // If the list is empty, do nothing.
	    if (tail == nullptr) {
	        return;
	    }
	    // Save a reference to the tail of the list.
	    Node* temp = tail;
	    // Set the tail of the list to the previous node in the list.
	    tail = tail->prev;
	    // If the list is not now empty, set the next field of the new tail of the list to null.
	    if (tail != nullptr) {
	        tail->next = nullptr;
	    }
	    // If the list is now empty, set the head of the list to null.
	    if (tail == nullptr) {
	        head = nullptr;
	    }
	    // Delete the old tail of the list.
	    delete temp;
	}

	// Function to print the values of all the nodes in the list.
	void print() {
	    // Start at the head of the list.
	    Node* current = head;
	    // Print the value of each node until we reach the end of the list.
	    while (current != nullptr) {
	        std::cout << current->data << " ";
	        current = current->next;
	    }
	    std::cout << std::endl;
	}
	};
	
	// Main function to demonstrate the linked list implementation.
	int main() {
	    // Create a new linked list.
	    LinkedList list;
	    // Insert some values at the front of the list.
	    list.insertAtFront(1);
	    list.insertAtFront(2);
	    list.insertAtFront(3);
	    // Print the values of the nodes in the list.
	    std::cout << "After inserting at front: ";
	    list.print();
	    // Insert some values at the end of the list.
	    list.insertAtEnd(4);
	    list.insertAtEnd(5);
	    list.insertAtEnd(6);
	    // Print the values of the nodes in the list.
	    std::cout << "After inserting at end: ";
	    list.print();
	    // Delete a node from the front of the list.
	    list.deleteAtFront();
	    // Print the values of the nodes in the list.
	    std::cout << "After deleting at front: ";
	    list.print();
	    // Delete a node from the end of the list.
	    list.deleteAtEnd();
	    // Print the values of the nodes in the list.
	    std::cout << "After deleting at end: ";
	    list.print();
	    return 0;
	}


```

___
