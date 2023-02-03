---
{"dg-publish":true,"permalink":"/college/sem-iv/ds/queues/"}
---

# What is a Queue

A queue is a linear data structure that follows a First In First Out (FIFO) principle. This means that the first element added to the queue will be the first one to be removed.

A queue has two main operations: enqueue and dequeue. Enqueue is the operation of adding an element to the end of the queue, and dequeue is the operation of removing the element from the front of the queue.

Queues are often used to store data that needs to be processed in a specific order, or to store data that will be used by multiple consumers.

An example of a queue in real life is a line of people waiting to buy tickets at a ticket counter. The person at the front of the line is the first one to be served, and the person at the end of the line is the last one to be served.

In computer science, queues are often used to store data that needs to be transmitted over a network or to store tasks that need to be executed by a computer.

There are several variations of queues, including circular queues, priority queues, and double-ended queues (also known as deques).

___

# ADT of a Queue

The ADT (Abstract Data Type) of a queue is a set of operations that can be performed on a queue data structure. The essential  operations of a queue ADT are:

-  `enqueue(element)`: adds an element to the end of the queue.
-  `dequeue()`: removes and returns the element at the front of the queue.
-  `peek()`: returns the element at the front of the queue without removing it.
-  `is_empty()`: returns `true` if the queue is empty, `false` otherwise.
-  `size()`: returns the number of elements in the queue.

Some queue ADTs may also include additional operations, such as:

-  `clear()`: removes all elements from the queue.
-  `contains(element)`: returns `true` if the queue contains the given element, `false` otherwise.

The specific implementation of a queue ADT may vary depending on the language and the needs of the application. However, the basic operations described above are common to most queue ADTs.

___

# Implementation and Usage of a Queue in C++


## Queue Array Implementation

```C++

#include <iostream>
using namespace std;

const int MAX_SIZE = 100;

class Queue {
 private:
  int arr[MAX_SIZE];  // array to store the queue elements
  int front;  // index of the front element
  int rear;  // index of the rear element
  int size;  // number of elements in the queue

 public:
  Queue() { front = 0; rear = MAX_SIZE - 1; size = 0; }
  bool enqueue(int x);  // add an element to the queue
  int dequeue();  // remove and return the front element
  int peek();  // get the front element
  bool is_empty();  // check if the queue is empty
  int get_size();  // get the number of elements in the queue
};

// Add an element to the queue
bool Queue::enqueue(int x) {
  // check for queue overflow
  if (size >= MAX_SIZE) {
    return false;
  }
  size++;
  rear = (rear + 1) % MAX_SIZE;
  arr[rear] = x;
  return true;
}

// Remove and return the front element
int Queue::dequeue() {
  // check for queue underflow
  if (is_empty()) {
    return -1;
  }
  int x = arr[front];
  front = (front + 1) % MAX_SIZE;
  size--;
  return x;
}

// Get the front element
int Queue::peek() {
  // check for queue underflow
  if (is_empty()) {
    return -1;
  }
  return arr[front];
}

// Check if the queue is empty
bool Queue::is_empty() {
  return (size == 0);
}

// Get the number of elements in the queue
int Queue::get_size() {
  return size;
}

 
int main() {
  Queue queue;
  queue.enqueue(1);
  queue.enqueue(2);
  queue.enqueue(3);
  cout << queue.get_size() << endl;  // prints 3
  cout << queue.peek() << endl;  // prints 1
  cout << queue.dequeue() << endl;  // prints 1
  cout << queue.is_empty() << endl;  // prints 0 (false)

  return 0;
}

```

___

## Queue Linked List Implementation

```C++

#include <iostream>
using namespace std;

struct Node {
  int data;
  Node* next;
};

class Queue {
 private:
  Node* front;  // pointer to the front of the queue
  Node* rear;  // pointer to the rear of the queue
  int size;  // number of elements in the queue

 public:
  Queue() { front = NULL; rear = NULL; size = 0; }
  bool enqueue(int x);  // add an element to the queue
  int dequeue();  // remove and return the front element
  int peek();  // get the front element
  bool is_empty();  // check if the queue is empty
  int get_size();  // get the number of elements in the queue
};

// Add an element to the queue
bool Queue::enqueue(int x) {
  // create a new node
  Node* new_node = new Node();
  new_node->data = x;
  new_node->next = NULL;

  // update the rear of the queue and the size
  if (is_empty()) {
    front = new_node;
  } else {
    rear->next = new_node;
  }
  rear = new_node;
  size++;

  return true;
}

// Remove and return the front element
int Queue::dequeue() {
  // check for queue underflow
  if (is_empty()) {
    return -1;
  }

  // get the data from the front node
  int x = front->data;

  // update the front of the queue and the size
  Node* temp = front;
  front = front->next;
  delete temp;
  size--;

  // update the rear of the queue if the queue is now empty
  if (is_empty()) {
    rear = NULL;
  }

  return x;
}

// Get the front element
int Queue::peek() {
  // check for queue underflow
  if (is_empty()) {
    return -1;
  }

  return front->data;
}

// Check if the queue is empty
bool Queue::is_empty() {
  return (front == NULL);
}

// Get the number of elements in the queue
int Queue::get_size() {
  return size;
}

int main() {
  Queue queue;
  queue.enqueue(1);
  queue.enqueue(2);
  queue.enqueue(3);
  cout << queue.get_size() << endl;  // prints 3
  cout << queue.peek() << endl;  // prints 1
  cout << queue.dequeue() << endl;  // prints 1
  cout << queue.is_empty() << endl;  // prints 0 (false)

  return 0;
}

```

___

