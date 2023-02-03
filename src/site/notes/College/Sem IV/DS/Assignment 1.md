---
{"dg-publish":true,"permalink":"/college/sem-iv/ds/assignment-1/"}
---


| Roll no.:           | Name               |
| ------------------- | ------------------ |
| Prog/Yr/Sem:        | Batch:             |
| Date of Assignment: 25/01/2023 | Date of Submission: 25/01/2023 | 

## 1. Write a Program for Inventory Updating using a structure having (char name [20], float rate, int qty, float price).

### a) Ask the user to enter one record (keep price blank). Create a function to calculate the price = rate * qty and store it for the record. Also, ask the user for updating the rate and qty and update the record and recalculate the price. Display all the details of the record.

Program:
```C++
#include <iostream>

using namespace std;

  

typedef struct {

char name[20];

float rate, price;

int qty;

}

Inventory;

  

void Calculate (Inventory &a) {

a.price = (float) a.rate * a.qty;

return ;

}

  

void Display (Inventory &a) {

cout<<"Name: "<<a.name<<endl

<<"Rate: "<<a.rate<<endl

<<"Quantity: "<<a.qty<<endl

<<"Price: "<<a.price<<endl

<<endl;

}

  

void EnterInformation(Inventory &a) {

cout<<"Name: ";

cin >> a.name;

cout<<"Rate: ";

cin >> a.rate;

cout<<"Quantity: ";

cin >> a.qty;

cout<<endl;

}

  

int main() {

int choice;

Inventory a;

while (true) {

cout<<"1. Input Information"<<endl

<<"2. Display Informtation"<<endl

<<"3. Quit"<<endl;

cout<<">> ";

cin>>choice;

switch (choice) {

case 1:

EnterInformation(a);

Calculate(a);

break;

case 2:

Display(a);

break;

case 3:

cout<<"Quitting..."<<endl;

return 0;

default:

cout<<"Invalid choice"<<endl;

}

}

return 0;

}
```

