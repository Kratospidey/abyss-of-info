---
{"dg-publish":true,"permalink":"/college/sem-iv/content/tower-of-hanoi/"}
---

```c++
#include <iostream>

#include <stack>

using namespace std;

  

const int NUM_DISKS = 3;

stack<int> towers[3];

int moves = 0;

  

void moveDisk(int from, int to) {

    int disk = towers[from].top();

    towers[from].pop();

    towers[to].push(disk);

    moves++;

    cout << "Move disk " << disk << " from tower " << from+1 << " to tower " << to+1 << endl;

}

  
  
  

void printTowers() {

    for (int i = 0; i < 3; i++) {

        cout << "Tower " << i+1 << ": ";

        stack<int> tower = towers[i];

        while (!tower.empty()) {

            cout << tower.top() << " ";

            tower.pop();

        }

        cout << endl;

    }

}

  

int main()

{

  

    for (int i = NUM_DISKS; i > 0; i--) {

        towers[0].push(i);

    }

  

    int from, to;

    cout << "Tower of Hanoi innit " << endl;

    cout << "Enter the number of the tower you want to move a disk from," << endl;

    cout << "followed by the number of the tower you want to move the disk to." << endl;

  

    while (towers[2].size() != NUM_DISKS) {

        printTowers();

        cout << "Moves made: " << moves << endl;

        cout << "Enter the tower to move disk from: ";

        cin >> from;

        cout << "Enter the tower to move disk to: ";

        cin >> to;

        if(from < 1 || from > 3 || to < 1 || to > 3) cout << "Invalid input, Please enter between 1-3" << endl;

        else if(towers[from-1].empty()) cout << "No disk in this tower!" << endl;

        else if(!towers[to-1].empty() && towers[from-1].top() > towers[to-1].top()) cout << "Can't put bigger disk on top of smaller disk!" << endl;

        else moveDisk(from-1, to-1);

    }

  

    cout << "You have successfully completed the game in " << moves << " moves!" << endl;

    cout<<"Big brain person can do it in just a single move tho"<<endl;

    return 0;

}
```
