---
{"dg-publish":true,"permalink":"/college/sem-iv/ds/ds-labs/ds-lab-7/"}
---


**Name:** [Param Makwana](mailto:paramsinghmakwana@gmail.com)                                                                                                                                                     

**Roll No:** F004

**Batch:** F1

**Date:** 21-02-23

___

# Circular Queue

```c++

#include <iostream>

#define MAX 10

using namespace std;

class QUEUE

{

public:

    int queue[MAX];

    int front, rear;

    QUEUE()

    {

        front = -1;

        rear = -1;

    }

public:

    bool enqueue(int num)

    {

        if ((front == 0 && rear == MAX - 1) || (rear == front -

                                                            1))

        {

            return false;

        }

        if (front == rear && rear == -1)

        {

            front = 0;

            rear = 0;

        }

        else

        {

            rear = (rear + 1) % MAX;

        }

        queue[rear] = num;

        return true;

    }

    int dequeue()

    {

        if (front == -1 && rear == -1)

        {

            return NULL;

        }

        int num = queue[front];

        front = (front + 1) % MAX;

        if (front == rear)

        {

            front = -1;

            rear = -1;

        }

        return num;

    }

    int Front()

    {

        return queue[front];

    }

    int size()

    {

        int count = front;

        while (count != rear)

        {

            count = (count + 1) % MAX;

        }

        return count;

    }

    int isEmpty()

    {

        if (front == -1 && rear == -1)

        {

            return 1;

        }

        return 0;

    }

};

  

int main(void)

{

    QUEUE q;

    int choice, num, result;

    while (true)

    {

        cout << "1. Enqueue" << endl;

        cout << "2. Dequeue" << endl;

        cout << "3. Front" << endl;

        cout << "4. Size" << endl;

        cout << "5. Is Empty?" << endl;

        cout << "6. EXIT" << endl;

        cout << endl

             << "Choice: ";

        cin >> choice;

        switch (choice)

        {

        case 1:

            num;

            result;

            cout << endl;

            cout << "Number: ";

            cin >> num;

            result = q.enqueue(num);

            if (result)

            {

                cout << "Added to Queue!" << endl;

            }

            else

            {

                cout << "Could not Add " << endl;

            }

            break;

        case 2:

            num;

            num = q.dequeue();

            cout << endl;

            cout << "Number: " << num << endl;

            break;

        case 3:

            num;

            num = q.Front();

            cout << endl;

            cout << "Front: " << num << endl;

            break;

        case 4:

            num;

            num = q.size();

            cout << endl;

            cout << "Size: " << num << endl;

            break;

        case 5:

            result;

            result = q.isEmpty();

            cout << endl;

            cout << "Empty: " << result << endl;

            break;

        case 6:

            cout << endl;

            cout << "Exiting..." << endl;

            return 0;

        default:

            cout << endl;

            cout << "Invalid Option!" << endl;

            break;

        }

    }

    return 0;

}

```