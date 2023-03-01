---
{"dg-publish":true,"permalink":"/college/sem-iv/ds/ds-theory/stacks/tower-of-hanoi/"}
---

```c++
#include <iostream>

#include <stack>

using namespace std;

const int NUM_DISKS = 3, SOURCE = 0, DEST = 2, AUX = 1;

stack<int> towers[3];

int moves = 0;

void moveDisk(int from, int to)
{
    int disk = towers[from].top();
    towers[from].pop();
    towers[to].push(disk);
    moves++;
    cout << "Move disk " << disk << " from tower " << from + 1 << " to tower " << to + 1 << endl;
}

void printTowers()
{

    for (int i = 0; i < 3; i++)
    {
        cout << "Tower " << i + 1 << ": ";
        stack<int> tower = towers[i];
        while (!tower.empty())
        {
            cout << tower.top() << " ";
            tower.pop();
        }
        cout << endl;
    }
}

void moveTower(int n, int from, int to, int using_)
{
    if (n == 0)
    {
        return;
    }
    moveTower(n - 1, from, using_, to);
    cout << "Move disk " << n << " from tower " << from + 1 << " to tower " << to + 1 << endl;
    moveDisk(from, to);
    moveTower(n - 1, using_, to, from);
}

int main()
{

    for (int i = NUM_DISKS; i > 0; i--)
    {
        towers[0].push(i);
    }
    moveTower(NUM_DISKS, SOURCE, DEST, AUX);
    return 0;
}
```
