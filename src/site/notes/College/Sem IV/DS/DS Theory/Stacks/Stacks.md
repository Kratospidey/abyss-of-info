---
{"dg-publish":true,"permalink":"/college/sem-iv/ds/ds-theory/stacks/stacks/"}
---

# What is a Stack

-  A stack is a linear data structure that follows the last-in, first-out (LIFO) principle. This means that the last element added to the stack will be the first one to be removed.
-  Operations commonly performed on stacks include push, pop, and peek. A push operation adds an element to the top of the stack, a pop operation removes an element from the top of the stack, and a peek operation returns the value of the top element without removing it from the stack.
- Stacks are commonly used in programming to store temporary data or to reverse the order of items. They can also be used to implement undo/redo functions and to evaluate expressions in programming languages.

___

# ADT of a Stack

The stack abstract data type is defined by the following structure and operations. A stack is structured, as described above, as an ordered collection of items where items are added to and removed from the end called the “top.” Stacks are ordered LIFO. The Essential stack operations are given below.

- `Stack()` creates a new stack that is empty. It needs no parameters and returns an empty stack.
- `push(item)` adds a new item to the top of the stack. It needs the item and returns nothing.
- `pop()` removes the top item from the stack. It needs no parameters and returns the item. The stack is modified.
- `peek()` • returns the top item from the stack but does not remove it. It needs no parameters. The stack is not modified.
- `is_empty()` tests to see whether the stack is empty. It needs no parameters and returns a Boolean value.
- `size()` returns the number of items on the stack. It needs no parameters and returns an integer.

___

# Implementation and Usage of a Stack in C++


## Stack Array Implementation

```Cpp

#include <iostream>
using namespace std;
#define MAX_SIZE 100

class Stack {
 private:
  int arr[MAX_SIZE];  // array to store the stack elements
  int top;  // top of stack

 public:
  Stack() { top = -1; }
  bool push(int x);  // push an element to the stack
  int pop();  // pop an element from the stack
  int peek();  // get the top element
  bool is_empty();  // check if the stack is empty
  int size();  // get the number of elements in the stack
};

bool Stack::push(int x) {
  if (top >= MAX_SIZE - 1) {
    // stack overflow
    return false;
  } else {
    arr[++top] = x;
    return true;
  }
}

int Stack::pop() {
  // check for stack underflow
  if (top < 0) {
    return 0;
  } else {
    int x = arr[top--];
    return x;
  }
}

int Stack::peek() {
  if (top < 0) {
    return 0;
  } else {
    int x = arr[top];
    return x;
  }
}

bool Stack::is_empty() {
  return (top < 0);
}

int Stack::size() {
  return (top + 1);
}

int main(){
	Stack stack;
	stack.push(1);
	stack.push(2);
	stack.push(3);
	cout << stack.size() << endl;  // prints 3
	cout << stack.peek() << endl;  // prints 3
	cout << stack.pop() << endl;  // prints 3
	cout << stack.is_empty() << endl;  // prints 0 (false)
	return 0;
}

```

___

## Stack Linked List Implementation

```Cpp
#include <iostream>
using namespace std;

// Definition of the Node struct
struct Node {
  int data;  // data stored in the node
  Node* next;  // pointer to the next node in the list
};

// Definition of the Stack class
class Stack {
 private:
  Node* head;  // pointer to the top of the stack
  int size;  // number of elements in the stack

 public:
  // Constructor to initialize an empty stack
  Stack() { head = NULL; size = 0; }

  // Push an element to the top of the stack
  bool push(int x);

  // Pop an element from the top of the stack
  int pop();

  // Get the top element of the stack
  int peek();

  // Check if the stack is empty
  bool is_empty();

  // Get the number of elements in the stack
  int get_size();
};

// Push an element to the top of the stack
bool Stack::push(int x) {
  // Create a new node
  Node* new_node = new Node();
  new_node->data = x;
  new_node->next = head;

  // Update the head of the list and the size of the stack
  head = new_node;
  size++;

  return true;
}

// Pop an element from the top of the stack
int Stack::pop() {
  // Check if the stack is empty
  if (is_empty()) {
    return -1;
  }

  // Get the data from the top node
  int x = head->data;

  // Update the head of the list and the size of the stack
  Node* temp = head;
  head = head->next;
  delete temp;
  size--;

  return x;
}

// Get the top element of the stack
int Stack::peek() {
  // Check if the stack is empty
  if (is_empty()) {
    return -1;
  }

  return head->data;
}

// Check if the stack is empty
bool Stack::is_empty() {
  return (head == NULL);
}

// Get the number of elements in the stack
int Stack::get_size() {
  return size;
}

int main()
{
	Stack stack;
	stack.push(1);
	stack.push(2);
	stack.push(3);
	cout << stack.get_size() << endl;  // prints 3
	cout << stack.peek() << endl;  // prints 3
	cout << stack.pop() << endl;  // prints 3
	cout << stack.is_empty() << endl;  // prints 0 (false)
	return 0;
}
```

___

# Programs based on Applications of Stacks

[[College/Sem IV/DS/DS Theory/Stacks/Decimal to Binary convertor using Stacks\|Decimal to Binary convertor using Stacks]]
[[College/Sem IV/DS/DS Theory/Stacks/Equation Solver using Stacks\|Equation Solver using Stacks]]
[[College/Sem IV/DS/DS Theory/Stacks/Tower of Hanoi\|Tower of Hanoi]]
[[College/Sem IV/DS/DS Theory/Stacks/Stack Sort\|Stack Sort]]
[[College/Sem IV/DS/DS Theory/Stacks/Infix to Postfix\|Infix to Postfix]]
[[College/Sem IV/DS/DS Theory/Stacks/Simple Postfix Calculator\|Simple Postfix Calculator]]


