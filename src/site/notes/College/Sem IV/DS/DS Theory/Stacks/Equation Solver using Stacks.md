---
{"dg-publish":true,"permalink":"/college/sem-iv/ds/ds-theory/stacks/equation-solver-using-stacks/"}
---

```C++

#include <iostream>

using namespace std;

#define MAX 100

  

class Stack

{

  

public:

    int top;

    char a[MAX];

  

public:

    Stack()

    {

        top = -1;

    }

    bool empty()

    {

        return top < 0;

    }

  

    bool full()

    {

        return top > MAX - 1;

    }

  

    bool push(int x)

    {

        if (full())

        {

            cout << "Stack overflow!" << endl;

            return false;

        }

        else

        {

            a[++top] = x;

            return true;

        }

    }

  

    int pop()

    {

        if (empty())

        {

            cout << "Stack underflow!" << endl;

            return 0;

        }

        else

        {

            return a[top--];

        }

    }

    int peek()

    {

        if (empty())

        {

            cout << "Stack underflow!" << endl;

            return 0;

        }

        else

        {

            return a[top];

        }

    }

  

    int size()

    {

        return MAX;

    }

};

  

int main()

{

    Stack s;

    char t;

    bool shit;

    char *str = new char[100];

    cin>>str;

    for(int i = 0; i < MAX; i++){

        if(str[i] == '(' ||str[i] == '[' || str[i] == '{'){

            s.push(str[i]);

        }

        if(str[i] == ')' ||str[i] == ']' || str[i] == '}'){

            t = s.pop();

            if ((t == '[' && str[i] != ']') || (t == '(' && str[i] != ')') || (t == '{' && str[i] != '}')){

                cout<<"Invalid set of brackets"<<endl;

                shit = true;

                break;

            }

        }

  

    }

    if(!shit){

        cout<<"You know basic maths"<<endl;

    }

  

}


```