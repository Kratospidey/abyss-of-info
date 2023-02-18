---
{"dg-publish":true,"permalink":"/college/sem-iv/ds/ds-labs/ds-lab-6/"}
---


**Name:** [Param Makwana](mailto:paramsinghmakwana@gmail.com)                                                                                                                                                     

**Roll No:** F004

**Batch:** F1

**Date:** 14-02-23

___

# Linear Queue Array Implementation

```c++
//F004 Param Makwana

#include <iostream>

using namespace std;

  

#define MAX 10

  

class Queue {

    public:

    int front, rear;

    int arr[MAX];

  

    //Constructor

    Queue() {

        front = -1;

        rear = -1;

    }

  

    //Auxilary Functions

    bool IsFull(){

        //You can return conditionals, it will evaluate answer and then return that value

        return rear == MAX - 1;

    }

  

    bool IsEmpty(){

        return (front == -1 && rear == -1);

    }

  

    int Size() {

        if (IsEmpty()) {

            return 0;

        }

        return (rear - front) + 1;

    }

  

    int Front(){

        if (IsEmpty()) {

            return -999;

        }

        return arr[front];

    }

  

    //Main Functions

    bool Enqueue(int num){

        if (IsEmpty()) {

            front = 0;

        }

        else if (IsFull()){

            cout<<"Queue overflow"<<endl;

            return false;

        }

        arr[++rear] = num;

        return true;

    }

  

    int Dequeue(){

        if (IsEmpty()){

            cout<<"Queue underflow"<<endl;

            return 0;

        }

        else if (Size() == 1) {

            int temp = arr[front];

            rear = -1;

            front = -1;

            return temp;

        }

        cout<<"Dequeued Number: ";

        return arr[front++];

    }

  

    void Display(){

        if (IsEmpty()) {

            cout<<"Queue Underflow"<<endl;

            return ;

        }

        cout<<endl<<"Queue: ";

        for (int i = front; i <= rear; i++) {

            cout<<arr[i]<<"  ";

        }

        cout<<endl<<endl;

        return ;

    }

};

  

int main(){

    Queue a;

    int choice, num;

    do {

        cout<<"Menu:"<<endl

            <<"1. Enqueue"<<endl

            <<"2. Dequeue"<<endl

            <<"3. Display"<<endl

            <<"4. Quit"<<endl

            <<"5. Size"<<endl

            <<"6. Front"<<endl

            <<"7. IsEmpty"<<endl

            <<"8. IsFull"<<endl

            <<"$ ";

        cin >> choice;

        switch(choice){

            case 1:

                cout<<"Number to enqueue: ";

                cin>>num;

                a.Enqueue(num);

                break;

            case 2:

                cout<<"Dequeued Number: "<<a.Dequeue()<<endl<<endl;

                break;

            case 3:

                a.Display();

                break;

            case 4:

                break;

            case 5:

                cout<<"Size: "<<a.Size()<<endl;

                break;

            case 6:

                num = a.Front();

                if (num == -999) {

                    cout<<"Queue Underflow"<<endl;

                } else {

                    cout<<"Front: "<<num<<endl;

                }

                break;

            case 7:

                if (a.IsEmpty() == true) {

                    cout<<"True"<<endl;

                } else {

                    cout<<"False"<<endl;

                }

                break;

            case 8:

                if (a.IsFull() == true) {

                    cout<<"True"<<endl;

                } else {

                    cout<<"False"<<endl;

                }

                break;

            default:

                cout<<"Invalid Input";

        }

    }

    while (choice != 4);

}
```

 