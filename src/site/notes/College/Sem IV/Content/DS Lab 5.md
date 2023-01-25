---
{"dg-publish":true,"permalink":"/college/sem-iv/content/ds-lab-5/"}
---

**Name:** [Param Makwana](mailto:paramsinghmakwana@gmail.com)                                                                                                                                                     

**Roll No:** F004

**Batch:** F1

**Date:** 24-01-23

___
# Part A
## Aim: Infix expression to Postfix expression

### Problem Statement:
Write a program to convert given Infix expression to Postfix expression.

###  Code:

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


### Output

![DSLAB5PIC1.png](data:image/png;base64,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)


___

# Part B

## Aim: Postfix expression evaluation

### Problem Statement:
Write a program to evaluate given Postfix expression.

### Code: 

```C++

  

#include <iostream>

  

#include <stack>

  

#include <string>

  

#include <cmath>

  

using namespace std;

  

double calculate(string postfix)

{

  

    stack<double> st;

  

    for (int i = 0; i < postfix.length(); i++)

    {

  

        if (postfix[i] >= '0' && postfix[i] <= '9')

        {

  

            st.push((double)(postfix[i] - '0'));

        }

        else

        {

  

            double num1 = st.top();

            st.pop();

  

            double num2 = st.top();

            st.pop();

  

            switch (postfix[i])

            {

  

            case '+':

  

                st.push(num2 + num1);

  

                break;

  

            case '-':

  

                st.push(num2 - num1);

  

                break;

  

            case '*':

  

                st.push(num2 * num1);

  

                break;

  

            case '/':

  

                st.push(num2 / num1);

  

                break;

  

            case '^':

  

                st.push(pow(num2, num1));

  

                break;

            case '%':

                st.push((int)num2 % (int)num1);

            }

        }

    }

  

    return st.top();

}

  

int main()

{

  

    string postfix = "23*5+";

  

    cout << "The value of the postfix expression '" << postfix << "' is: " << calculate(postfix) << endl;

  

    return 0;

}

```


### Output:

![DSLAB5PIC2.png](data:image/png;base64,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)

___

