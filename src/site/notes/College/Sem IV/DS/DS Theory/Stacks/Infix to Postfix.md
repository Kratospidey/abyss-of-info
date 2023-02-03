---
{"dg-publish":true,"permalink":"/college/sem-iv/ds/ds-theory/stacks/infix-to-postfix/"}
---

```C++

#include <iostream>

#include <stack>

#include <string>

#include <cctype>

using namespace std;

  

int prec(char a)

{

    if (a == '^')

    {

        return 3;

    }

    else if (a == '*' || a == '/')

    {

        return 2;

    }

    else if (a == '+' || a == '-')

    {

        return 1;

    }

    else

    {

        return -1;

    }

}

  

int main()

{

    stack<int> operators;
    

    string infix;

    cout << "Enter an infix mathematical equation" << endl;

    std::getline(std::cin, infix);


    int len = infix.length();

    string output;


    for (int i = 0; i < len; i++)

    {

        if (infix[i] != ' ')

        {

            if (isdigit(infix[i]))

            {

                output += infix[i];

            }

            else if (infix[i] == '(')

            {

                operators.push(infix[i]);

            }

            else if (operators.empty() || operators.top() == '(')

            {

                operators.push(infix[i]);

            }

            else if (infix[i] == ')')

            {

                while (operators.top() != '(')

                {

                    output += operators.top();

                    operators.pop();

                }

                operators.pop();

            }

            else

            {

                while (!operators.empty() && prec(infix[i]) <= prec(operators.top()))

                {

                    output += operators.top();

                    operators.pop();

                }

                operators.push(infix[i]);

            }

        }

    }

  

    while (!operators.empty())

    {

        output += operators.top();

        operators.pop();

    }

  

    cout << output << endl;

}

```

___
