---
{"dg-publish":true,"permalink":"/college/sem-iv/ds/ds-theory/queues/queues/"}
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

# Implementation and Usage of a Linear Queue in C++

A linear queue, also known as a First-In-First-Out (FIFO) queue, is a basic data structure that operates on the principle of first-in-first-out. Elements are added to the end of the queue and removed from the front. The first element to be added to the queue is the first to be removed.

Advantages of linear queue:

-   Simple and easy to implement.
-   Memory utilization is efficient.
-   The time complexity for operations such as insertion and deletion is constant.

Disadvantages of linear queue:

-   Limited in size, as it needs a pre-defined maximum size.
-   Can't be used in situations where the elements need to be accessed randomly.
-   Deletion of an element in the middle of the queue is not possible, which makes it unsuitable for certain use cases.

Linear queues are widely used in computer science and are a fundamental building block for other data structures such as stacks, priority queues, and deques. They are also used in real-world applications such as scheduling processes in an operating system, handling requests in a web server, and organizing print jobs in a printer queue.


## Linear Queue Array Implementation

```C++

#include <iostream>

using namespace std;

  

const int MAX_SIZE = 100;

  

class Queue

{

private:

    int front, rear, size;

    int arr[MAX_SIZE];

  

public:

    Queue() : front(-1), rear(-1), size(0) {}

  

    void enqueue(int data)

    {

        if (rear == MAX_SIZE - 1)

        {

            cout << "Queue is full" << endl;

            return;

        }

        arr[++rear] = data;

        size++;

    }

  

    void dequeue()

    {

        if (front == rear)

        {

            cout << "Queue is empty" << endl;

            return;

        }

        front++;

        size--;

    }

  

    int getFront()

    {

        if (front == rear)

        {

            cout << "Queue is empty" << endl;

            return -1;

        }

        return arr[front + 1];

    }

  

    int getRear()

    {

        if (front == rear)

        {

            cout << "Queue is empty" << endl;

            return -1;

        }

        return arr[rear];

    }

  

    bool isEmpty() { return front == rear; }

  

    int getSize() { return size; }

};

  

int main()

{

    Queue q;

  

    q.enqueue(1);

    q.enqueue(2);

    q.enqueue(3);

    q.enqueue(4);

  

    cout << "Front: " << q.getFront() << endl;

    cout << "Rear: " << q.getRear() << endl;

    cout << "Size: " << q.getSize() << endl;

  

    q.dequeue();

  

    cout << "Front: " << q.getFront() << endl;

    cout << "Rear: " << q.getRear() << endl;

    cout << "Size: " << q.getSize() << endl;

  

    return 0;

}

```



## Linear Queue Linked List Implementation

```C++

#include <iostream>

using namespace std;

  

class Node

{

public:

    int data;

    Node *next;

};

  

class Queue

{

private:

    Node *front;

    Node *rear;

    int size;

  

public:

    Queue() : front(nullptr), rear(nullptr), size(0) {}

  

    void enqueue(int data)

    {

        Node *newNode = new Node();

        newNode->data = data;

        newNode->next = nullptr;

  

        if (rear == nullptr)

        {

            front = rear = newNode;

            return;

        }

        rear->next = newNode;

        rear = newNode;

        size++;

    }

  

    void dequeue()

    {

        if (front == nullptr)

        {

            cout << "Queue is empty" << endl;

            return;

        }

        Node *temp = front;

        front = front->next;

        delete temp;

        size--;

        if (front == nullptr)

            rear = nullptr;

    }

  

    int getFront()

    {

        if (front == nullptr)

        {

            cout << "Queue is empty" << endl;

            return -1;

        }

        return front->data;

    }

  

    int getRear()

    {

        if (rear == nullptr)

        {

            cout << "Queue is empty" << endl;

            return -1;

        }

        return rear->data;

    }

  

    bool isEmpty() { return front == nullptr; }

  

    int getSize() { return size; }

};

  

int main()

{

    Queue q;

  

    q.enqueue(1);

    q.enqueue(2);

    q.enqueue(3);

    q.enqueue(4);

  

    cout << "Front: " << q.getFront() << endl;

    cout << "Rear: " << q.getRear() << endl;

    cout << "Size: " << q.getSize() << endl;

  

    q.dequeue();

  

    cout << "Front: " << q.getFront() << endl;

    cout << "Rear: " << q.getRear() << endl;

    cout << "Size: " << q.getSize() << endl;

  

    return 0;

}

```

___

# Implementation and Usage of a Circular Queue in C++

A circular queue is a linear data structure that operates as if the table used for the storage of elements is circular, so that when the last position is reached, the next element is stored in the first position, making a circle.

Advantages of Circular Queue:

1.  It makes efficient use of memory space by reusing the freed up space when an element is dequeued.
2.  The insertion and deletion operations can be performed efficiently.
3.  The circular queue is useful when we do not want to waste the memory space or when the size of the queue is fixed.

Disadvantages of Circular Queue:

1.  One of the major disadvantages of the circular queue is that it is more complex to implement compared to other data structures.
2.  It is difficult to expand or shrink the size of a circular queue once it is created.
3.  It is also more difficult to access elements in a circular queue as we need to keep track of the front and rear pointers.


## Circular Queue Array Implementation

```C++

#include <iostream>

using namespace std;

  

const int MAX_SIZE = 5;

  

class CircularQueue

{

private:

    int front;

    int rear;

    int arr[MAX_SIZE];

  

public:

    CircularQueue() : front(-1), rear(-1) {}

  

    void enqueue(int data)

    {

        if ((rear + 1) % MAX_SIZE == front)

        {

            cout << "Queue is full" << endl;

            return;

        }

        if (front == -1)

            front = 0;

        rear = (rear + 1) % MAX_SIZE;

        arr[rear] = data;

    }

  

    void dequeue()

    {

        if (front == -1)

        {

            cout << "Queue is empty" << endl;

            return;

        }

        if (front == rear)

        {

            front = -1;

            rear = -1;

        }

        else

        {

            front = (front + 1) % MAX_SIZE;

        }

    }

  

    int getFront()

    {

        if (front == -1)

        {

            cout << "Queue is empty" << endl;

            return -1;

        }

        return arr[front];

    }

  

    int getRear()

    {

        if (rear == -1)

        {

            cout << "Queue is empty" << endl;

            return -1;

        }

        return arr[rear];

    }

  

    bool isFull() { return (rear + 1) % MAX_SIZE == front; }

  

    bool isEmpty() { return front == -1; }

  

    int getSize()

    {

        if (front == -1)

            return 0;

        if (rear >= front)

            return rear - front + 1;

        return (MAX_SIZE - front) + (rear + 1);

    }

};

  

int main()

{

    CircularQueue q;

  

    q.enqueue(1);

    q.enqueue(2);

    q.enqueue(3);

    q.enqueue(4);

    q.enqueue(5);

  

    cout << "Front: " << q.getFront() << endl;

    cout << "Rear: " << q.getRear() << endl;

    cout << "Size: " << q.getSize() << endl;

  

    q.dequeue();

    q.enqueue(6);

  

    cout << "Front: " << q.getFront() << endl;

    cout << "Rear: " << q.getRear() << endl;

    cout << "Size: " << q.getSize() << endl;

  

    return 0;

}

```


## Circular Queue Linked List Implementation

```C++

#include <iostream>

using namespace std;

  

class Node

{

public:

    int data;

    Node *next;

};

  

class CircularQueue

{

private:

    Node *front;

    Node *rear;

    int size;

  

public:

    CircularQueue() : front(nullptr), rear(nullptr), size(0) {}

  

    void enqueue(int data)

    {

        Node *temp = new Node();

        temp->data = data;

        temp->next = nullptr;

  

        if (front == nullptr && rear == nullptr)

        {

            front = rear = temp;

            rear->next = front;

        }

        else

        {

            rear->next = temp;

            rear = temp;

            rear->next = front;

        }

        size++;

    }

  

    void dequeue()

    {

        if (front == nullptr)

        {

            cout << "Queue is empty" << endl;

            return;

        }

        if (front == rear)

        {

            front = rear = nullptr;

        }

        else

        {

            Node *temp = front;

            front = front->next;

            rear->next = front;

            delete temp;

        }

        size--;

    }

  

    int getFront()

    {

        if (front == nullptr)

        {

            cout << "Queue is empty" << endl;

            return -1;

        }

        return front->data;

    }

  

    int getRear()

    {

        if (rear == nullptr)

        {

            cout << "Queue is empty" << endl;

            return -1;

        }

        return rear->data;

    }

  

    int getSize() { return size; }

  

    bool isEmpty() { return front == nullptr; }

};

  

int main()

{

    CircularQueue q;

  

    q.enqueue(1);

    q.enqueue(2);

    q.enqueue(3);

    q.enqueue(4);

    q.enqueue(5);

  

    cout << "Front: " << q.getFront() << endl;

    cout << "Rear: " << q.getRear() << endl;

    cout << "Size: " << q.getSize() << endl;

  

    q.dequeue();

    q.enqueue(6);

  

    cout << "Front: " << q.getFront() << endl;

    cout << "Rear: " << q.getRear() << endl;

    cout << "Size: " << q.getSize() << endl;

  

    return 0;

}

```

___

# Implementation and Usage of a Deque in C++

A deque, short for "double-ended queue", is a data structure that allows elements to be inserted and removed from both the front and the rear. This makes it more flexible than a traditional queue or a stack, where elements can only be inserted at one end and removed from the other.

Advantages of using a deque include:

-   Improved versatility over queues and stacks, as elements can be inserted and removed from both ends.
-   Can be implemented as a dynamic data structure, allowing it to grow or shrink as needed.

Disadvantages of using a deque include:

-   Complexity of implementation compared to a queue or a stack.
-   Increased memory usage compared to a queue or a stack, as elements must be stored at both ends of the deque.

Overall, a deque can be a useful data structure for situations where both front and rear access to elements is required. However, it is important to consider the trade-offs between the advantages and disadvantages before deciding to use a deque.


## Deque Array Implementation

```C++

#include <iostream>

  

const int MAX = 100;

  

class Deque

{

    int array[MAX];

    int front;

    int rear;

  

public:

    Deque()

    {

        front = -1;

        rear = -1;

    }

  

    void insertFront(int value)

    {

        if (front == 0)

        {

            std::cout << "Error: Deque overflow" << std::endl;

        }

        else

        {

            if (front == -1)

            {

                front = 0;

                rear = 0;

            }

            else

            {

                front--;

            }

            array[front] = value;

        }

    }

  

    void insertRear(int value)

    {

        if (rear == MAX - 1)

        {

            std::cout << "Error: Deque overflow" << std::endl;

        }

        else

        {

            if (front == -1)

            {

                front = 0;

                rear = 0;

            }

            else

            {

                rear++;

            }

            array[rear] = value;

        }

    }

  

    void deleteFront()

    {

        if (front == -1)

        {

            std::cout << "Error: Deque underflow" << std::endl;

        }

        else

        {

            if (front == rear)

            {

                front = -1;

                rear = -1;

            }

            else

            {

                front++;

            }

        }

    }

  

    void deleteRear()

    {

        if (front == -1)

        {

            std::cout << "Error: Deque underflow" << std::endl;

        }

        else

        {

            if (front == rear)

            {

                front = -1;

                rear = -1;

            }

            else

            {

                rear--;

            }

        }

    }

  

    int getFront()

    {

        if (front == -1)

        {

            std::cout << "Error: Deque is empty" << std::endl;

            return -1;

        }

        else

        {

            return array[front];

        }

    }

  

    int getRear()

    {

        if (front == -1)

        {

            std::cout << "Error: Deque is empty" << std::endl;

            return -1;

        }

        else

        {

            return array[rear];

        }

    }

  

    bool isEmpty()

    {

        return (front == -1);

    }

  

    int size()

    {

        if (front == -1)

        {

            return 0;

        }

        else

        {

            return (rear - front + 1);

        }

    }

};

  

int main()

{

    Deque dq;

    dq.insertFront(1);

    dq.insertRear(2);

    dq.insertRear(3);

    std::cout << "Front: " << dq.getFront() << std::endl;

    std::cout << "Rear: " << dq.getRear() << std::endl;

    dq.deleteFront();

    std::cout << "Front: " << dq.getFront() << std::endl;

    std::cout << "Rear: " << dq.getRear() << std::endl;

    dq.deleteRear();

    std::cout << "Rear: " << dq.getRear() << std::endl;

    dq.deleteRear();

    if (dq.isEmpty())

    {

        std::cout << "Deque is empty" << std::endl;

    }

    else

    {

        std::cout << "Deque is not empty" << std::endl;

    }

    return 0;

}

```


## Deque Linked List Implementation

```C++ 

#include <iostream>

using namespace std;

  

class Node

{

public:

    int data;

    Node *next;

    Node *prev;

};

  

class Deque

{

private:

    Node *front;

    Node *rear;

    int count;

  

public:

    Deque() : front(nullptr), rear(nullptr), count(0) {}

  

    void insertFront(int data)

    {

        Node *temp = new Node();

        temp->data = data;

        temp->next = front;

        temp->prev = nullptr;

        if (front != nullptr)

            front->prev = temp;

        front = temp;

        if (rear == nullptr)

            rear = front;

        count++;

    }

  

    void insertRear(int data)

    {

        Node *temp = new Node();

        temp->data = data;

        temp->next = nullptr;

        temp->prev = rear;

        if (rear != nullptr)

            rear->next = temp;

        rear = temp;

        if (front == nullptr)

            front = rear;

        count++;

    }

  

    void deleteFront()

    {

        if (front == nullptr)

        {

            cout << "Deque is empty" << endl;

            return;

        }

        Node *temp = front;

        front = front->next;

        if (front != nullptr)

            front->prev = nullptr;

        delete temp;

        if (front == nullptr)

            rear = nullptr;

        count--;

    }

  

    void deleteRear()

    {

        if (rear == nullptr)

        {

            cout << "Deque is empty" << endl;

            return;

        }

        Node *temp = rear;

        rear = rear->prev;

        if (rear != nullptr)

            rear->next = nullptr;

        delete temp;

        if (rear == nullptr)

            front = nullptr;

        count--;

    }

  

    int getFront()

    {

        if (front == nullptr)

        {

            cout << "Deque is empty" << endl;

            return -1;

        }

        return front->data;

    }

  

    int getRear()

    {

        if (rear == nullptr)

        {

            cout << "Deque is empty" << endl;

            return -1;

        }

        return rear->data;

    }

  

    int size() { return count; }

  

    bool isEmpty() { return front == nullptr; }

};

  

int main()

{

    Deque d;

  

    d.insertFront(1);

    d.insertFront(2);

    d.insertRear(3);

    d.insertRear(4);

  

    cout << "Front: " << d.getFront() << endl;

    cout << "Rear: " << d.getRear() << endl;

    cout << "Size: " << d.size() << endl;

  

    d.deleteFront();

    d.deleteRear();

  

    cout << "Front: " << d.getFront() << endl;

    cout << "Rear: " << d.getRear() << endl;

    cout << "Size: " << d.size() << endl;

}

```

___
