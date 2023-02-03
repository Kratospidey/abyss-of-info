---
{"dg-publish":true,"permalink":"/college/sem-iv/ds/decimal-to-binary-convertor-using-stacks/"}
---

```C++

#include <iostream>
using namespace std;

class Stack {
    public:
    int arr[100], top;


    Stack() {
        this->top = -1;
    }

    //Auxilary functions

    bool IsEmpty() {
        if (this->top == -1){
            return true;
        }
        return false;
    }

    bool IsFull() {
        if (this->top == 99){
            return true;
        }
        return false;
    }

    void Size(){
        cout<<"Size: "<<top + 1<<endl<<endl;
        return ;
    }

    void Peek(){
        if (IsEmpty()){
            cout<<"Stack is empty"<<endl;
            return ;
        }
        cout<<"Topmost element: "<<arr[top]<<endl<<endl;
        return ;
    }

    //Main functions

    bool Push(int a){
        if (IsFull()) {
            cout<<"Stack is already full"<<endl;
            return false;
        }
        top++;
        arr[top] = a;
        return true;
    }

    bool Pop () {
        if (IsEmpty()){
            cout<<"Stack is already empty"<<endl;
            return false;
        }
        top--;
        return true;
    }

    void Display() {
        cout<<"Stack: "<<endl;
        for (int i = top; i >= 0; i--){
            cout<<arr[i]<<endl;
        }
        cout<<endl;
    }

};

int main(){
    Stack a;
    int n;
    cout<<"Enter base-10 number: "<<endl;
    cin>>n;
    while (n > 0){
        a.Push(n % 2);
        n = n / 2;
    }
    while (!a.IsEmpty()){
        cout<<a.arr[a.top];
        a.Pop();
    }
    cout<<endl;
    return 0;
}

```

